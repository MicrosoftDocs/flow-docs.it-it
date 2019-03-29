---
title: Integrare Microsoft Flow con siti Web e app | Microsoft Docs
description: Incorporare le esperienze di Microsoft Flow in un sito Web o un'app.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 47d44b2c97275add492153d85138b7d11b554530
ms.sourcegitcommit: 3c7822c7207cfa51d0274e9647ef02e5ea1d999f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2019
ms.locfileid: "58321411"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Integrare Microsoft Flow con siti Web e app

Incorporare Microsoft Flow nell'app o nel sito Web usando *widget di Flow* per offrire agli utenti un modo semplice per automatizzare le attività personali o professionali.

I widget di Flow sono iframe che si trovano in un documento host. Questo documento punta a una pagina nella finestra di progettazione di Microsoft Flow. Questi widget integrano la funzionalità specifica di Microsoft Flow nell'applicazione di terze parti.

I widget possono essere semplici. Ad esempio, un widget che esegue il rendering di un elenco di modelli senza alcuna comunicazione tra host e iframe. I widget possono essere anche complessi. Ad esempio, un widget che effettua il provisioning di un flusso da un modello e quindi attiva il flusso tramite una comunicazione bidirezionale tra host e widget.

## <a name="prerequisites"></a>Prerequisiti

- Un **account Microsoft** oppure
- Un account aziendale o dell'istituto di istruzione

## <a name="use-the-unauthenticated-widget"></a>Usare il widget non autenticato
Per usare un modello non autenticato, incorporarlo direttamente nell'applicazione host in un iframe. Non è necessario un SDK JS o un token di accesso. 

### <a name="show-templates-for-your-scenarios"></a>Visualizzare i modelli per gli scenari
Per iniziare, aggiungere il codice seguente per visualizzare i modelli di Microsoft Flow nel sito Web:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

| Parametro | Descrizione |
| --- | --- |
| locale |Codice lingua e area geografica di quattro lettere per la visualizzazione del modello. Ad esempio, `en-us` rappresenta l'inglese americano e `de-de` rappresenta il tedesco. |
| search term |Il termine di ricerca per i modelli da includere nella visualizzazione. Ad esempio, cercare `wunderlist` per visualizzare i modelli per Wunderlist. |
| number of templates |Il numero di modelli da includere nella visualizzazione. |
| destination |La pagina visualizzata quando l'utente seleziona il modello. Immettere `details` per visualizzare i dettagli sul modello oppure immettere `new` per aprire la finestra di progettazione di Microsoft Flow. |
| parameters.{name} |Contesto aggiuntivo da passare al flusso. |
| templateCategory | Filtri per la categoria del modello specificato                     | 

Se il parametro di destinazione è `new`, la finestra di progettazione di Microsoft Flow viene aperta quando gli utenti selezionano un modello. Gli utenti possono quindi creare un flusso nella finestra di progettazione. Per l'esperienza completa del widget, vedere la sezione successiva.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Passaggio di parametri aggiuntivi al modello di flusso

Se l'utente è in un contesto specifico nel sito Web o nell'app, è possibile passare il contesto al flusso. Ad esempio, un utente può aprire un modello per ricevere *una notifica quando un elemento viene aggiunto a un elenco* durante la ricerca in un determinato elenco di Wunderlist. Per passare l'ID elenco come *parametro* al flusso, seguire questa procedura:

1. Definire il parametro nel modello di flusso prima della pubblicazione. Un parametro è simile a `@{parameters('parameter_name')}`.
1. Passare il parametro nell'attributo iframe src. Ad esempio, aggiungere `&parameters.listName={the name of the list}` se si ha un parametro denominato **listName**.

### <a name="full-sample"></a>Esempio completo

Per visualizzare i primi quattro modelli Wunderlist in tedesco e per consentire all'utente di iniziare a usare **myCoolList**, usare questo codice:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Usare i widget di Flow autenticati

La tabella seguente mostra l'elenco dei widget di Microsoft Flow che supportano l'esperienza completa all'interno del widget tramite il token di accesso dell'autenticazione utente. Sarà necessario usare il Software Developer Kit Javascript (SDK JS) di Microsoft Flow per incorporare i widget e fornire il token di accesso utente necessario.

| Tipo di widget    | Funzionalità supportata                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Flussi          | Visualizza un elenco dei flussi in una scheda per i flussi personali e condivisi. Modificare un flusso esistente o creare un nuovo flusso basato su un modello o vuoto. | 
| Creazione flussi   | Crea un flusso basato su un ID modello fornito dall'applicazione host.                                                                | 
| Runtime        | Attiva un flusso manuale o ibrido fornito dall'applicazione host.                                                        | 
| Centro approvazioni | Incorpora le richieste di approvazione e le approvazioni inviate.                                                                                        | 
| Modelli      | Visualizza un elenco di modelli. L'utente sceglie un modello per creare un nuovo flusso.                                                                         | 

Usare l'SDK di Flow autenticato per consentire agli utenti di creare e gestire flussi direttamente dal sito Web o dall'app senza passare a Microsoft Flow. Per usare l'SDK autenticato, l'utente dovrà accedere con l'account Microsoft o Azure Active Directory.

> [!NOTE]
> Non è possibile nascondere il branding di Microsoft Flow quando si usano i widget.

## <a name="widget-architecture"></a>Architettura dei widget

I widget di Microsoft Flow incorporano un iframe che fa riferimento a Microsoft Flow in un'applicazione host. L'host fornisce il token di accesso richiesto dal widget di Microsoft Flow. L'SDK JS di Microsoft Flow consente all'applicazione host di inizializzare e gestire il ciclo di vita del widget.

![architettura del widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Dettagli dell'SDK JS

Il team di Microsoft Flow fornisce l'SDK JS per facilitare l'integrazione dei widget di Flow nelle applicazioni di terze parti. L'SDK JS di Flow è disponibile come collegamento pubblico nel servizio Flow e consente all'applicazione host di gestire gli eventi dal widget e di interagire con l'applicazione Flow inviando azioni al widget. Gli eventi e le azioni dei widget sono specifiche del tipo di widget.

### <a name="widget-initialization"></a>Inizializzazione dei widget

Prima di inizializzare il widget è necessario aggiungere il riferimento all'SDK JS di Flow all'applicazione host.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Creare un'istanza dell'SDK JS passando il nome host facoltativo e i valori delle impostazioni locali in un oggetto JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US',
}); 
```

| Nome     | Obbligatorio/Facoltativo | Descrizione                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Facoltativo          | Nome host di Microsoft Flow, ad esempio https://flow.microsoft.com        | 
| `locale`   | Facoltativo          | Impostazioni locali del client per il widget (se il valore non viene passato, viene usato il valore predefinito `en-Us`) | 


Dopo aver creato l'istanza dell'SDK JS è possibile inizializzare e incorporare un widget di Microsoft Flow in un elemento padre nell'applicazione host. Per eseguire queste operazioni, aggiungere un tag div HTML:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Quindi inizializzare il widget di Microsoft Flow con il metodo renderWidget() dell'SDK JS. Assicurarsi di specificare il tipo di widget e le impostazioni corrispondenti.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flow-div',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {},
});
```

Di seguito è riportato uno stile di esempio per il contenitore che è possibile modificare per adattarlo alle dimensioni dell'applicazione host.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

Di seguito sono elencati i parametri per `renderWidget()`: 

| Parametro        | Obbligatorio/Facoltativo | Descrizione                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Obbligatorio          | ID di un elemento DIV nella pagina host in cui verrà incorporato il widget                      | 
| `environmentId`    | Facoltativo          | I widget richiedono un ID ambiente. Se non si specifica un ID, viene usato un ambiente predefinito. | 
| `flowsSettings`    | Facoltativo          | Oggetto delle impostazioni di Microsoft Flow                                                                        | 
| `templateSettings` | Facoltativo          | Oggetto delle impostazioni del modello                                                                    | 
| `approvalSettings` | Facoltativo          | Oggetto delle impostazioni dell'approvazione                                                                    | 

### <a name="access-tokens"></a>Token di accesso

Dopo l'esecuzione di `renderWidget()` dell'SDK JS, l'SDK JS inizializza un iframe che punta all'URL del widget di Microsoft Flow. Questo URL contiene tutte le impostazioni nei parametri della stringa di query. L'applicazione host deve ricevere un token di accesso di Microsoft Flow per l'utente (token JWT di Azure Active Directory con destinatari https://service.flow.microsoft.com) prima di inizializzare il widget. Il widget genera un evento `GET_ACCESS_TOKEN` per richiedere un token di accesso proveniente dall'host. L'host deve gestire l'evento e passare il token al widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

L'applicazione host è responsabile della gestione del token e del passaggio del token con una data di scadenza valida al widget quando necessario. Se il widget è aperto per lunghi periodi, l'host deve verificare se il token è scaduto e, se necessario, aggiornare il token prima di passarlo al widget.

### <a name="detecting-if-the-widget-is-ready"></a>Rilevare se il widget è pronto

Dopo l'inizializzazione, il widget genera un evento per notificare che il widget è pronto. L'host può rimanere in ascolto dell'evento `WIDGET_READY` ed eseguire qualsiasi codice host aggiuntivo.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Impostazioni del widget

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings consente di personalizzare la funzionalità del widget di Microsoft Flow.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parametro | Obbligatorio/Facoltativo | Descrizione | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Obbligatorio | Usare il GUID del modello quando l'utente seleziona il pulsante **Crea da zero** nel widget di Flow | 
| `flowsFilter` | Facoltativo | Il widget di Microsoft Flow applica il filtro specificato per la visualizzazione dei flussi. È possibile ad esempio visualizzare i flussi che fanno riferimento a un sito di SharePoint specifico. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Facoltativo | Imposta la scheda attiva predefinita visualizzata nel widget di Microsoft Flow. <br /> Ad esempio, <br /> ```tab:'sharedFlows' ``` visualizza la scheda Team<br /> e ``` tab:'myFlows' ``` visualizza la scheda Flussi personali. |   

### <a name="templatessettings"></a>TemplatesSettings 

Questa impostazione si applica a tutti i widget che consentono di creare flussi basati su un modello, inclusi i widget dei flussi, di creazione flussi e dei modelli.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Parametro |Obbligatorio/Facoltativo | Descrizione                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Facoltativo          | Parametri della fase di progettazione da usare durante la creazione di un flusso basato su un modello, ad esempio: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Facoltativo          | I valori validi sono 'new' o 'details'. Quando il parametro è impostato su 'details', viene visualizzata una pagina dei dettagli durante la creazione di un flusso basato su un modello.     |
| `pageSize` | Facoltativo          | Numero di modelli da visualizzare. Dimensione predefinita = 6 | 
| `searchTerm` | Facoltativo          | Visualizzare i modelli corrispondenti al termine di ricerca specificato| 
| `templateCategory` | Facoltativo          | Visualizzare i modelli di una categoria specifica| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Si applica ai widget del centro approvazioni.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Parametro | Obbligatorio/Facoltativo | Descrizione | 
|------------|-------------------|--------------| 
| `hideLink`| Facoltativo | Quando il parametro è impostato su `true`, il widget nasconde i collegamenti delle approvazioni ricevute e inviate | 
| `autoNavigateToDetails`| Facoltativo | Quando il parametro è impostato su `true`, il widget visualizza automaticamente i dettagli dell'approvazione quando è presente una sola approvazione | 
| `approvalsFilter`| Facoltativo | Il widget di approvazione applica il filtro di approvazione specificato durante la visualizzazione delle approvazioni, ad esempio:    Il widget di approvazione applica il filtro di approvazione specificato durante la visualizzazione delle approvazioni, ad esempio: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Facoltativo | Scheda attiva predefinita da visualizzare nel widget di Flow. <br/> Valori validi: 'receivedApprovals', 'sentApprovals' | 
| `showSimpleEmptyPage`| Facoltativo | Visualizza una pagina vuota quando non sono presenti approvazioni | 
| `hideInfoPaneCloseButton` | Facoltativo | Nasconde il pulsante Chiudi del riquadro informazioni (oppure nell'host è già presente un pulsante Chiudi) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Eventi del widget

Il widget di Microsoft Flow supporta gli eventi che consentono all'host di essere in ascolto degli eventi del ciclo di vita del widget. Il widget di Microsoft Flow supporta due tipi di eventi: eventi di notifica unidirezionale (ad esempio, Widget\_Ready) ed eventi generati dal widget per recuperare i dati dall'host (Get\_Access\_Token). L'host deve usare il metodo widget.listen() per essere in ascolto di determinati eventi generati dal widget.

### <a name="usage"></a>Uso

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Eventi supportati dal tipo di widget

| Evento del widget      | Dettagli                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Il caricamento del widget è stato completato                                      | 
| `WIDGET_RENDERED`   | Il widget è stato caricato e il rendering dell'interfaccia utente è stato completato                      | 
| `GET_ACCESS_TOKEN`  | Richiesta del widget di un token di accesso utente incorporato                      | 
| `GET_STRINGS`       | Consente all'host di eseguire l'override di un set di stringhe dell'interfaccia utente visualizzate nel widget | 

### <a name="runtime-widget"></a>Widget di runtime

| Evento del widget                    | Dettagli                                     | Dati                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Attivato ed è stata avviata l'esecuzione del flusso      |           | 
| `RUN_FLOW_COMPLETED`              | L'esecuzione del flusso è stata attivata             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | L'utente ha selezionato il pulsante Fine nell'esecuzione del flusso       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | L'utente ha selezionato il pulsante Annulla nell'esecuzione del flusso     |           | 
| `FLOW_CREATION_SUCCEEDED`         | Il flusso è stato creato           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Attivato quando l'host deve chiudere il widget |       | 

### <a name="flow-creation-widget"></a>Widget di creazione flussi

| Evento del widget             | Dettagli                                  | Dati  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | La creazione del flusso non è riuscita                     |       | 
| `WIDGET_CLOSE`             | Attivato quando l'host deve chiudere il widget  |       | 
| `TEMPLATE_LOAD_FAILED`     | Non è stato possibile caricare il modello              |       | 
| `FLOW_CREATION_SUCCEEDED`  | Il flusso è stato creato        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget di approvazione

| Evento del widget                      | Dettagli                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Stato di approvazione ricevuta modificato  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Stato di approvazione inviata modificato      | 

L'evento **GET\_STRINGS** consente di personalizzare il testo per alcuni elementi dell'interfaccia utente visualizzati nel widget. È possibile personalizzare le stringhe seguenti:

| Chiave della stringa                     | Uso nel widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Testo visualizzato sul pulsante Crea flusso nel widget di creazione flussi e nel widget di runtime                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | Il valore iniziale da usare per il nome del flusso nel widget di creazione del flusso. Usata solo quando è abilitata l'impostazione allowCustomFlowName. | 
| `FLOW_CREATION_HEADER`           | Intestazione da usare durante la creazione di un flusso nel widget di creazione flussi e nel widget di runtime                                                    | 
| `INVOKE_FLOW_HEADER`             | Intestazione da usare quando si richiama un flusso nel widget di runtime                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Testo visualizzato sul pulsante usato per richiamare o eseguire un flusso nel widget di runtime                                                       | 

### <a name="example"></a>Esempio

Chiamare `widgetDoneCallback` passando un oggetto JSON con coppie chiave-valore della chiave della stringa e un testo per sostituire il valore predefinito.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Azioni del widget

L'host usa le azioni del widget per inviare un'azione o un messaggio specifico al widget. L'SDK JS del widget fornisce il metodo `notify()` per inviare un messaggio o un payload JSON al widget. Ogni azione del widget supporta una firma di payload specifica.

### <a name="usage"></a>Uso

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Esempio 

Richiamare un flusso inviando il comando seguente a un widget di runtime 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Widget di runtime

| Azione del widget                               | Dettagli                                                      | Interfaccia del parametro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Attiva l'esecuzione di un flusso                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Attiva l'esecuzione di un flusso in base al modello                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Ottiene lo schema di trigger di un flusso                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Annulla le attività in sospeso e genera un evento WIDGET_CLOSE |                      | 

### <a name="flow-creation-widget"></a>Widget di creazione flussi

| Azione del widget                               | Dettagli                                                      | Interfaccia del parametro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Crea un flusso per il modello selezionato                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Crea un flusso per la definizione di modello selezionata          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Annulla le attività in sospeso e genera un evento WIDGET_CLOSE |                      | 

### <a name="approval-widget"></a>Widget di approvazione

| Azione del widget  | Dettagli                                           | Interfaccia del parametro  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Chiude il riquadro informazioni in cui sono visualizzati i dettagli dell'approvazione  | N/D                  | 

## <a name="configuring-your-client-application"></a>Configurazione dell'applicazione client

È necessario configurare l'applicazione client con gli ambiti di servizio di Flow (autorizzazioni delegate). Se l'app di Azure Active Directory (AAD) usata per l'integrazione del widget usa un flusso di autorizzazione 'concessione del codice', l'app AAD deve essere preconfigurata con le autorizzazioni delegate supportate da Microsoft Flow. In questo modo vengono concesse le autorizzazioni delegate che consentono all'applicazione di:

-   Gestire le approvazioni
-   Leggere le approvazioni
-   Leggere le attività
-   Gestire i flussi
-   Leggere i flussi

Per selezionare una o più autorizzazioni delegate, seguire questa procedura:

1.  Passare a https://portal.azure.com 
2.  Selezionare **Azure Active Directory**.
3.  Selezionare **Registrazioni app** in **Gestisci**.
4.  Specificare l'applicazione di terze parti da configurare per gli ambiti di servizio di Flow.
5.  Selezionare **Impostazioni**.
      ![architettura del widget](../media/embed-flow-dev/AAD-App-Settings.png)
6. Selezionare **Autorizzazioni necessarie** in **Accesso all'API**/
7. Selezionare **Aggiungi**.
8. Scegliere **Selezionare un'API**.
      ![architettura del widget](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Cercare **Servizio Microsoft Flow** e selezionarla. Nota: per poter visualizzare Servizio Microsoft Flow, è necessario che il tenant abbia almeno un utente AAD che ha eseguito l'accesso al portale di Flow (<https://flow.microsoft.com>)
10. Scegliere gli ambiti di Flow necessari per l'applicazione e quindi selezionare **Salva**.
      ![architettura del widget](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

L'applicazione otterrà un token del servizio Flow che contiene le autorizzazioni delegate nell'attestazione \'scp' nel token JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Applicazione di esempio con incorporamento di widget di Flow 

Nella sezione delle risorse è disponibile un'applicazione a pagina singola JavaScript di esempio che è possibile usare per provare a incorporare widget di Flow in una pagina host. Per usare l'applicazione di esempio è necessario registrare un'applicazione AAD con il flusso di concessione implicita abilitato.

### <a name="registering-an-aad-app"></a>Registrazione di un'app AAD

1.  Accedere al [portale di Azure](https://portal.azure.com/).
2.  Nel riquadro di spostamento a sinistra selezionare **Azure Active Directory**, quindi **Registrazioni app** (anteprima) \> Nuova registrazione.
3.  Quando viene visualizzata la pagina **Registra un'applicazione**, immettere un nome per l'applicazione.
4.  In **Tipi di account supportati** selezionare **Account** in una directory dell'organizzazione.
5.  Nella sezione **URL di reindirizzamento** selezionare la piattaforma Web e impostare il valore sull'URL dell'applicazione in base al server Web.  Impostare questo valore su http://localhost:30662/ per eseguire l'app di esempio.
6.  Selezionare **Registra**.
7.  Nella pagina **Panoramica** dell'app prendere nota del valore di ID applicazione (client).
8.  Per l'esempio è necessario abilitare il [flusso di concessione implicita](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow). Nel riquadro di spostamento di sinistra dell'applicazione registrata selezionare **Autenticazione**.
9.  In **Impostazioni avanzate** in **Concessione implicita** selezionare le caselle di controllo **Token ID** e **Token di accesso**. Token ID e token di accesso devono essere specificati poiché l'app esegue l'accesso degli utenti e chiama l'API di Flow.
10. Selezionare **Salva**.

### <a name="running-the-sample"></a>Esecuzione dell'esempio
<!-- todo where should I download from? -->
<!-- todo is this a misspelling: applicaionConfig -->
1.  Scaricare l'esempio e copiarlo in una cartella locale nel dispositivo.
2.  Aprire il file index.htmlnella cartella FlowSDKSample e modificare `applicaionConfig` per aggiornare `clientID` all'ID applicazione registrato in precedenza.
    ![architettura del widget](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  L'app di esempio è configurata per l'uso degli ambiti di Flow **Flows.Read.All** e **Flow.Manage.All.** È possibile configurare altri ambiti aggiornando la proprietà **flowScopes** nell'oggetto **applicationConfig**.
4.  Eseguire questi comandi per installare la dipendenza ed eseguire l'app di esempio:
    > \> npm install \> node server.js
5. Aprire il browser e immettere http://localhost:30662
6. Selezionare il pulsante **Accedi** per eseguire l'autenticazione in AAD e acquisire un token di accesso del flusso.
7. La casella di testo **Token di accesso** contiene il token di accesso.
    ![architettura del widget](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Selezionare il **widget di caricamento flussi** o il **widget di caricamento modelli** per incorporare i widget corrispondenti.
    ![architettura del widget](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

[Collegamento per il download](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip) dell'applicazione di esempio.

## <a name="resources"></a>Risorse

### <a name="widget-test-pages"></a>Pagine di test dei widget

Sono disponibili altre informazioni sull'integrazione e sulle impostazioni dei widget:

- Widget di modelli: <[https://flow.microsoft.com/en-us/test/templateswidget/](https://flow.microsoft.com/en-us/test/templateswidget/)>
- Widget di creazione flussi: <[https://flow.microsoft.com/en-us/test/flowcreationwidget/](https://flow.microsoft.com/en-us/test/flowcreationwidget/)>
- Widget di runtime: <[https://flow.microsoft.com/en-us/test/runtimewidget/](https://flow.microsoft.com/en-us/test/runtimewidget/)>
- Widget del centro approvazioni: <[https://flow.microsoft.com/en-us/test/approvalcenterwidget/](https://flow.microsoft.com/en-us/test/approvalcenterwidget/)>
- Widget dei flussi: <[https://flow.microsoft.com/en-us/test/managewidget/](https://flow.microsoft.com/en-us/test/managewidget/)>

### <a name="supported-widget-locales"></a>Impostazioni locali dei widget supportate

Se le impostazioni locali inizializzate non sono elencate, Flow usa per impostazione predefinita le impostazioni locali supportate più vicine.

| Impostazioni locali     | Lingua                   | 
|------------|----------------------------| 
| bg-bg      | Bulgaro (Bulgaria)       | 
| ca-es      | Catalano (Spagna)            | 
| cs-cz      | Ceco (Repubblica Ceca)     | 
| da-dk      | Danese (Danimarca)           | 
| de-de      | Tedesco (Germania)           | 
| el-gr      | Greco (Grecia)             | 
| en-Us      | Inglese (Stati Uniti)    | 
| es-es      | Spagnolo (castigliano)        | 
| et-ee      | Estone (Estonia)         | 
| eu-es      | Basco (Spagna)             | 
| fi-fi      | Finlandese (Finlandia)          | 
| fr-fr      | Francese (Francia)            | 
| gl-es      | Galiziano (Spagna)           | 
| hi-HU      | Ungherese (Ungheria)        | 
| hi-in      | Hindi (India)              | 
| hr-hr      | Croato (Croazia)         | 
| id-Id      | Indonesiano (Indonesia)     | 
| it-It      | Italiano (Italia)            | 
| jp-Jp      | Giapponese (Giappone)           | 
| kk-kz      | Kazako (Kazakhstan)        | 
| ko-kr      | Coreano (Corea)             | 
| lt-LT      | Lituano (Lituania)     | 
| lv-lv      | Lettone (Lettonia)           | 
| ms-my      | Malese (Malaysia)           | 
| nb-no      | Norvegese (Bokmål)         | 
| nl-nl      | Olandese (Paesi Bassi)        | 
| pl-pl      | Polacco (Polonia)            | 
| pt-br      | Portoghese (Brasile)        | 
| pt-pt      | Portoghese (Portogallo)      | 
| ro-ro      | Rumeno (Romania)         | 
| ru-ru      | Russo (Russia)           | 
| sk-sk      | Slovacco (Slovacchia)          | 
| sl-si      | Sloveno (Slovenia)       | 
| sr-cyrl-rs | Serbo (alfabeto cirillico, Serbia) | 
| sr-latn-rs | Serbo (alfabeto latino, Serbia)    | 
| sv-se      | Svedese (Svezia)           | 
| th-th      | Thai (Thailandia)            | 
| tr-tr      | Turco (Turchia)           | 
| uk-ua      | Ucraino (Ucraina)        | 
| vi-vn      | Vietnamita (Vietnam)      |
