---
title: Registrare e usare i connettori personalizzati | Microsoft Docs
description: Registrare e usare i connettori personalizzati in Microsoft Flow usando OpenAPI e Postman.
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: sunayv
ms.openlocfilehash: 94d46b2948f03316162e1c1d45860ae94feb897c
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="register-and-use-custom-connectors-in-microsoft-flow"></a>Registrare e usare i connettori personalizzati in Microsoft Flow
Microsoft Flow consente di compilare flussi di lavoro senza codice. In alcuni casi, però, è necessario estendere le funzionalità di Microsoft Flow e i servizi web sono una scelta naturale a tale scopo. Il flusso può connettersi a un servizio, eseguire operazioni e ottenere dati. Quando si vuole connettere un determinato servizio Web a Microsoft Flow, è possibile registrarlo come connettore personalizzato. Questo processo consente a Microsoft Flow di comprendere le caratteristiche della propria API Web, inclusa l'autenticazione che richiede, le operazioni che supporta e i parametri e gli output per ognuna di tali operazioni.

In questo argomento vengono esaminati i passaggi necessari per registrare e usare un connettore personalizzato e verrà usata l'[API Analisi del testo](https://www.microsoft.com/cognitive-services/text-analytics-api) di Servizi cognitivi di Azure. Questa API identifica il linguaggio, la valutazione e le frasi chiave nel testo che le viene passato.

## <a name="prerequisites"></a>Prerequisiti
* Un [account Microsoft Flow](https://flow.microsoft.com).
* Un file OpenAPI 2.0 (precedentemente noto come Swagger) in formato JSON, un URL a una definizione di OpenAPI o un file Postman Collection per l'API. Se non si ha nessuno di questi prerequisiti, saranno fornite indicazioni per l'utente.
* Un'immagine da usare come icona per il connettore personalizzato (facoltativo).

## <a name="steps-in-the-custom-connector-process"></a>Passaggi del processo del connettore personalizzato
Il processo del connettore personalizzato prevede diversi passaggi, che verranno descritti brevemente di seguito. Questo articolo presuppone che si abbia già un'API RESTful con un tipo qualsiasi di accesso con autenticazione, perciò ci la parte restante sarà concentrata sui passaggi da 3 a 6. Per un esempio dei passaggi 1 e 2, vedere [Creare un'API Web personalizzata per Microsoft Flow](customapi-web-api-tutorial.md).

1. **Compilare un'API RESTful** nel linguaggio e nella piattaforma di propria scelta. Per le tecnologie Microsoft, è consigliabile una delle seguenti (ma è possibile usare qualsiasi piattaforma):
   
   * Funzioni di Azure
   * App Web di Azure
   * App per le API di Azure
2. **Proteggere l'API** usando uno dei seguenti meccanismi di autenticazione. È possibile consentire l'accesso non autenticato ai connettori, ma non è consigliabile.
   
   * Azure Active Directory. Per altre informazioni, vedere [Usare Azure Active Directory con un connettore personalizzato in Microsoft Flow](customapi-azure-resource-manager-tutorial.md).
   * OAuth 2.0 per servizi specifici come Dropbox, Facebook e SalesForce
   * OAuth 2.0 generica
   * Chiave API
   * Autenticazione di base
3. **Descrivere l'API** in uno dei due modi standard del settore, in modo che Microsoft Flow possa connettersi ad essa.
   
   * Un file OpenAPI
   * Un file Postman Collection
     
     È anche possibile compilare un file OpenAPI nel passaggio 4 come parte del processo di registrazione.
4. **Registrare il connettore personalizzato** usando una procedura guidata in Microsoft Flow, in cui si specifica la descrizione di un'API, i dettagli di sicurezza e altre informazioni.
5. **Usare il connettore personalizzato** in un'app. Creare una connessione al connettore all'interno dell'app e chiamare qualsiasi operazione fornita dall'API, proprio come si chiamano le connessioni standard in Microsoft Flow.
6. **Condividere il connettore personalizzato** come se si trattasse delle altre risorse in Microsoft Flow. Questo passaggio è facoltativo, ma è spesso opportuno condividere i connettori personalizzati tra più autori di app.

## <a name="describe-your-api"></a>Descrivere l'API
Supponendo che si abbia un'API con un tipo qualsiasi di accesso con autenticazione, è necessario descriverla in modo che Microsoft Flow possa connettersi a essa. A tale scopo, creare un file OpenAPI o un file Postman Collection da *qualsiasi* endpoint API REST, tra cui:

* Connettori pubblicamente disponibili. Alcuni esempi sono [Spotify](https://developer.spotify.com/), [Uber](https://developer.uber.com/), [Slack](https://api.slack.com/), [Rackspace](http://docs.rackspace.com/) e altri ancora.
* Un'API creata e distribuita in qualsiasi provider di hosting su cloud, tra cui Azure, Amazon Web Services (AWS), Heroku, Google Cloud e altri ancora.
* Un'API line-of-business personalizzata distribuita nella propria rete, purché esposta sulla rete Internet pubblica.

I file OpenAPI 2.0 (precedentemente noti come Swagger) e Postman Collection usano formati differenti, ma sono entrambi documenti indipendenti dal linguaggio e in un formato leggibile al computer che descrivono le operazioni e i parametri dell'API:

* È possibile generare questi documenti usando una serie di strumenti a seconda del linguaggio e della piattaforma di cui si avvale l'API. Per un esempio di file OpenAPI, vedere la [documentazione dell'API Analisi del testo](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/export?DocumentFormat=Swagger&ApiName=Azure).
* Se non si ha già un file OpenAPI per la propria API e non si vuole crearne uno, è comunque possibile creare facilmente un connettore personalizzato usando un file Postman Collection. Per altre informazioni, vedere [Creare un file Postman Collection](postman-collection.md).
* Microsoft Flow usa sostanzialmente OpenAPI dietro le quinte, in modo che un file Postman Collection venga analizzato e convertito in un file di definizione OpenAPI.

**Nota**: le dimensioni del file devono essere inferiori a 1 MB.

### <a name="getting-started-with-openapi-and-postman"></a>Introduzione a OpenAPI e Postman
* Se non si ha familiarità con OpenAPI, vedere l'[introduzione a OpenAPI](http://swagger.io/getting-started/) sul sito swagger.io.
* Se non si ha familiarità con Postman, installare l'[app Postman](https://www.getpostman.com/apps) dal relativo sito.
* Se l'API viene compilata con le App per le API di Azure o Funzioni di Azure, vedere [Esportazione di un'API ospitata in Azure in PowerApps e Microsoft Flow](https://docs.microsoft.com/azure/app-service/app-service-export-api-to-powerapps-and-flow) per altre informazioni.

## <a name="register-your-custom-connector"></a>Registrare il connettore personalizzato
A questo punto, si userà il file OpenAPI o Postman Collection per registrare il connettore personalizzato in Microsoft Flow.

1. In [flow.microsoft.com](https://flow.microsoft.com), nella barra superiore, selezionare l'icona a forma ingranaggio per aprire il menu Impostazioni. Selezionare l'opzione **Connettori personalizzati**.
   
    ![Crea connettore personalizzato](./media/register-custom-api/managecustomapi.png)  
2. Selezionare **Crea connettore personalizzato**.
   
    ![Proprietà del connettore personalizzato](./media/register-custom-api/newcustomapi.png)
3. Nella scheda **Generale** scegliere come si vuole creare il connettore personalizzato.
   
   * Caricare OpenAPI
   * Incollare l'URL OpenAPI
   * Caricare un file Postman Collection V1
     
     ![Come creare un connettore personalizzato](./media/register-custom-api/choosehowtocreate.png)
     
     Caricare un'icona per il connettore personalizzato. I campi Descrizione, Host e URL di Base sono in genere popolati automaticamente con le informazioni dal file OpenAPI. Se non sono popolati automaticamente, è possibile aggiungervi informazioni manualmente. Selezionare **Continua**.
4. Nella scheda **Sicurezza** immettere le proprietà di autenticazione.
   
    ![Tipi di autenticazione](./media/register-custom-api/authenticationtypes.png)
   
   * Il tipo di autenticazione viene popolato automaticamente in base a ciò che si definisce nell'oggetto `securityDefinitions` del file OpenAPI. Di seguito è riportato un esempio di OAuth 2.0.
     
       ```
       "securityDefinitions": {
           "AAD": {
           "type": "oauth2",
           "flow": "accessCode",
           "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
           "tokenUrl": "https://login.windows.net/common/oauth2/token"
           "scopes": {}
           }
       },
       ```
   * Se il file OpenAPI non usa l'oggetto `securityDefintions`, non sono necessari valori aggiuntivi.
   * Quando si usa un file Postman Collection, il tipo di autenticazione viene popolato automaticamente solo quando si usano i tipi di autenticazione supportati, ad esempio OAuth 2.0 o Di base.
   * Per un esempio di impostazione dell'autenticazione di Azure Active Directory (AAD), vedere [Creare un'API Web personalizzata per Microsoft Flow](customapi-web-api-tutorial.md#set-up-azure-active-directory-authentication).
5. Nella scheda **Definizioni**, tutte le operazioni definite nel file OpenAPI o Postman Collection, insieme ai valori di richiesta e risposta, vengono popolati automaticamente. Se sono state definite tutte le operazioni necessarie, è possibile andare al passaggio 6 del processo di registrazione senza apportare modifiche in questa schermata.
   
    ![Scheda Definizione](./media/register-custom-api/definitiontab.png)
   
    Se si vogliono modificare le azioni esistenti o aggiungere nuove azioni al connettore personalizzato, continuare a leggere qui di seguito.
   
   1. Se si vuole aggiungere una nuova azione che non è già nel file OpenAPI o Postman Collection, selezionare **Nuova azione** nel riquadro a sinistra e compilare la sezione **Generale** con il nome, la descrizione e la visibilità dell'operazione.
   2. Nella sezione **Richiesta** selezionare **Importa da esempio** in alto a destra. Nel modulo a destra, incollare una richiesta di esempio. Le richieste di esempio sono in genere disponibili nella documentazione dell'API, in cui è possibile ottenere informazioni per la compilazione dei campi **Verbo**, **URL richiesta**, **Intestazioni** e **Corpo**. Per un esempio, vedere la [documentazione dell'API Analisi del testo](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/operations/56f30ceeeda5650db055a3c6).
      
      > [!IMPORTANT]
      > Assicurarsi di rimuovere l'intestazione `Content-type` dalle azioni, perché verrà aggiunta automaticamente da Microsoft Flow. Le intestazioni di autenticazione definite nella sezione **Security** devono essere rimosse anche da azioni e trigger. 
      > 
      > 
      
      ![Importa da esempio](./media/register-custom-api/importfromsample.png)
   3. Selezionare **Importa** per completare la definizione della richiesta. Definire la risposta in modo analogo.
6. Dopo aver definito tutte le operazioni, selezionare **Crea** per creare il connettore personalizzato.
7. Dopo aver creato il connettore personalizzato, passare alla scheda **Test** per testare le operazioni definite nell'API. Scegliere una connessione e fornire parametri di input per testare un'operazione.
   
    ![Testare il connettore personalizzato](./media/register-custom-api/testcustomapi.png)
   
    Se la chiamata è riuscita, si otterrà una risposta valida.
   
    ![Testare la risposta del connettore](./media/register-custom-api/testapiresponse.png)

### <a name="quota-and-throttling"></a>Quota e limitazione
* Per informazioni dettagliate sulle quote di creazione del connettore personalizzato, vedere la pagina dei [prezzi di Microsoft Flow](https://flow.microsoft.com/pricing/). I connettori personalizzati condivisi con l'utente corrente non vengono conteggiati in questa quota.
* Per ciascuna connessione creata in un connettore personalizzato, è possibile eseguire fino a 500 richieste al minuto.

## <a name="share-your-custom-connector"></a>Condividere il connettore personalizzato
Ora che è stato creato un connettore personalizzato, è possibile condividerlo con altri utenti nell'organizzazione. Tenere presente che quando si condivide un connettore personalizzato, altri utenti potrebbero cominciare a dipendere da esso e che eliminandolo saranno eliminate anche tutte le connessioni al connettore. Se si vuole fornire un connettore agli utenti esterni all'organizzazione, vedere la [panoramica sulla certificazione dei connettori personalizzati in Microsoft Flow](api-connector-overview.md).

1. In [flow.microsoft.com](https://flow.microsoft.com), nella barra superiore, selezionare l'icona a forma ingranaggio per aprire il menu Impostazioni. Selezionare l'opzione **Connettori personalizzati**.
   
    ![Nuova connessione](./media/register-custom-api/managecustomapi.png)
2. Selezionare i puntini di sospensione (**...**) per il connettore, quindi selezionare **Visualizza proprietà**.  
   
    ![Visualizzare le proprietà del connettore](./media/register-custom-api/view-properties.png)
3. Selezionare **Condividi**, quindi immettere gli utenti o gruppi a cui si vuole concedere l'accesso al connettore.  
   
    ![Condividere un connettore personalizzato](./media/register-custom-api/sharecustomapi.png)
4. Selezionare **Salva**.

## <a name="next-steps"></a>Passaggi successivi
[Informazioni su come creare un file Postman Collection](postman-collection.md)

[Informazioni sulle estensioni OpenAPI personalizzate](customapi-how-to-swagger.md).

[Usare un'API Web ASP.NET](customapi-web-api-tutorial.md).

[Registrare un'API di Azure Resource Manager](customapi-azure-resource-manager-tutorial.md).

