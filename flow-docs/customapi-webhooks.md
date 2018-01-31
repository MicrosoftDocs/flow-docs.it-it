---
title: Usare i webhook con Microsoft Flow | Microsoft Docs
description: Informazioni su come creare flussi che interagiscono con webhook in Microsoft Flow
services: 
suite: flow
documentationcenter: 
author: msftman
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/08/2017
ms.author: deonhe
ms.openlocfilehash: cf899063ed6244e85d7eb0759efc9421cbdaa327
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2018
---
# <a name="use-webhooks-with-microsoft-flow"></a>Usare webhook con Microsoft Flow
I [webhook](http://www.webhooks.org/) sono semplici callback HTTP usati per fornire notifiche di eventi.  Microsoft Flow consente di usare webhook per attivare flussi.  Questa esercitazione illustra come creare un flusso attivato da un webhook.

> [!NOTE]
> GitHub verrà usato come esempio di un servizio che può inviare notifiche tramite webhook, ma le tecniche illustrate di seguito possono essere estese a qualsiasi servizio che usa webhook.
> 
> 

## <a name="prerequisites"></a>Prerequisiti
Per completare l'esercitazione, sono necessari:

* Conoscenze di base dei [webhook](http://www.webhooks.org/).
* Conoscenze di base della [specifica OpenAPI](http://swagger.io/specification/) (Swagger).
* Un account [GitHub](https://www.github.com).
* Il [file JSON OpenAPI di esempio](https://pwrappssamples.blob.core.windows.net/samples/githubWebhookSample.json) per questa esercitazione.
* In alternativa è anche possibile usare l'[interfaccia utente dei trigger](customapi-webhooks.md#creating-webhook-triggers-from-the-ui) per definire i trigger di webhook, nel caso in cui non si voglia scrivere manualmente il file OpenAPI.

## <a name="the-openapi-file"></a>File OpenAPI
I webhook vengono implementati in Microsoft Flow come un tipo di [connettore personalizzato](register-custom-api.md), quindi sarà necessario fornire un file JSON OpenAPI per definire la forma del webhook dell'esempio.  Il file OpenAPI contiene tre definizioni essenziali per il funzionamento del webhook:

1. Creazione del webhook
2. Definizione della richiesta di hook in ingresso dall'API (in questo caso, GitHub)
3. Eliminazione del webhook

### <a name="creating-the-webhook"></a>Creazione del webhook
Il webhook viene creato sul lato GitHub mediante un POST HTTP a `/repos/{owner}/{repo}/hooks`.  Microsoft Flow dovrà eseguire il post in questo URL quando viene creato un nuovo flusso, usando il trigger definito nel file OpenAPI o ogni volta che il trigger viene modificato.  Nell'esempio seguente la proprietà `post` contiene lo schema della richiesta che verrà inviata a GitHub.

```json
"/repos/{owner}/{repo}/hooks": {
    "x-ms-notification-content": {
    "description": "Details for Webhook",
    "schema": {
        "$ref": "#/definitions/WebhookPushResponse"
    }
    },
    "post": {
    "description": "Creates a Github webhook",
    "summary": "Triggers when a PUSH event occurs",
    "operationId": "webhook-trigger",
    "x-ms-trigger": "single",
    "parameters": [
        {
        "name": "owner",
        "in": "path",
        "description": "Name of the owner of targetted repository",
        "required": true,
        "type": "string"
        },
        {
        "name": "repo",
        "in": "path",
        "description": "Name of the repository",
        "required": true,
        "type": "string"
        },
        {
        "name": "Request body of webhook",
        "in": "body",
        "description": "This is the request body of the Webhook",
        "schema": {
            "$ref": "#/definitions/WebhookRequestBody"
        }
        }
    ],
    "responses": {
        "201": {
        "description": "Created",
        "schema": {
            "$ref": "#/definitions/WebhookCreationResponse"
        }
        }
    }
    }
},
```

> [!IMPORTANT]
> La proprietà `"x-ms-trigger": "single"` è un'estensione dello schema che indica a Microsoft Flow di visualizzare questo webhook nell'elenco dei trigger disponibili nella finestra di progettazione del flusso, quindi assicurarsi di includerla.
> 
> 

### <a name="defining-the-incoming-hook-request-from-the-api"></a>Definizione della richiesta di hook in ingresso dall'API
La forma della richiesta di hook in ingresso (la notifica da GitHub a Microsoft Flow) è definita nella proprietà `x-ms-notification-content` personalizzata, come illustrato nell'esempio precedente.  Non è necessario che includa l'intero contenuto della richiesta, ma solo le parti che si vuole usare nei flussi.

### <a name="deleting-the-webhook"></a>Eliminazione del webhook
È molto importante includere una definizione in OpenAPI per indicare a Microsoft Flow come eliminare il webhook.  Microsoft Flow proverà a eliminare il webhook ogni volta che si aggiorna il trigger nel flusso o quando si elimina il flusso.

```json
"/repos/{owner}/{repo}/hooks/{hook_Id}": {
    "delete": {
    "description": "Deletes a Github webhook",
    "operationId": "DeleteTrigger",
    "parameters": [
        {
        "name": "owner",
        "in": "path",
        "description": "Name of the owner of targetted repository",
        "required": true,
        "type": "string"
        },
        {
        "name": "repo",
        "in": "path",
        "description": "Name of the repository",
        "required": true,
        "type": "string"
        },
        {
        "name": "hook_Id",
        "in": "path",
        "description": "ID of the Hook being deleted",
        "required": true,
        "type": "string"
        }
    ]
    }
},
```

> [!IMPORTANT]
> Per fare in modo che Microsoft Flow possa eliminare un webhook, l'API **deve** includere un'intestazione HTTP `Location` nella risposta 201 al momento della creazione del webhook.  L'intestazione `Location` deve contenere il percorso per il webhook che verrà usato con HTTP DELETE.  Ad esempio, il percorso `Location` incluso nella risposta di GitHub segue questo formato: `https://api.github.com/repos/<user name>/<repo name>/hooks/<hook ID>`.
> 
> 

## <a name="authentication"></a>Autenticazione
L'API che invia la richiesta di webhook a Microsoft Flow prevederà in genere una qualche forma di autenticazione e GitHub non è un'eccezione.  Sono supportati vari tipi di autenticazione.  Per questa esercitazione, useremo i token di accesso personali di GitHub.

1. Passare a [GitHub](https://www.github.com) ed eseguire l'accesso se non è già stato fatto.
2. In alto a destra fare clic sull'**immagine del profilo** e quindi fare clic su **Settings** (Impostazioni) nel menu.
   
    ![Settings (Impostazioni)](./media/customapi-webhooks/github-settings.png)
3. Nel menu a sinistra, in **Developer settings** (Impostazioni per sviluppatori), fare clic su **Personal access tokens** (Token di accesso personali).
   
    ![Personal access tokens (Token di accesso personali)](./media/customapi-webhooks/personal-access-tokens.png)
4. Fare clic sul pulsante **Generate new token** (Genera nuovo token).
   
    ![Generate new token (Genera nuovo token)](./media/customapi-webhooks/generate-new-token.png)
5. Immettere una descrizione nella casella **Token description** (Descrizione token).
6. Selezionare la casella di controllo **admin:repo_hook**.
   
    ![admin:repo_hook](./media/customapi-webhooks/repo-hook.png)
7. Fare clic sul pulsante **Generate token** (Genera token).
8. Prendere nota del nuovo token.
   
    ![Nuovo token](./media/customapi-webhooks/new-token.png)
   
   > [!IMPORTANT]
   > Non sarà possibile accedere di nuovo a questo token. È necessario copiarlo e incollarlo da qualche parte, ad esempio nel Blocco note, per usarlo in seguito nell'esercitazione.
   > 
   > 

## <a name="adding-the-webhook-to-microsoft-flow"></a>Aggiunta del webhook a Microsoft Flow
A questo punto è disponibile tutto ciò che serve per aggiungere il webhook a Microsoft Flow come connettore personalizzato.

1. Passare al [portale Web di Microsoft Flow](https://flow.microsoft.com) ed eseguire l'accesso se non è già stato fatto.
2. Fare clic sull'icona **Impostazioni** e quindi su **Connettori personalizzati**.
   
    ![connettori personalizzati](./media/customapi-webhooks/custom-apis.png)
3. Fare clic sul pulsante **Crea connettore personalizzato**.
4. Fare clic sull'icona della cartella di file nella casella **Importa OpenAPI** e quindi selezionare il file OpenAPI di esempio.
5. Fare clic su **Carica icona** nella sezione **Informazioni generali** e quindi selezionare un'immagine da usare come icona.
6. Fare clic su **Continua**.
   
    ![Importare OpenAPI](./media/customapi-webhooks/import-swagger.png)
7. Nella schermata successiva verranno configurate le impostazioni di sicurezza.  In **Tipo di autenticazione** selezionare **Autenticazione di base**.
8. Nella sezione **Autenticazione di base** immettere il testo **Nome utente** e **Password** per i campi etichetta.  Si noti che queste saranno le uniche etichette visualizzate quando il trigger viene usato in un flusso.
   
    ![Autenticazione di base](./media/customapi-webhooks/basic-auth.png)
9. Nella parte superiore della pagina assegnare un nome al flusso e fare clic su **Crea connettore**.
   
    ![Crea API](./media/customapi-webhooks/create-api.png)

Il nuovo connettore personalizzato viene visualizzato nell'elenco nella pagina dei connettori personalizzati.

## <a name="creating-webhook-triggers-from-the-ui"></a>Creazione di trigger di webhook dall'interfaccia utente
1. Dopo aver caricato/creato il file OpenAPI di base, passare alla scheda **Definizione** della procedura guidata del connettore personalizzato.
2. Nel riquadro a sinistra, fare clic su **+ Nuovo trigger** e compilare la descrizione del trigger. In questo esempio viene creato un trigger generato quando si effettua una richiesta di pull a un repository.
   
    ![Crea trigger-1](./media/customapi-webhooks/create-new-trigger-1.png)
3. Successivamente, definire la richiesta di creazione del trigger di webhook. È possibile farlo importando una richiesta *create webhook trigger* di esempio. Per la creazione di un webhook, vedere le [Informazioni di riferimento sulle API Github](https://developer.github.com/v3/repos/hooks/#create-a-hook). 
4. Microsoft Flow aggiunge automaticamente ```content-type``` standard e intestazioni di sicurezza, in modo che non sia necessario definirli durante l'importazione da un esempio. 
   
    ![Crea trigger-2](./media/customapi-webhooks/create-new-trigger-2.png)
5. Dopo aver importato la richiesta di creazione webhook, verrà definito la risposta del webhook con l'importazione da una risposta di esempio. Vedere le [Informazioni di riferimento alle API Github](https://developer.github.com/v3/activity/events/types/#pullrequestevent) per un evento di richiesta pull. 
   
    **Nota**: non è necessario incollare l'intera risposta. Devono essere definiti solo i campi necessari.
   In questo esempio vengono estratti solo l'URL della richiesta pull e le informazioni dell'utente che l'ha eseguita.
   
    ![Crea trigger-3](./media/customapi-webhooks/create-new-trigger-3.png)
6. Il passaggio finale consiste nel selezionare un parametro nella richiesta di creazione del webhook, nel cui valore Microsoft Flow deve popolare un URL di callback per Github. In questo caso, è la proprietà url nell'oggetto ```config```.
   
    ![Crea trigger-4](./media/customapi-webhooks/create-new-trigger-4.png)

## <a name="using-the-webhook-as-a-trigger"></a>Uso del webhook come trigger
Dopo aver configurato tutto il necessario, è ora possibile usare il webhook in un flusso.  Di seguito verrà creato un flusso per inviare una notifica push all'app per dispositivi mobili Microsoft Flow ogni volta che il repository GitHub riceve un comando git push.

1. Nel [portale web di Microsoft Flow](https://flow.microsoft.com), nella parte superiore della pagina, fare clic su **Flussi personali**.
2. Fare clic su **Crea da zero**.
3. Nella finestra di progettazione per Microsoft Flow cercare il connettore personalizzato registrato in precedenza.
   
    ![Nuovo trigger](./media/customapi-webhooks/new-trigger.png)
   
    Fare clic sull'elemento nell'elenco per usarlo come trigger.
4. Dato che questo è il primo utilizzo del connettore personalizzato, è necessario connettersi.  Immettere un nome descrittivo in **Nome connessione**.  Usare il nome utente di GitHub per **Nome utente**.  Per **Password** usare il **token di accesso personale** creato in precedenza.
   
    ![Nuova connessione](./media/customapi-webhooks/new-connection.png)
   
    Fare clic su **Crea**.
5. A questo punto è necessario fornire informazioni a Microsoft Flow sul repository da monitorare.  Si potrebbero riconoscere i campi dall'oggetto **WebhookRequestBody** nel file OpenAPI.  Per **owner** e **repo** immettere il nome del proprietario e del repository di un repository di GitHub da monitorare.
   
    ![Informazioni sul repository](./media/customapi-webhooks/repo-info.png)
   
   > [!IMPORTANT]
   > In questo esempio viene usato il repository per [Visual Studio Code](https://code.visualstudio.com). È necessario usare un repository per il quale l'account usato ha i diritti.  Il modo più semplice consiste nell'usare il proprio repository.
   > 
   > 
6. Fare clic su **+ Nuovo passaggio** e quindi su **Aggiungi un'azione**.
7. Cercare e selezionare l'azione **Notifica push**.
   
    ![Notifica push](./media/customapi-webhooks/push-notification.png)
8. Immettere testo nel campo **Testo**.  Si noti che l'oggetto **WebhookPushResponse** nel file OpenAPI definisce l'elenco dei parametri che è possibile usare.
   
    ![Dettagli della notifica push](./media/customapi-webhooks/push-details.png)
9. Nella parte superiore della pagina assegnare un nome al flusso e fare clic su **Crea flusso**.
   
    ![Nome del flusso](./media/customapi-webhooks/flow-name.png)

## <a name="verification-and-troubleshooting"></a>Verifica e risoluzione dei problemi
Per verificare che tutto sia configurato correttamente, fare clic su **Flussi personali** e quindi fare clic sull'**icona delle informazioni** accanto al nuovo flusso per visualizzare la cronologia di esecuzione.  Dovrebbe essere già visibile almeno un'esecuzione completata correttamente dalla creazione del webhook.  Questo indica che il webhook è stato creato correttamente sul lato di GitHub.  Se l'esecuzione non è riuscita, è possibile analizzare i dettagli di esecuzione per scoprire i motivi dell'errore.  Se l'errore è dovuto a una risposta "404 Non trovato", è probabile che l'account GitHub non abbia le autorizzazioni corrette per creare un webhook nel repository usato.

## <a name="summary"></a>Riepilogo
Se tutto è configurato correttamente, si riceveranno notifiche push nell'app per dispositivi mobili Microsoft Flow ogni volta che si verifica un comando git push nel repository GitHub selezionato.  Tramite il processo descritto sopra è possibile usare qualsiasi servizio in grado di supportare webhook come trigger nei flussi.

## <a name="next-steps"></a>Passaggi successivi
* [Registrare un connettore personalizzato](register-custom-api.md).
* [Usare un'API Web ASP.NET](customapi-web-api-tutorial.md).
* [Registrare un'API di Azure Resource Manager](customapi-azure-resource-manager-tutorial.md).

