---
title: I flussi vengono ora archiviati in Common Data Service e usano l'API Web avanzata
description: I flussi vengono ora archiviati in Common Data Service e usano l'API Web avanzata.
author: stepsic-microsoft-com
ms.reviewer: deonhe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: business-applications
ms.technology: ''
ms.author: stepsic
audience: Power user
ms.openlocfilehash: ede20606d1d5ba2a97217dfbcfb3c9fffec2c017
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463592"
---
# <a name="microsoft-flow-web-api"></a>API Web Microsoft Flow

In futuro, tutti i flussi verranno archiviati in Common Data Service e sfrutteranno l'[API Web avanzata](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/perform-operations-web-api).

Questo contenuto illustra la gestione dei flussi inclusi nella scheda **Soluzioni** in Microsoft Flow. Attualmente, i flussi in **Flussi personali** non sono supportati da queste API.

## <a name="compose-http-requests"></a>Comporre richieste HTTP

Per iniziare a creare richieste, è prima necessario costruire l'URL. Il formato per l'URL di base dell'API Web di Microsoft Flow è: `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. I due parametri sono:

- L'**ID organizzazione** è un nome univoco per l'ambiente che archivia i flussi. È possibile visualizzare l'ID organizzazione nel selettore dell'ambiente in alto a destra di Microsoft Flow. Si noti che l'**ID organizzazione** è diverso dall'**ID ambiente** (ovvero il GUID visualizzato nell'URL del flusso).

     ![Selettore dell'ambiente](media/web-api/get-organization-id.png "Selettore dell'ambiente")

- Il **sottodominio dell'area** dipende dalla posizione dell'ambiente. Quando si accede a Microsoft Flow, è possibile visualizzare l'area dell'ambiente nell'URL della pagina Web. Usare tale nome di area per trovare il sottodominio corrispondente nella tabella seguente:

     ![URL di Flow](media/web-api/get-region-name.png "URL di Flow")

     | Area         | Sottodominio   |
     | -------------- | ----------- |
     | Stati Uniti  | crm         |
     | America del Sud  | crm2        |
     | Canada         | crm3        |
     | Europa         | crm4        |
     | Asia Pacifico   | crm5        |
     | Australia      | crm6        |
     | Giappone          | crm7        |
     | India          | crm8        |
     | US Government  | crm9        |
     | Regno Unito | crm11       |

È anche possibile ottenere l'elenco delle istanze disponibili a livello di programmazione tramite il metodo [Get Instances](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) (Ottenere istanze) nell'API di gestione online.

Per ogni richiesta all'API Web, le intestazioni `Accept` e `Content-type` devono essere impostate su `application/json`.

Infine, compilare l'intestazione `Authorization` con un token di connessione di Azure AD. [Qui](https://docs.microsoft.com/powerapps/developer/common-data-service/authenticate-oauth) sono disponibili istruzioni su come acquisire un token di connessione di Azure AD per Common Data Service. Ad esempio, questa richiesta:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

La risposta contiene l'elenco dei flussi all'interno dell'ambiente:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#workflows",
    "value": [{
        "@odata.etag": "W/\"12116760\"",
        "category": 5,
        "statecode": 0,
        "workflowidunique": "00000000-0000-0000-0000-000000000001",
        "workflowid" : "00000000-0000-0000-0000-000000000002",
        "createdon": "2018-11-15T19:45:51Z",
        "_ownerid_value": "00000000-0000-0000-0000-000000000003",
        "modifiedon": "2018-11-15T19:45:51Z",
        "ismanaged": false,
        "name": "Sample flow",
        "_modifiedby_value": "00000000-0000-0000-0000-000000000003",
        "_createdby_value": "00000000-0000-0000-0000-000000000003",
        "type": 1,
        "description": "This flow updates some data in Common Data Service.",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"source\":\"NotSpecified\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\",\"tier\":\"NotSpecified\"}},\"definition\":{...}},\"schemaVersion\":\"1.0.0.0\"}"
    }]
}
```

## <a name="list-flows"></a>Ottenere un elenco dei flussi

Come illustrato in precedenza, è possibile ottenere l'elenco dei flussi di lavoro chiamando `GET` su `workflows`. Ogni flusso di lavoro ha molte proprietà, ma le più rilevanti sono:

| Nome proprietà     | Descrizione                                              |
| ----------------- | -------------------------------------------------------- |
| category          | Categoria del flusso. I diversi tipi sono: 0 - flussi di lavoro classici di Common Data Service,  1 - dialoghi classici di Common Data Service, 2 - regole business, 3 - azioni classiche di Common Data Service, 4- flussi di processi aziendali e 5 - flussi automatizzati, immediati o pianificati. |
| statecode         | Stato del flusso. Lo stato può essere **0** - disattivato oppure **1** - attivato.|
| workflowuniqueid  | Identificatore univoco per l'installazione del flusso. |
| workflowid        | Identificatore univoco per un flusso tra tutte le importazioni. |
| createdon         | Data di creazione del flusso. |
| _ownerid_value    | Identificatore univoco dell'utente o del team proprietario del flusso. Questo è un ID dall'entità systemusers in Common Data Service. |
| modifiedon        | Ora dell'ultimo aggiornamento del flusso. |
| ismanaged         | Indica se il flusso è stato installato tramite una soluzione gestita. |
| name              | Nome visualizzato assegnato al flusso. |
| _modifiedby_value | Ultimo utente che ha aggiornato il flusso. Questo è un ID dall'entità systemusers in Common Data Service. |
| _createdby_value  | Utente che ha creato il flusso. Questo è un ID dall'entità systemusers in Common Data Service. |
| type              | Indica se il flusso è in esecuzione o è un modello che può essere usato per creare flussi aggiuntivi. 1 - flusso, 2 - attivazione o 3 - modello. |
| description       | Descrizione del flusso fornita dall'utente. |
| clientdata        | Codice JSON codificato come stringa di un oggetto che contiene connectionReferences e la definizione del flusso. |

È anche possibile richiedere proprietà specifiche, filtrare l'elenco dei flussi e molto altro, come descritto nella [documentazione dell'API di Common Data Service per l'esecuzione di query sui dati](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/query-data-web-api). Ad esempio, questa query restituisce solo i flussi automatizzati, immediati o pianificati attualmente attivi:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Creare un flusso

Chiamare `POST` sulla raccolta `workflows` per creare un flusso. Le proprietà richieste per i flussi automatizzati, immediati e pianificati sono: category, name, type, primaryentity e clientdata. Usare `none` per la proprietà primaryentity per questi tipi di flussi.

È anche possibile specificare una descrizione e un codice di stato.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
        "category": 5,
        "statecode": 0,
        "name": "Sample flow name",
        "type": 1,
        "description": "This flow reads some data from Common Data Service.",
        "primaryentity":"none",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"connectionName\":\"shared-commondataser-00000000-0000-0000-0000-000000000004\",\"source\":\"Invoker\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\"}},\"definition\":{\"$schema\": \"https:\/\/schema.management.azure.com\/providers\/Microsoft.Logic\/schemas\/2016-06-01\/workflowdefinition.json#\",\"contentVersion\": \"1.0.0.0\",\"parameters\": {\"$connections\": {\"defaultValue\": {},\"type\": \"Object\"},\"$authentication\": {\"defaultValue\": {},\"type\": \"SecureObject\"}},\"triggers\": {\"Recurrence\": {\"recurrence\": {\"frequency\": \"Minute\",\"interval\": 1},\"type\": \"Recurrence\"}},\"actions\": {\"List_records\": {\"runAfter\": {},\"metadata\": {\"flowSystemMetadata\": {\"swaggerOperationId\": \"GetItems_V2\"}},\"type\": \"ApiConnection\",\"inputs\": {\"host\": {\"api\": {\"runtimeUrl\": \"https:\/\/firstrelease-001.azure-apim.net\/apim\/commondataservice\"},\"connection\": {\"name\": \"@parameters('$connections')['shared_commondataservice']['connectionId']\"}},\"method\": \"get\",\"path\": \"\/v2\/datasets\/@{encodeURIComponent(encodeURIComponent('default.cds'))}\/tables\/@{encodeURIComponent(encodeURIComponent('accounts'))}\/items\",\"queries\": {\"$top\": 1},\"authentication\": \"@parameters('$authentication')\"}}},\"outputs\": {}}},\"schemaVersion\":\"1.0.0.0\"}"
}
```

La sezione più importante è `clientdata`, che contiene i connectionReferences usati dal flusso e la [definizione](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language) del flusso. I connectionReferences sono i mapping per ogni connessione usata dal flusso.

Esistono tre proprietà:

| Nome proprietà  | Descrizione                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Identifica la connessione. Per visualizzare la proprietà connectionName, passare alla pagina **Connessioni** e quindi copiare il nome dall'URL della connessione. |
| source         | `Embedded` o `Invoker`. Il valore `Invoker` è valido solo per i flussi immediati (quelli in cui un utente seleziona un pulsante per eseguire il flusso) e indica che l'utente finale fornirà la connessione. In questo caso connectionName viene usato solo in fase di progettazione. Se la connessione è `Embedded`, ciò significa che viene usato sempre il valore connectionName specificato. |
| id             | Identificatore della connessione. L'id inizia sempre con `/providers/Microsoft.PowerApps/apis/` e prosegue poi con il nome della connessione, che è possibile copiare dall'URL della connessione o selezionando la connessione dalla pagina **Connessioni**. |

Dopo l'esecuzione della richiesta `POST`, si riceverà l'intestazione `OData-EntityId`, che conterrà il valore `workflowid` per il nuovo flusso.

## <a name="update-a-flow"></a>Aggiornare un flusso

È possibile chiamare `PATCH` sul flusso di lavoro per aggiornare, attivare o disattivare un flusso. Usare la proprietà `workflowid` per effettuare queste chiamate. Ad esempio, è possibile aggiornare la descrizione e il proprietario del flusso con la chiamata seguente:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "description" : "This flow will ensure consistency across systems.",
    "ownerid@odata.bind": "systemusers(00000000-0000-0000-0000-000000000005)",
}
```

> [!NOTE]
> La sintassi per la modifica del proprietario usa il formato `odata.bind`. Questo significa che invece di modificare direttamente il valore del campo \_ownerid_value, si aggiunge `@odata.bind` al nome della proprietà e quindi si esegue il wrapping dell'ID con `systemusers()`.

In un altro esempio, è possibile attivare un flusso con questa chiamata:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "statecode" : 1
}
```

### <a name="delete-a-flow"></a>Eliminare un flusso

È possibile eliminare un flusso con una semplice chiamata `DELETE`:

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> Non è possibile eliminare un flusso attivato. È prima necessario disattivare il flusso (vedere **Aggiornare un flusso** in precedenza). In caso contrario, verrà visualizzato l'errore: `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Recuperare tutti gli utenti con cui è stato condiviso un flusso

È possibile ottenere un elenco degli utenti con accesso usando una *funzione* in Common Data Service. Questa funzione accetta l'unico parametro `Target`:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/RetrieveSharedPrincipalsAndAccess(Target=@tid)?@tid={'@odata.id':'workflows(00000000-0000-0000-0000-000000000002)'}
Accept: application/json
Authorization: Bearer ey...
```

Il parametro `Target` è una stringa JSON con una singola proprietà denominata `@odata.id`. Sostituire l'ID del flusso di lavoro nell'esempio precedente. Il risultato è il seguente:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.RetrieveSharedPrincipalsAndAccessResponse",
    "PrincipalAccesses": [
        {
            "AccessMask": "ReadAccess",
            "Principal": {
                "@odata.type": "#Microsoft.Dynamics.CRM.systemuser",
                "ownerid": "00000000-0000-0000-0000-000000000005"
            }
        }
    ]
}
```

## <a name="share-or-unshare-a-flow"></a>Condividere un flusso o annullarne la condivisione

È possibile condividere un flusso con l'azione `GrantAccess`.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/GrantAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "PrincipalAccess": {
        "Principal": {
            "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
            "ownerid" : "00000000-0000-0000-0000-000000000005"
        },
        "AccessMask": "ReadAccess"
    }
}
```

Il parametro `AccessMask` è un campo con i valori seguenti per diversi livelli di autorizzazione:

| Nome         | Descrizione                                          |
| ------------ | ---------------------------------------------------- |
| None         | Nessun accesso.                                           |
| ReadAccess   | Diritto di leggere il flusso.                          |
| WriteAccess  | Diritto di aggiornare il flusso.                        |
| DeleteAccess | Diritto di eliminare il flusso.                        |
| ShareAccess  | Diritto di condividere il flusso.                         |
| AssignAccess | Diritto di modificare il proprietario del flusso.           |

È possibile combinare le autorizzazioni con una virgola, ad esempio consentire sia la lettura che l'aggiornamento di un flusso passando `ReadAccess,WriteAccess`.

È possibile *annullare la condivisione* di un flusso con l'azione `RevokeAccess`. Ecco un esempio:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/RevokeAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "Revokee": {
        "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
        "ownerid" : "00000000-0000-0000-0000-000000000005"
    }
}
```

`RevokeAccess` rimuove tutte le autorizzazioni concesse in `AccessMask`.

## <a name="export-flows"></a>Esportare flussi

Usare l'azione `ExportSolution` per esportare i flussi in un file ZIP. Prima di tutto, aggiungere i flussi desiderati in una [soluzione](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/).

Quando il flusso è incluso in una soluzione, chiamare l'azione seguente:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ExportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "SolutionName" : "Awesome solution 1",
    "Managed": false
}
```

`ExportSolution` restituisce una stringa con codifica in base 64 nella proprietà `ExportSoutionFile`.

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.ExportSolutionResponse",
    "ExportSolutionFile": "UEsDBBQAAgAI..."
}
```

È quindi possibile salvare il file nel controllo del codice sorgente e/o usare qualsiasi sistema di gestione o distribuzione delle versioni desiderato.

## <a name="import-flows"></a>Importare flussi

Chiamare l'azione `ImportSolution` per importare una soluzione.

| Nome proprietà                    | Descrizione                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | Se sono presenti istanze esistenti di questi flussi in Common Data Service, questo flag deve essere impostato su `true` per importarli. In caso contrario, non verranno sovrascritti. |
| PublishWorkflows                 | Indica se i flussi classici di Common Data Service verranno attivati al momento dell'importazione. Questa impostazione non si applica ad altri tipi di flussi. |
| ImportJobId                      | Specifica un nuovo GUID univoco per tenere traccia del processo di importazione. |
| CustomizationFile                | File ZIP con codifica in base 64 che contiene la soluzione. |

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ImportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "OverwriteUnmanagedCustomizations": false,
    "PublishWorkflows" : true,
    "ImportJobId" : "00000000-0000-0000-0000-000000000006",
    "CustomizationFile" : "UEsDBBQAAgAI..."
}
```

Dato che l'importazione è un'operazione di lunga durata, la risposta all'azione ImportSolution sarà `204 No content`. Per tenere traccia dello stato di avanzamento, chiamare `GET` sull'oggetto `importjobs`, specificando l'`ImportJobId` incluso nell'azione `ImportSolution` originale.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Questa chiamata restituisce lo stato dell'operazione di importazione, inclusi `progress` (percentuale di completamento), `startedon` e `completedon` (se l'importazione è terminata).

Dopo il completamento dell'importazione, sarà necessario configurare le connessioni per il flusso, dato che i `connectionNames` saranno probabilmente diversi nell'ambiente di destinazione (ammesso che le connessioni esistano). Se si configurano nuove connessioni nell'ambiente di destinazione, il proprietario dei flussi deve crearli nella finestra di progettazione di Microsoft Flow. Se le connessioni sono già configurate nel nuovo ambiente, è quindi possibile usare `PATCH` per i `clientData` del flusso con i nomi delle connessioni.
