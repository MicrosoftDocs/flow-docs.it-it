---
title: Integrare Microsoft Flow con siti Web e app | Microsoft Docs
description: Incorporare le esperienze di Microsoft Flow nel sito Web o nell'app.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: cf2f14826670cf221411fa2204ee9b2c5581222e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547720"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Integra Microsoft Flow con siti Web e app
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Incorporare Microsoft Flow nell'app o nel sito Web usando i *widget Flow* per offrire agli utenti un modo semplice per automatizzare le attività personali o professionali.

I widget Flow sono iframe che si trovano in un documento host. Questo documento fa riferimento a una pagina nella finestra di progettazione Microsoft Flow. Questi widget integrano funzionalità di Microsoft Flow specifiche nell'applicazione di terze parti.

I widget possono essere semplici. Ad esempio, un widget che esegue il rendering di un elenco di modelli senza comunicazione tra l'host e iframe. I widget possono anche essere complessi. Ad esempio, un widget che effettua il provisioning di un flusso da un modello e quindi attiva il flusso tramite la comunicazione bidirezionale tra l'host e il widget.

## <a name="prerequisites"></a>Prerequisiti

- Un **account Microsoft** o
- Un account aziendale o dell'Istituto di istruzione

## <a name="use-the-unauthenticated-widget"></a>Usare il widget non autenticato
Per usare il widget modelli non autenticati, incorporarlo direttamente nell'applicazione host usando un iframe. Non è necessario JS SDK o un token di accesso. 

### <a name="show-templates-for-your-scenarios"></a>Mostra i modelli per gli scenari
Per iniziare, aggiungere il codice seguente per visualizzare i modelli di Microsoft Flow nel sito Web:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| Parametro | Descrizione |
| --- | --- |
| locale |Il codice della lingua e dell'area di quattro lettere per la visualizzazione modello. Ad esempio, `en-us` rappresenta l'inglese americano e `de-de` rappresenta il tedesco. |
| termine di ricerca |Termine di ricerca per i modelli che si desidera visualizzare nella visualizzazione. Ad esempio, cercare `wunderlist` per visualizzare i modelli per Wunderlist. |
| numero di modelli |Il numero di modelli che si desidera visualizzare nella visualizzazione. |
| Destinazione |Pagina che viene visualizzata quando gli utenti selezionano il modello. Immettere `details` per visualizzare i dettagli sul modello oppure immettere `new` per aprire la finestra di progettazione Microsoft Flow. |
| Categoria |Filtra alla categoria del modello specificata. | 
| parametri. nome |Contesto aggiuntivo da passare al flusso. |


Se il parametro di destinazione è `new`, viene visualizzata la finestra di progettazione Microsoft Flow quando gli utenti selezionano un modello. Gli utenti possono quindi creare un flusso nella finestra di progettazione. Vedere la sezione successiva se si vuole avere un'esperienza completa dal widget.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Passaggio di parametri aggiuntivi al modello di flusso

Se l'utente si trova in un contesto specifico nel sito Web o nell'app, potrebbe essere necessario passare il contesto al flusso. Ad esempio, un utente potrebbe aprire un modello per ricevere una *notifica quando un elemento viene aggiunto a un elenco* osservando un determinato elenco in Wunderlist. Seguire questa procedura per passare l'ID elenco come *parametro* al flusso:

1. Definire il parametro nel modello di flusso prima di pubblicarlo. Un parametro ha un aspetto simile a `@{parameters('parameter_name')}`.
1. Passare il parametro nella stringa di query dell'iframe src. Ad esempio, aggiungere `&parameters.listName={the name of the list}` se si dispone di un parametro denominato **listname**.

### <a name="full-sample"></a>Esempio completo

Per visualizzare i primi quattro modelli di Wunderlist in tedesco e per avviare l'utente con l'oggetto **Filecooling**, usare il codice seguente:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Usare i widget di flusso autenticato

La tabella seguente mostra l'elenco dei widget di Microsoft Flow che supportano l'esperienza completa all'interno del widget usando il token di accesso per l'autenticazione utente. Per incorporare i widget e fornire il token di accesso utente necessario, è necessario usare Microsoft Flow JavaScript Software Developer Kit (JS SDK).

| Tipo di widget    | Funzionalità supportata                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Flussi          | Mostra un elenco di flussi in una scheda per i flussi personali e condivisi. Modificare un flusso esistente o creare un nuovo flusso da un modello o da un campo vuoto. | 
| flowCreation   | Crea un flusso da un ID modello fornito dall'applicazione host.                                                                | 
| Runtime        | Attiva un flusso di trigger manuale o ibrido fornito dall'applicazione host.                                                        | 
| approvalCenter | Incorpora le richieste di approvazione e le approvazioni inviate.                                                                                        | 
| Modelli      | Mostra un elenco di modelli. L'utente sceglie uno per creare un nuovo flusso.                                                                         | 

Usare Authenticated Flow SDK per consentire agli utenti di creare e gestire i flussi direttamente dal sito Web o dall'app, anziché passare a Microsoft Flow. È necessario accedere all'utente con il proprio account Microsoft o Azure Active Directory per usare l'SDK autenticato.

> [!NOTE]
> Non è possibile nascondere la personalizzazione del Microsoft Flow quando si usano i widget.

## <a name="widget-architecture"></a>architettura widget

Microsoft Flow widget funzionano incorporando un iframe che fa riferimento a Microsoft Flow in un'applicazione host. L'host fornisce il token di accesso richiesto dal widget Microsoft Flow. Microsoft Flow JS SDK consente all'applicazione host di inizializzare e gestire il ciclo di vita dei widget.

![architettura widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Dettagli SDK JS

Il team di Microsoft Flow fornisce JS SDK per semplificare l'integrazione di widget di Flow in applicazioni di terze parti. Flow JS SDK è disponibile come collegamento pubblico nel servizio Microsoft Flow e consente all'applicazione host di gestire gli eventi dal widget e interagire con l'applicazione Microsoft Flow inviando azioni al widget. Gli eventi e le azioni del widget sono specifici del tipo di widget.

### <a name="widget-initialization"></a>Inizializzazione widget

Il riferimento a Flow JS SDK deve essere aggiunto all'applicazione host prima di inizializzare il widget.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Creare un'istanza di JS SDK passando i valori del nome host e delle impostazioni locali facoltativi in un oggetto JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Nome     | Obbligatorio/facoltativo | Descrizione                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Opzionale          | Microsoft Flow nome host, ad esempio https://flow.microsoft.com        | 
| `locale`   | Opzionale          | Impostazioni locali del client per il widget (il valore predefinito è `en-Us` se non è specificato) | 


Una volta creata l'istanza di JS SDK, è possibile inizializzare e incorporare un Microsoft Flow widget in un elemento padre nell'applicazione host. A tale scopo, aggiungere un elemento div HTML:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Quindi, inizializzare il widget Microsoft Flow con il metodo `renderWidget()` JS SDK. Assicurarsi di specificare il tipo di widget e le impostazioni corrispondenti.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Ecco uno stile di esempio per il contenitore che è possibile modificare per trovare la corrispondenza con le dimensioni dell'applicazione host.

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

Questi sono i parametri per `renderWidget()`: 

| Parametro        | Obbligatorio/facoltativo | Descrizione                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Obbligatorio          | ID di un elemento DIV nella pagina host in cui verrà incorporato il widget.                   | 
| `environmentId`    | Opzionale          | I widget richiedono un ID ambiente. Se non si specifica un ID, viene usato un ambiente predefinito. | 
| `flowsSettings`    | Opzionale          | Oggetto impostazioni Microsoft Flow                                                                        | 
| `templateSettings` | Opzionale          | Oggetto impostazioni modello                                                                    | 
| `approvalSettings` | Opzionale          | Oggetto impostazioni di approvazione                                                                    | 

### <a name="access-tokens"></a>Token di accesso

Dopo l'esecuzione del `renderWidget()` JS SDK, JS SDK Inizializza un iframe che punta all'URL del widget Microsoft Flow. Questo URL contiene tutte le impostazioni nei parametri della stringa di query. L'applicazione host deve ottenere un token di accesso Microsoft Flow per l'utente (Azure Active Directory token JWT con audience https://service.flow.microsoft.com) prima di inizializzare il widget. Il widget genera un evento `GET_ACCESS_TOKEN` per richiedere un token di accesso dall'host. L'host deve gestire l'evento e passare il token al widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

L'applicazione host è responsabile della gestione del token e del passaggio con una data di scadenza valida al widget quando richiesto. Se il widget è aperto per periodi più lunghi, l'host deve verificare se il token è scaduto e aggiornare il token se necessario prima di passarlo al widget.

### <a name="detecting-if-the-widget-is-ready"></a>Rilevamento se il widget è pronto

Una volta completata l'inizializzazione, il widget genera un evento per notificare che il widget è pronto. L'host può restare in ascolto dell'evento `WIDGET_READY` ed eseguire qualsiasi altro codice host.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Impostazioni widget

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings può essere usato per personalizzare le funzionalità del widget Microsoft Flow.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parametro | Obbligatorio/facoltativo | Descrizione | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Obbligatorio | Usare il GUID del modello quando l'utente seleziona il pulsante **Crea da zero** nel widget Flow | 
| `flowsFilter` | Opzionale | Il widget Microsoft Flow applica il filtro fornito quando si elencano i flussi. Ad esempio, Mostra flussi che fanno riferimento a un sito di SharePoint specifico. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Opzionale | Imposta come predefinito la scheda attiva da visualizzare nel widget Microsoft Flow. <br /> Per esempio <br /> ```tab:'sharedFlows' ``` Visualizza la scheda Team<br /> e ``` tab:'myFlows' ``` Visualizza la scheda flussi personali. |   

### <a name="templatessettings"></a>TemplatesSettings 

Questo vale per tutti i widget che consentono di creare flussi da un modello, inclusi i widget Flows, FlowCreation e Templates.

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

| Parametro |Obbligatorio/facoltativo | Descrizione                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Opzionale          | Parametri della fase di progettazione da usare durante la creazione di un flusso da un modello, ad esempio: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Opzionale          | I valori validi sono ' New ' o ' details '. Quando è impostato su' details ', viene visualizzata una pagina di dettaglio durante la creazione di un flusso da un modello.     |
| `pageSize` | Opzionale          | Numero di modelli da visualizzare. Dimensioni predefinite = 6 | 
| `searchTerm` | Opzionale          | Visualizza i modelli che corrispondono al termine di ricerca specificato| 
| `templateCategory` | Opzionale          | Visualizzare i modelli in una categoria specifica| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Si applica ai widget ApprovalCenter.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Parametro | Obbligatorio/facoltativo | Descrizione | 
|------------|-------------------|--------------| 
| `hideLink`| Opzionale | Quando è impostato su `true`, il widget nasconde i collegamenti ricevuti e di approvazione inviati | 
| `autoNavigateToDetails`| Opzionale | Quando è impostato su `true`, il widget apre automaticamente i dettagli di approvazione quando esiste una sola approvazione | 
| `approvalsFilter`| Opzionale | Il widget di approvazione applicherà il filtro di approvazione specificato quando si elencano le approvazioni, ad esempio: il widget di approvazione applicherà il filtro di approvazione specificato quando si elencano le approvazioni, ad esempio: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Opzionale | Scheda attiva predefinita da visualizzare nel widget Flow. <br/> Valori validi:' receivedApprovals ',' sentApprovals ' | 
| `showSimpleEmptyPage`| Opzionale | Mostra una pagina vuota se non sono presenti approvazioni | 
| `hideInfoPaneCloseButton` | Opzionale | Nasconde il pulsante di chiusura del riquadro informazioni (o l'host ha già un pulsante Chiudi) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Eventi widget

Il widget Microsoft Flow supporta gli eventi che consentono all'host di restare in ascolto degli eventi del ciclo di vita dei widget. Il widget Microsoft Flow supporta due tipi di eventi: eventi di notifica unidirezionali (ad esempio, widget\_Ready) ed eventi generati dal widget per recuperare i dati dall'host (Get\_Access\_token). L'host deve usare il metodo widget. Listen () per ascoltare eventi specifici generati dal widget.

### <a name="usage"></a>Utilizzo

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Eventi supportati per tipo di widget

| Evento widget      | Dettagli                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Caricamento del widget completato                                      | 
| `WIDGET_RENDERED`   | Widget caricato e rendering dell'interfaccia utente completato                      | 
| `GET_ACCESS_TOKEN`  | Richiesta widget per incorporare il token di accesso utente                      | 
| `GET_STRINGS`       | Consente all'host di eseguire l'override di un set di stringhe dell'interfaccia utente visualizzate nel widget | 

### <a name="runtime-widget"></a>Widget di runtime

| Evento widget                    | Dettagli                                     | Dati                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Attivata e l'esecuzione del flusso è stata avviata      |           | 
| `RUN_FLOW_COMPLETED`              | L'esecuzione del flusso è stata attivata             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Pulsante operazione selezionata dall'utente nell'esecuzione del flusso       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Pulsante Annulla selezionato dall'utente nell'esecuzione del flusso     |           | 
| `FLOW_CREATION_SUCCEEDED`         | Il flusso è stato creato correttamente           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Generato quando l'host chiude il widget |       | 

### <a name="flow-creation-widget"></a>Widget per la creazione di flussi

| Evento widget             | Dettagli                                  | Dati  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Creazione del flusso non riuscita                     |       | 
| `WIDGET_CLOSE`             | Generato quando l'host chiude il widget  |       | 
| `TEMPLATE_LOAD_FAILED`     | Non è stato possibile caricare il modello              |       | 
| `FLOW_CREATION_SUCCEEDED`  | Il flusso è stato creato correttamente        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget approvazione

| Evento widget                      | Dettagli                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Stato approvazione ricevuta modificato  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Stato di approvazione inviato modificato      | 

L'evento **GET\_Strings** consente di personalizzare il testo per alcuni degli elementi dell'interfaccia utente mostrati nel widget. È possibile personalizzare le stringhe seguenti:

| Chiave di stringa                     | Usare nel widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Testo visualizzato sul pulsante Crea flusso in entrambi i widget di creazione del flusso e Runtime                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | Valore iniziale da usare per il nome del flusso nel widget per la creazione del flusso. Usato solo quando è abilitata l'impostazione allowCustomFlowName. | 
| `FLOW_CREATION_HEADER`           | Intestazione da usare quando si crea un flusso sia nella creazione del flusso che nel widget di runtime                                                    | 
| `INVOKE_FLOW_HEADER`             | Intestazione da usare quando si richiama un flusso nel widget di runtime                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Testo visualizzato sul pulsante usato per richiamare/eseguire un flusso nel widget di runtime                                                       | 

### <a name="example"></a>Esempio

Chiamare `widgetDoneCallback` passando un oggetto JSON con coppie chiave-valore della chiave di stringa e del testo per eseguire l'override del valore predefinito.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Azioni widget

L'host usa le azioni widget per inviare un'azione o un messaggio specifico al widget. Widget JS SDK fornisce il metodo `notify()` per inviare un messaggio o un payload JSON al widget. Ogni azione widget supporta una firma del payload specifica.

### <a name="usage"></a>Utilizzo

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

| Azione widget                               | Dettagli                                                      | Interfaccia parametro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Attiva un'esecuzione del flusso                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Attiva un'esecuzione del flusso in base al modello                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Ottiene lo schema del trigger per un flusso                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Annulla tutte le attività in sospeso e genera un evento WIDGET_CLOSE |                      | 

### <a name="flow-creation-widget"></a>Widget per la creazione di flussi

| Azione widget                               | Dettagli                                                      | Interfaccia parametro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Crea un flusso per il modello selezionato                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Crea un flusso per la definizione di modello selezionata          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Annulla tutte le attività in sospeso e genera un evento WIDGET_CLOSE |                      | 

### <a name="approval-widget"></a>Widget approvazione

| Azione widget  | Dettagli                                           | Interfaccia parametro  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Chiude il riquadro informazioni che Visualizza i dettagli dell'approvazione  | N/A                  | 

## <a name="configuring-your-client-application"></a>Configurazione dell'applicazione client

Sarà necessario configurare l'applicazione client con gli ambiti del servizio Flow (autorizzazioni delegate). Se l'app Azure Active Directory (AAD) usata per l'integrazione del widget usa un flusso di autorizzazione di concessione del codice, l'app AAD deve essere preconfigurata con autorizzazioni delegate supportate da Microsoft Flow. Fornisce le autorizzazioni delegate che consentono all'applicazione:

-   Gestisci approvazioni
-   Leggi approvazioni
-   Attività di lettura
-   Gestisci flussi
-   Lettura flussi

Per selezionare una o più autorizzazioni delegate, attenersi alla procedura seguente:

1.  Vai a https://portal.azure.com 
2.  Selezionare **Azure Active Directory**.
3.  Selezionare **registrazioni app** in **Gestisci**.
4.  Immettere l'applicazione di terze parti da configurare per gli ambiti del servizio Flow.
5.  Selezionare **Impostazioni**.
      architettura del widget ![](../media/embed-flow-dev/AAD-App-Settings.png)
6. Selezionare le **autorizzazioni necessarie** in **accesso all'API**/
7. Selezionare **Aggiungi**.
8. Scegliere **selezionare un'API**.
      architettura del widget ![](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Cercare **Microsoft Flow servizio** e selezionarlo. Nota: prima di poter visualizzare Microsoft Flow servizio, il tenant deve avere almeno un utente AAD connesso al portale di Flow (<https://flow.microsoft.com>)
10. Scegliere gli ambiti di flusso necessari per l'applicazione e quindi selezionare **Salva**.
      architettura del widget ![](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

L'applicazione otterrà ora un token del servizio Flow che contiene autorizzazioni delegate nell'attestazione \'SCP ' nel token JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Widget di flusso di incorporamento dell'applicazione di esempio 

Nella sezione risorse è disponibile un'applicazione a pagina singola JavaScript di esempio, che consente di provare a incorporare i widget di Flow in una pagina host. Per usare l'applicazione di esempio, è necessario registrare un'applicazione AAD con il flusso di concessione implicito abilitato.

### <a name="registering-an-aad-app"></a>Registrazione di un'app AAD

1.  Accedere al [portale di Azure](https://portal.azure.com/).
2.  Nel riquadro di spostamento a sinistra selezionare **Azure Active Directory**, quindi selezionare **registrazioni app** (anteprima) \> nuova registrazione.
3.  Quando viene visualizzata la pagina **registra un'applicazione** , immettere un nome per l'applicazione.
4.  In **tipi di account supportati**selezionare **account** in qualsiasi directory dell'organizzazione.
5.  Nella sezione **URL di reindirizzamento** selezionare la piattaforma Web e impostare il valore sull'URL dell'applicazione\'s basato sul server Web.  Configurare questo valore per http://localhost:30662/ per eseguire l'app di esempio.
6.  Selezionare **registra**.
7.  Nella pagina **Panoramica** dell'app prendere nota del valore di ID applicazione (client).
8.  Per l'esempio è necessario che sia abilitato il [flusso di concessione implicito](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) . Nel riquadro di spostamento a sinistra dell'applicazione registrata selezionare **Authentication (autenticazione**).
9.  In **Impostazioni avanzate**, in **concessione implicita**, abilitare le caselle di controllo **token ID** e **token di accesso** . I token ID e i token di accesso sono necessari perché questa app deve eseguire l'accesso agli utenti e all'API del flusso di chiamate.
10. Selezionare **Salva**.

### <a name="running-the-sample"></a>Esecuzione dell'esempio
<!-- todo where should I download from? -->
1.  Scaricare l'esempio e copiarlo in una cartella locale del dispositivo.
2.  Aprire il file index. html nella cartella FlowSDKSample e modificare il `applicationConfig` per aggiornare l'`clientID` all'ID applicazione registrato in precedenza.
    architettura del widget ![](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  L'app di esempio è configurata per usare gli ambiti di flusso Flows **. Read. All** e **Flow. Manage. all.** È possibile configurare gli ambiti aggiuntivi aggiornando la proprietà **flowScopes** nell'oggetto **applicationConfig** .
4.  Eseguire questi comandi per installare la dipendenza ed eseguire l'app di esempio:
    > \> NPM install \> node server. js
5. Aprire il browser e quindi immettere http://localhost:30662
6. Selezionare il pulsante **Sign in (accedi** ) per eseguire l'autenticazione ad Aad e acquisire un token di accesso Flow.
7. La casella di testo **token di accesso** contiene il token di accesso.
    architettura del widget ![](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Selezionare il widget **Load Flows** o **Load templates widget** per incorporare i widget corrispondenti.
    architettura del widget ![](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

Collegamento di [download](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip)dell'applicazione di esempio.

## <a name="resources"></a>Risorse

### <a name="widget-test-pages"></a>Pagine di test del widget

Altre informazioni sull'integrazione e le impostazioni dei widget:

- Widget modelli: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- Widget FlowCreation: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Widget di runtime: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Widget del Centro approvazioni: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Widget Flows: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Impostazioni locali widget supportate

Se le impostazioni locali inizializzate non sono elencate, il flusso utilizzerà per impostazione predefinita le impostazioni locali più vicine supportate.

| locale     | linguaggio                   | 
|------------|----------------------------| 
| BG-BG      | Bulgaro (Bulgaria)       | 
| ca-es      | Catalano (Spagna)            | 
| CS-CZ      | Ceco (Repubblica Ceca)     | 
| da-dk      | Danese (Danimarca)           | 
| De-de      | Tedesco (Germania)           | 
| El-gr      | Greco (Grecia)             | 
| it-it      | Inglese (Stati Uniti)    | 
| Es-es      | Spagnolo (castigliano)        | 
| EE      | Estone (Estonia)         | 
| eu-es      | Basco (Spagna)             | 
| Fi-Fi      | Finlandese (Finlandia)          | 
| Fr-FR      | Francese (Francia)            | 
| GL-ES      | Galiziano (Spagna)           | 
| Salve-HU      | Ungherese (Ungheria)        | 
| Hi-in      | Hindi (India)              | 
| HR-HR      | Croato (Croazia)         | 
| ID ID      | Indonesiano (Indonesia)     | 
| it      | Italiano (Italia)            | 
| jp-jp      | Giapponese (Giappone)           | 
| kk-KZ      | Kazako (Kazakistan)        | 
| Ko-KR      | Coreano (Corea)             | 
| lt-LT      | Lituano (Lituania)     | 
| LV-LV      | Lettone (Lettonia)           | 
| MS-My      | Malese (Malaysia)           | 
| NB-No      | Norvegese (Bokmål)         | 
| nl-nl      | Olandese (Paesi Bassi)        | 
| Pl-pl      | Polacco (Polonia)            | 
| PT-BR      | Portoghese (Brasile)        | 
| PT-PT      | Portoghese (Portogallo)      | 
| ro-ro      | Rumeno (Romania)         | 
| Ru-ur      | Russo (Russia)           | 
| SK-SK      | Slovacco (Slovacchia)          | 
| SL-si      | Sloveno (Slovenia)       | 
| Sr-Cyrl-RS | Serbo (alfabeto cirillico, Serbia) | 
| Sr-Latn-RS | Serbo (alfabeto latino, Serbia)    | 
| SV-se      | Svedese (Svezia)           | 
| th-TH      | Thai (Tailandia)            | 
| TR-TR      | Turco (Turchia)           | 
| Regno Unito-ua      | Ucraino (Ucraina)        | 
| vi-VN      | Vietnamita (Vietnam)      |
