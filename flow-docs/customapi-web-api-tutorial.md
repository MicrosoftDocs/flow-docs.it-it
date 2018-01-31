---
title: Creare un connettore personalizzato per un'API Web | Microsoft Docs
description: Informazioni su come creare un'API Web ASP.NET con autenticazione di Azure Active Directory in Microsoft Flow
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
ms.date: 12/06/2016
ms.author: sunayv
ms.openlocfilehash: fef904b02d4b0f028edba236b73e19155b6f4919
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2018
---
# <a name="build-a-custom-connector-for-a-web-api-in-microsoft-flow"></a>Creare un connettore personalizzato per un'API Web in Microsoft Flow
Questa esercitazione illustra come iniziare a creare un'API Web ASP.NET, ospitarla nelle App Web di Azure, abilitare l'autenticazione di Azure Active Directory e quindi registrare l'API Web ASP.NET in Microsoft Flow. Dopo aver registrato l'API, è possibile connettersi a essa e chiamarla dal flusso. 

## <a name="prerequisites"></a>Prerequisiti
* Una [sottoscrizione di Azure](https://azure.microsoft.com/free/).
* Un [account PowerApps](https://powerapps.microsoft.com).
* [Visual Studio](https://www.visualstudio.com/vs/) 2013 o versione successiva.

## <a name="create-an-aspnet-web-api-and-deploy-it-to-azure"></a>Creare un'API Web ASP.NET e distribuirla in Azure
1. In Visual Studio fare clic su **File** > **Nuovo progetto** per creare una nuova applicazione Web C# ASP.NET.
   
    ![Nuova App Web](./media/customapi-web-api-tutorial/newwebapp.png)
2. Selezionare il modello **API Web**.  Lasciare selezionato **Ospita nel cloud**.  Fare clic su **Modifica autenticazione**.
   
    ![Modello Nuovo progetto Web](./media/customapi-web-api-tutorial/new-web-api.png)
3. Selezionare **No Authentication** (Nessuna autenticazione), quindi fare clic su **OK**.
   
    ![No Authentication (Nessuna autenticazione)](./media/customapi-web-api-tutorial/noauth.png)
4. Fare clic su **OK** nella finestra di dialogo **Nuovo progetto ASP.NET**.  Viene visualizzata la finestra di dialogo Configura App Web di Microsoft Azure.
   
    ![Configura App Web di Microsoft Azure](./media/customapi-web-api-tutorial/azure-publishing.png)]
   
    Selezionare il proprio account Azure, digitare un **nome dell'App Web** (oppure lasciare quello predefinito) e selezionare la **sottoscrizione** di Azure.  Selezionare o creare un **piano di servizio app** (cioè una raccolta di App Web nella sottoscrizione).  Selezionare o creare un **gruppo di risorse** (un raggruppamento di risorse di Azure nella sottoscrizione).  Selezionare l'area geografica in cui deve essere distribuita l'App Web.  Se richiesto per l'API Web, selezionare o creare un **server di database** di Azure.  Infine, fare clic su **OK**.
5. Creare l'API Web.
   
   > [!NOTE]
   > Se non si ha già codice pronto per un'API Web, provare l'esercitazione [Introduzione all'API Web ASP.NET 2 (C#)](https://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api).
   > 
   > 
6. Per connettere l'API Web a PowerApps, è necessario un file [Swagger](http://swagger.io/) che descriva le operazioni.  È possibile scrivere il proprio file OpenAPI usando l'[editor online](http://editor.swagger.io/), tuttavia, per questa esercitazione, si userà uno strumento open source chiamato [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle/blob/master/README.md).  Installare il pacchetto NuGet Swashbuckle nel progetto Visual Studio facendo clic su **Strumenti** > **Gestione pacchetti NuGet** > **Console di Gestione pacchetti**, quindi digitare il comando `Install-Package Swashbuckle` nella Console di Gestione pacchetti.
   
    ![Install-Package Swashbuckle](./media/customapi-web-api-tutorial/swashbuckle-console.png)
   
   > [!TIP]
   > Quando si esegue l'applicazione API Web dopo l'installazione di Swashbuckle, viene ora generato un file OpenAPI all'URL `http://<your root URL>/swagger/docs/v1`.  L'interfaccia utente generata è disponibile anche all'indirizzo `http://<your root URL>/swagger`.
   > 
   > 
7. Quando l'API Web è pronta, pubblicarla in Azure. Per pubblicare da Visual Studio, fare clic con il pulsante destro del mouse sul progetto Web in Esplora soluzioni, fare clic su **Pubblica...**, quindi seguire le istruzioni nella finestra di dialogo Pubblica.
8. Recuperare il file JSON OpenAPI accedendo a `https://<azure-webapp-url>/swagger/docs/v1`.  Salvare il contenuto come file JSON.  A seconda del browser, potrebbe essere necessario copiare e incollare il testo in un file di testo vuoto.   
   
   > [!IMPORTANT]
   > Un documento OpenAPI con ID operazione duplicati non è valido. Se si usa il modello C# di esempio, l'ID operazione `Values_Get` viene ripetuto. È possibile correggere il problema modificando un'istanza in `Value_Get` e ripetendo la pubblicazione.
   > 
   > È anche possibile scaricare un file [OpenAPI di esempio](https://pwrappssamples.blob.core.windows.net/samples/webAPI.json) da questa esercitazione. Prima di usarlo, assicurarsi di rimuovere i commenti (che iniziano con `//`).
   > 
   > 

## <a name="set-up-azure-active-directory-authentication"></a>Configurare l'autenticazione in Azure Active Directory
Ora verranno create due applicazioni di Azure Active Directory (AAD) in Azure.  Un esempio di come eseguire questa operazione è disponibile nell'[esercitazione su Azure Resource Manager](customapi-azure-resource-manager-tutorial.md#enable-authentication-in-azure-active-directory).

> [!IMPORTANT]
> Le due app devono trovarsi nella stessa directory.
> 
> 

### <a name="first-aad-application-securing-the-web-api"></a>Prima applicazione di AAD: proteggere l'API Web
La prima applicazione di Azure AD viene usata per proteggere l'API Web. Assegnarle il nome **webAPI**.  Seguire i passaggi dell'esercitazione sopra (solo la sezione intitolata "Abilitare l'autenticazione in Azure Active Directory") con i valori seguenti:

* URL di accesso: `https://login.windows.net`
* URL di risposta: `https://<your-root-url>/.auth/login/aad/callback`
* Non è necessaria una chiave client.
* Non è necessario delegare le autorizzazioni.
* **Importante** Annotare l'ID applicazione,  perché verrà usato in un secondo momento.

### <a name="second-aad-application-securing-the-custom-connector-and-delegated-access"></a>Seconda applicazione di AAD: proteggere il connettore personalizzato e l'accesso delegato
La seconda applicazione di AAD viene usata per proteggere la registrazione del connettore personalizzato e acquisire l'accesso delegato all'API Web protetta dalla prima applicazione. Assegnarle il nome **webAPI-customAPI** .

* URL di accesso: `https://login.windows.net`
* URL di risposta: `https://msmanaged-na.consent.azure-apim.net/redirect`
* Aggiungere le autorizzazioni per disporre dell'accesso delegato all'API Web.
* Prendere nota anche dell'ID di questa applicazione, perché servirà anch'esso in un secondo momento.
* Generare una chiave client e archiviarla in un luogo sicuro. Questa chiave servirà in un secondo momento.

## <a name="add-authentication-to-your-azure-web-app"></a>Aggiungere l'autenticazione all'App Web di Azure
1. Accedere al [portale di Azure](https://portal.azure.com) e trovare l'App Web distribuita nella prima sezione.
2. Fare clic su **Impostazioni**, quindi selezionare **Autenticazione/Autorizzazione**.
3. Attivare l'**autenticazione servizio app** e selezionare **Azure Active Directory**.  Nel pannello successivo selezionare **Rapida**.  
4. Fare clic su **Seleziona app AD esistente** e selezionare l'applicazione AAD **webAPI** creata in precedenza.

A questo punto sarà possibile usare AAD per autenticare l'applicazione Web.

## <a name="add-the-custom-connector-to-microsoft-flow"></a>Aggiungere il connettore personalizzato a Microsoft Flow
1. Modificare il file OpenAPI aggiungendo l'oggetto `securityDefintions` e l'autenticazione AAD usata per l'App Web. La sezione del file OpenAPI contenente la proprietà **host** dovrebbe avere questo aspetto:

```javascript
// File header should be above here...

"host": "<your-root-url>",
"schemes": [
    "https"         //Make sure this is https!
],
"securityDefinitions": {
    "AAD": {
        "type": "oauth2",
        "flow": "accessCode",
        "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
        "tokenUrl" : "https://login.windows.net/common/oauth2/token",
        "scopes": {}
    }
},

// The rest of the OpenAPI follows...
```

1. Passare a [Microsoft Flow](https://flow.powerapps.com) e aggiungere un connettore personalizzato come descritto in [Registrare e usare i connettori personalizzati in Microsoft Flow](register-custom-api.md).
2. Dopo aver caricato il file OpenAPI, la procedura guidata riconosce automaticamente che è in uso l'autenticazione AAD per l'API Web.
3. Configurare l'autenticazione di AAD per il connettore personalizzato.  
   
   * **ID client**: *l'ID client di webAPI-CustomAPI*
   * **Segreto**: *la chiave client di webAPI-CustomAPI*
   * **URL di accesso**: `https://login.windows.net`
   * **ResourceUri**: *l'ID client di webAPI*
4. Fare clic su **Crea** e creare una connessione al connettore personalizzato.

## <a name="next-steps"></a>Passaggi successivi
Esplorare il connettore personalizzato nell'[esercitazione su Azure Resource Manager](customapi-azure-resource-manager-tutorial.md).

