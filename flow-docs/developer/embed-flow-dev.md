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
ms.date: 05/09/2017
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 738e566a9b064231a3bc2fe8bf7317df2bafbfef
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462810"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Integrare Microsoft Flow con siti Web e app
Incorporare Microsoft Flow direttamente dall'app o dal sito Web per concedere agli utenti un modo semplice per automatizzare le attività personali o professionali.

Per creare flussi, gli utenti dovranno avere un **Account Microsoft** o un account aziendale o dell'istituto di istruzione in **Azure Active Directory**. Microsoft Flow non supporta, ad esempio, una soluzione "white label" che supporti qualsiasi identità usata dal sistema (a meno che non usi già gli account Microsoft o AAD).

## <a name="prerequisites"></a>Prerequisiti
* [Compilare un connettore personalizzato](register-custom-api.md) che connetta il servizio a Microsoft Flow.
* [Creare e pubblicare uno o più modelli](../publish-a-template.md) che usano l'API.

## <a name="show-templates-for-your-scenarios"></a>Visualizzare i modelli per gli scenari
Per iniziare, aggiungere il codice seguente per visualizzare i modelli di flusso direttamente nel sito Web:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**Nota**: è stata aggiunta un'interruzione di riga in modo che il codice sia visualizzato meglio nella pagina.

| Parametro | Descrizione |
| --- | --- |
| locale |Codice lingua e area geografica di quattro lettere per la visualizzazione del modello. Ad esempio, `en-us` rappresenta l'inglese americano e `de-de` rappresenta il tedesco. |
| search term |Il termine di ricerca per i modelli da includere nella visualizzazione. Ad esempio, cercare `wunderlist` per visualizzare i modelli per Wunderlist. |
| number of templates |Il numero di modelli da includere nella visualizzazione. |
| destination |La pagina visualizzata quando l'utente sceglie il modello. Specificare `details` per visualizzare i dettagli sul modello oppure specificare `new` per aprire la finestra di progettazione di Microsoft Flow. |
| parameters.{name} |Contesto aggiuntivo da passare al flusso. |

Se il parametro di destinazione è `new`, Microsoft Flow viene aperto quando gli utenti fanno clic su un modello. Sarà quindi possibile creare un flusso nella finestra di progettazione. Per osservare il funzionamento dell'esperienza completa all'interno dell'app, vedere la sezione successiva.

### <a name="passing-additional-parameters-to-the-flow"></a>Passaggio di parametri aggiuntivi al flusso
Se l'utente è in un determinato contesto in un'app o nel sito Web, si può decidere di passare tale contesto al flusso. Ad esempio, un utente può aprire un modello per ricevere *una notifica quando un elemento viene aggiunto a un elenco* durante la ricerca in un determinato elenco di Wunderlist. Seguendo questi passaggi, è possibile passare l'ID elenco come *parametro* al flusso:

1. Definire il parametro nel modello di flusso prima della pubblicazione. Un parametro è simile a `@{parameters('parameter_name')}`.
2. Passare il parametro nell'attributo iframe src. Ad esempio, aggiungere `&parameters.listName={the name of the list}` se si ha un parametro denominato **listName**.

### <a name="full-sample"></a>Esempio completo
Per visualizzare i primi quattro modelli su Wunderlist in tedesco e avviare l'utente con **myCoolList**:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>Incorporare la gestione dei flussi
Usare Flow SDK autenticato per consentire agli utenti di creare e gestire flussi direttamente dal sito Web o dall'app (invece di passare al portale di Microsoft Flow). Per usare l'SDK autenticato, l'utente dovrà accedere all'account Microsoft o Azure Active Directory.

> [!NOTE]
> Tutti gli utenti che usano Microsoft Flow nell'applicazione saranno utenti di Microsoft Flow. Non è possibile nascondere il branding di Microsoft Flow.
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>Includere il codice JavaScript per l'SDK autenticato
Seguendo questo esempio, includere l'SDK nel codice HTML. È anche possibile scaricare, minimizzare e includere l'SDK con il prodotto.

```javascript
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>Creare un contenitore per contenere la visualizzazione
Aggiungere un tag div HTML

```html
<div id="flowDiv" class="flowContainer"></div>
```

Si consiglia di applicare uno stile a questo contenitore in modo che venga visualizzato con dimensioni appropriate durante l'uso:

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

Si noti che il rendering dell'attributo iframe non verrà eseguito correttamente con una larghezza inferiore a 320 pixel e non riempirà il contenuto con una larghezza superiore a 1200 pixel. Per quanto riguarda l'altezza, qualsiasi valore andrà bene.

### <a name="authentication-against-the-sdk"></a>Autenticazione sull'SDK
Per l'elenco dei flussi che l'utente ha già scritto e anche per creare flussi in base ai modelli, fornire un authToken da AAD.

```javascript
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https://flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv',
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

Per trovare l'`environmentId`, eseguire la chiamata all'API seguente, che restituisce l'elenco di ambienti a cui l'utente ha accesso:

```http
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

La chiamata restituisce una risposta JSON con l'elenco degli ambienti, da cui è possibile selezionare qualsiasi ambiente. È possibile cercare l'ambiente utente predefinito controllando la proprietà `properties.isDefault=true`.

In questo esempio, `requestParam` è definito come:

```javascript
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

Successivamente, `widgetDoneCallback` è una funzione di callback che deve essere chiamata una volta che l'host ha acquisito il token. Ciò avviene perché l'acquisizione di token è probabilmente un processo asincrono. I parametri che devono essere passati quando si chiama questa funzione sono `(errorResult: any, successResult: any)`. Il parametro successResult dipenderà dal tipo di callback. Per `GetAccessToken` il tipo è:

```javascript
export interface IGetAccessTokenResult {
    token: string;
}
```
