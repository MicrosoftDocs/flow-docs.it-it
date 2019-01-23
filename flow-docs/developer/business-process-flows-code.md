---
title: Usare i processi aziendali con il codice | MicrosoftDocs
description: Informazioni su come usare i processi aziendali a livello di codice per creare processi aziendali più efficienti e semplificati.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 4fcbca859d167e82229aa60f96f5122912e5cca3
ms.sourcegitcommit: c7c9add30d5bf1ab6bd5b55b802fd28618b38411
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362979"
---
# <a name="work-with-business-process-flows-using-code"></a>Usare i processi aziendali con il codice

Un *processo aziendale* consente di creare processi aziendali di vendita, servizio o altro genere in modo più efficiente e semplificato. Posizionando controlli speciali nella parte superiore dei moduli di entità, viene creata una visualizzazione del processo aziendale. Gli utenti possono familiarizzare con le varie fasi dei processi di vendita, marketing o servizio fino al completamento. Ogni processo supporta più fasi e passaggi. È possibile aggiungere o rimuovere i passaggi, modificare l'ordine delle fasi o aggiungere nuove entità al processo aziendale.  
  
È possibile eseguire simultaneamente diverse istanze del processo aziendale usando lo stesso record di entità. Gli utenti possono passare tra le istanze simultanee del processo aziendale e riprendere a lavorare nella fase corrente del processo. 

Questo argomento offre informazioni su come usare i processi aziendali a livello di codice.

> [!NOTE]
> Non è necessario scrivere il codice per usare i processi aziendali. Per informazioni sull'uso dell'interfaccia utente per creare e gestire i processi aziendali, vedere [Panoramica dei processi aziendali](../business-process-flows-overview.md)  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Prerequisiti per il processo aziendale 

Nel processo aziendale possono essere incluse le entità personalizzate e le entità che hanno aggiornato i moduli dell'interfaccia utente. La proprietà <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> delle entità aggiornate dell'interfaccia utente è impostata su `true`. 

Per abilitare un'entità del processo aziendale, impostare la proprietà <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> su `true`.

> [!IMPORTANT]
>  L'abilitazione di un'entità del processo aziendale è un processo unidirezionale e non può essere annullato.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definire un processo aziendale
  
Usare la finestra di progettazione grafica del processo aziendale per definire un processo aziendale. Altre informazioni: [Creare un processo aziendale](../create-business-process-flow.md)

Per impostazione predefinita, un record di processo aziendale viene creato con lo stato `Draft`.  

La definizione di un processo aziendale viene archiviata nell'entità <xref:Microsoft.Dynamics.CRM.workflow>, mentre le informazioni sulla fase del processo aziendale vengono archiviate nell'entità <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Attivare un processo aziendale  
 Per poter usare il processo aziendale, è prima necessario attivarlo. Per attivarlo, si deve avere il privilegio `prvActivateBusinessProcessFlow` per l'entità `Workflow`. Usare il messaggio <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> per impostare lo stato del record di entità `Workflow` su `Activated`. Altre informazioni: [Perform specialized operations using Update](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) (Eseguire operazioni specifiche con Update) 

 > [!NOTE]
 > Per attivare un processo aziendale, è anche possibile usare la finestra di progettazione del processo aziendale. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entità del processo aziendale 
 Dopo aver attivato la definizione di un processo aziendale modificando lo stato del record di entità `Workflow` corrispondente o usando la finestra di progettazione del processo aziendale, viene automaticamente creata un'entità personalizzata in cui archiviare il processo aziendale attivato. Tale entità viene denominata "*\<activesolutionprefix>*_*\<uniquename>*", dove uniquename viene derivato dal nome specificato.  
  
 Ad esempio, se il nome specificato per la definizione del processo aziendale è "My Custom BPF" e si usa l'autore predefinito (new) per la soluzione attiva, il nome dell'entità personalizzata creata per l'archiviazione delle istanze del processo sarà "new_mycustombpf".  
  
 Se il valore `uniquename` non è disponibile per la definizione di un processo aziendale, ad esempio se il processo aziendale è stato importato come parte di una soluzione da una versione precedente, il nome predefinito dell'entità personalizzata sarà "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  I record del processo aziendale di esempio usano le entità di sistema per archiviare i record dell'istanza del processo aziendale corrispondente.  
>   
>  Tuttavia, le nuove definizioni del processo aziendale create useranno le entità personalizzate per archiviare i record dell'istanza, come spiegato in precedenza. 

È possibile recuperare il nome dell'entità del processo aziendale usando uno dei modi seguenti:

- **Interfaccia utente**: usare l'interfaccia utente di personalizzazione per selezionare l'entità del processo aziendale:

    ![](media/bpf-entity-name.png)
- **API Web**: usare la richiesta seguente:

    **Richiesta**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Risposta**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- **Servizio organizzazione**: Usare l'esempio di codice seguente:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> La proprietà <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> è `true` per le entità del processo aziendale. Per recuperare tutte le entità del processo aziendale nell'istanza, eseguire la richiesta API Web seguente:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Gestire la sicurezza per i processi aziendali

L'entità personalizzata che viene creata automaticamente all'attivazione di un processo aziendale per archiviare le istanze del processo aziendale è conforme al modello di sicurezza standard come per qualsiasi altra entità personalizzata in Customer Engagement. Ciò implica che i privilegi concessi per tali entità definiscono le autorizzazioni di runtime per gli utenti per i processi aziendali.

L'ambito dell'entità del processo aziendale personalizzata è l'organizzazione. I privilegi standard di creazione, recupero, aggiornamento ed eliminazione per questa entità definiscono le autorizzazioni per l'utente in base ai ruoli assegnati all'utente stesso. Per impostazione predefinita, quando viene creata l'entità personalizzata del processo aziendale, l'accesso viene concesso solo ai ruoli di sicurezza **Amministratore sistema** e **Addetto personalizzazione sistema** ed è necessario concedere in modo esplicito le autorizzazioni per la nuova entità de processo aziendale (ad esempio, **My Custom BPF**) per gli altri ruoli di sicurezza in base alle esigenze.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Creare, recuperare, aggiornare ed eliminare record dell'entità del processo aziendale (istanze del processo)  
 L'entità personalizzata che viene creata automaticamente all'attivazione di una definizione di processo aziendale archivia tutte le istanze del processo per la definizione del processo aziendale. L'entità personalizzata supporta la creazione a livello di codice standard e la gestione dei record (istanze del processo) tramite l'API Web e l'endpoint di CRM 2011.

> [!IMPORTANT]
> Il passaggio a un'altra istanza del processo per un record di entità è supportato solo tramite l'interfaccia utente (client) o a livello di codice usando le informazioni disponibili in questa sezione. Non è più possibile usare il messaggio `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> o <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) per cambiare processo a livello di codice (impostare un altro processo aziendale come istanza del processo attiva) per il record dell'entità di destinazione. 

 Si considera l'esempio seguente che include un processo aziendale tra entità, "My Custom BPF", con 3 fasi: S1:Account, S2:Account e S3:Contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Recuperare tutti i record (istanze) per un'entità del processo aziendale
 Se il nome dell'entità del processo aziendale è "new_mycustombpf", usare la query seguente per recuperare tutti i record (istanze del processo) per l'entità del processo aziendale:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

A questo punto, si potrebbero non ottenere istanze in risposta se non esistono. Eseguire questa richiesta dopo aver creato un'istanza della definizione del processo aziendale, come descritto più avanti in questo argomento.

> [!NOTE]
> Per informazioni su come recuperare il nome dell'entità del processo aziendale, vedere la sezione precedente [Entità del processo aziendale](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Creare un record di entità del processo aziendale (istanza del processo) 

Creare un record di entità del processo aziendale (istanza del processo) a livello di codice se si vuole passare a un altro processo aziendale per un record di entità senza usare l'interfaccia utente. 

Per creare un record di entità del processo aziendale, è necessario specificare i valori seguenti: 
- Associare il record di entità del processo aziendale a un record di entità primaria impostando la proprietà di navigazione a valore singolo con la annotazione `@odata.bind`. Per individuare il nome della proprietà di navigazione che si riferisce al record di entità primaria per la definizione del processo aziendale, usare il [documento CSDL $metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Associare il record di entità del processo aziendale a una fase valida specificata nella definizione del processo aziendale, impostando la proprietà di navigazione a valore singolo con la annotazione `@odata.bind`. Per individuare il nome della proprietà di navigazione (in genere `activestageid`) che si riferisce al record di fase per la definizione del processo aziendale, usare il [documento CSDL $metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    È anche possibile recuperare le informazioni relative a tutte le fasi di una definizione del processo aziendale usando la richiesta dell'API Web seguente, presupponendo che l'ID della definizione del processo aziendale sia 2669927e-8ad6-4f95-8a9a-f1008af6956f:

    **Richiesta**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Risposta**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

A questo punto, usare la richiesta seguente per creare un'istanza della definizione del processo aziendale per un record di account (ID=a176be9e-9a68-e711-80e7-00155d41e206) e la fase attiva impostata come prima fase dell'istanza del processo, S1 (ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Richiesta**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Risposta**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Si noti che se si vuole creare un'istanza della definizione del processo aziendale impostando la fase attiva non come prima fase ma come ***altra fase***, è necessario specificare anche `traversedpath` nella richiesta. Il percorso incrociato è specificato dalla stringa delimitata da virgole degli ID delle fasi del processo che rappresentano le fasi visitate dell'istanza del processo aziendale. La richiesta seguente crea un'istanza per un record di account (ID=679b2464-71b5-e711-80f5-00155d513100) e la fase attiva impostata come seconda fase, S2 (ID=19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Aggiornare un record di entità del processo aziendale (istanza del processo)

È possibile aggiornare un'istanza del processo per passare alla fase successiva o precedente, abbandonare, riattivare o terminare un'istanza del processo. 

#### <a name="stage-navigation"></a>Spostamento tra le fasi

Per passare a una fase diversa, è necessario aggiornare un record dell'istanza del processo per modificare il relativo ID della fase attiva e conseguentemente aggiornare il percorso incrociato. Si noti che durante l'aggiornamento del processo aziendale, è possibile passare solo alla fase precedente o successiva.

Per spostarsi tra le fasi, è necessario l'ID dell'istanza del processo aziendale che si vuole aggiornare. Per recuperare tutte le istanze del processo aziendale, vedere la sezione precedente [Recuperare tutti i record (istanze) per un'entità del processo aziendale](#retrieve-all-the-records-instances-for-a-business-process-flow-entity).

Supponendo che l'ID dell'istanza del processo da aggiornare sia dc2ab599-306d-e811-80ff-00155d513100, usare la richiesta seguente per aggiornare la fase attiva da S1 a S2:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Modificare lo stato di un'istanza del processo: interrompere, riattivare o terminare 

Un'istanza del processo può avere uno degli stati seguenti: **Active**, **Finished** o **Aborted**. Lo stato è determinato dagli attributi seguenti per il record di istanza del processo:

- **statecode**: visualizza lo stato dell'istanza del processo.

    |Valore|Etichetta|
    |-----|-----|
    |0    |Attivo|
    |1    |Non attivo|

- **statuscode**: visualizza informazioni sullo stato dell'istanza del processo.

    |Valore|Etichetta|
    |-----|-----|
    |1    |Attivo|
    |2    |Terminato|
    |3    |Interrotto|

A questo punto, per **interrompere** un'istanza del processo, usare la richiesta seguente e impostare i valori `statecode` e `statuscode` in modo appropriato:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> È possibile interrompere un'istanza del processo in qualsiasi fase.

Analogamente, per riattivare un'istanza del processo, sostituire rispettivamente i valori `statecode` e `statuscode` nel codice precedente con i valori **0** e **1**.

Infine, per impostare lo stato di un'istanza del processo su **Terminato** (stato possibile solo nell'ultima fase di un'istanza del processo), sostituire rispettivamente i valori `statecode` e `statuscode` nel codice precedente con **0** e **2**.

#### <a name="cross-entity-navigation"></a>Navigazione tra entità

Per la navigazione tra entità in questo esempio, è necessario impostare la fase attiva dell'istanza del processo sull'ultima fase, S3 (ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), aggiornare quindi il percorso incrociato e impostare un record contatto come record di entità primaria in base alla definizione del processo aziendale.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Eliminare un record di entità del processo aziendale (istanza del processo)

Usare la richiesta dell'API Web seguente:

**Richiesta**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Risposta**

Se il record esiste, si otterrà una risposta normale con stato 204 a indicare che l'eliminazione è stata completata. Se l'entità non viene trovata, si otterrà una risposta con stato 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Usare i messaggi RetrieveProcessInstances e RetrieveActivePath

Usare il messaggio `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) per recuperare tutte le istanze del processo aziendale per un record di entità tra tutte le definizione del processo aziendale. Le istanze del processo aziendale restituite per un'entità vengono ordinate in base all'attributo `modifiedon` dell'istanza. Ad esempio, l'istanza del processo aziendale modificata più di recente sarà il *primo* record nella raccolta restituita. L'istanza del processo aziendale modificata più di recente è l'istanza attiva nell'interfaccia utente per il record di entità.  
  
Ogni record dell'istanza del processo aziendale restituito per un record di entità tramite il messaggio `RetrieveProcessInstances` memorizza l'ID della fase attiva nell'attributo `processstageid` che può essere usato per individuare la fase attiva e passare alla fase precedente o successiva. A tale scopo, è prima necessario trovare il percorso attivo di un'istanza del processo aziendale e le fasi disponibili nell'istanza del processo usando il messaggio `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Dopo aver trovato la fase attiva e le informazioni sul percorso attivo di un'istanza del processo aziendale, è possibile usare tali dati per passare alla fase precedente o successiva nel percorso attivo. Lo spostamento in avanti nelle fasi deve avvenire in sequenza, vale a dire che è possibile spostarsi solo in avanti, passando alla fase successiva del percorso attivo.   
  
 Per l'esempio di codice completo che dimostra l'uso di questi due metodi e lo spostamento tra le fasi tramite [Servizio organizzazione](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), vedere [Esempio: Usare i processi aziendali](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Applicare un processo aziendale durante la creazione di un record di entità

Questa sezione offre informazioni sul comportamento predefinito che consente di applicare automaticamente i processi aziendali a nuovi record di entità creati in Customer Engagement. Spiega anche come poter sostituire questo comportamento per applicare un processo aziendale a scelta a nuovi record di entità.

Per impostazione predefinita, per un'entità per la quale sono stati definiti più processi aziendali, il sistema applica un processo aziendale al nuovo record di entità usando la logica in più passi seguente:
1. Identificare tutti i processi aziendali applicabili al nuovo record di entità in base all'attributo **Workflow.PrimaryEntity** dei record di definizione del processo aziendale.
2. Identificare le definizioni del processo aziendale che l'utente corrente usa per eseguire l'accesso. Per informazioni su come determinare e gestire l'accesso al processo aziendale, vedere la sezione [Gestire la sicurezza per i processi aziendali](#BPFSecurity) illustrata in precedenza in questo argomento.<br/>  
3. Tutte le definizioni del processo aziendale nel sistema sono soggette a un ordine globale per ogni entità. L'ordine del processo aziendale viene archiviato nell'attributo **Workflow.ProcessOrder** Le definizioni del processo aziendale per un'entità vengono classificate in base a questo ordine e viene selezionata quella con il valore più basso nell'ordine.
4. Infine, se il record di entità viene creato da un'app aziendale (modulo dell'app), viene applicato un altro livello di filtro per selezionare il processo aziendale da applicare automaticamente al nuovo record di entità. Quando si lavora in un'app, gli utenti possono accedere solo a entità, processi aziendali, visualizzazioni e moduli rilevanti, che sono stati loro concessi in virtù dei ruoli di sicurezza assegnati all'app aziendale. 
    - Se l'app aziendale non contiene processi aziendali, il processo aziendale verrà applicato come spiegato fino al passaggio 3.
    - Se l'app aziendale contiene uno o più processi aziendali, sarà applicato solo il processo aziendale presente nell'app. In questo caso, quando l'utente usa un contesto dell'app aziendale, l'elenco dei processi aziendali descritti nel passaggio 3 viene filtrato per ottenere i processi che fanno parte dell'app aziendale all'interno del modulo dell'app. Tali processi vengono poi classificati in base all'ordine del processo. 
    - Se nessun processo aziendale è disponibile nell'app aziendale per l'entità e l'utente non ha accesso ad alcun processo, non verrà applicato nessun processo aziendale al nuovo record di entità.

È possibile eseguire l'override della logica predefinita per ottenere i processi aziendali da applicare automaticamente ai nuovi record di entità. A tale scopo, impostare l'attributo **ProcessId** dell'entità su uno dei valori seguenti durante la creazione di un nuovo record di entità:
- Impostare su **Guid.Empty** per ignorare l'impostazione di un processo aziendale per i nuovi record di entità. Questa opzione potrebbe essere utile se si creano record di entità in blocco, ma non si vuole applicare un processo aziendale a tali record.
- Impostare l'attributo su un'entità specifica del processo aziendale (riferimento all'entità). In questo caso, il sistema applicherà il processo aziendale specificato anziché la logica predefinita.

Se durante la creazione di un nuovo record di entità non si imposta un valore per l'attributo **ProcessId**, il sistema applicherà la logica predefinita come descritto in precedenza.

> [!NOTE]
> La sostituzione della logica predefinita per ottenere i processi aziendali da applicare automaticamente ai nuovi record di entità è supportata solo a livello di codice. Non è possibile eseguire tale operazione usando l'interfaccia utente.

## <a name="legacy-process-related-attributes-in-entities"></a>Attributi legacy correlati al processo nelle entità

Gli attributi legacy correlati al processo (ad esempio **ProcessId**, **StageId** e **TraversedPath**) nelle entità abilitate per i processi aziendali sono già deprecati. La modifica degli attributi legacy correlati al processo per i record di entità di destinazione non garantisce la coerenza dello stato del processo aziendale e ***non*** è uno scenario supportato. È consigliabile usare gli attributi dell'entità del processo aziendale, come illustrato in precedenza nella sezione [Creare, recuperare, aggiornare ed eliminare i record di entità del processo aziendale (istanze del processo)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances).

L'unica eccezione consiste nel modificare a livello di codice l'attributo **ProcessId** durante la creazione di un record di entità in modo da sostituire l'applicazione predefinita del processo aziendale con un nuovo record, come illustrato nella sezione precedente: [Applicare un processo aziendale durante la creazione di un record di entità](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Supporto per la programmazione lato client dei processi aziendali  
 Esiste un oggetto lato client che è possibile usare per interagire con i processi aziendali negli script del modulo. I processi aziendali attivano eventi lato client ogni volta che un processo viene applicato a un record, la fase viene modificata o il relativo stato cambia in `Active`, `Finished` o `Aborted`. Altre informazioni: [formContext.data.process (Client API reference)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md) (formContext.data.process (riferimento API client))  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Numero massimo di processi, fasi e passaggi  
 Per ogni entità, il valore predefinito per il numero massimo di processi aziendali attivati è 10. È possibile specificare un valore diverso usando l'attributo `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Se il valore è maggiore di 10, le prestazioni del sistema potrebbero diminuire quando si passa da un processo all'altro oppure si apre un record assegnato a un processo. Il calo delle prestazione potrebbe essere particolarmente evidente se i processi contemplano più entità.  
  
 Le impostazioni seguenti non sono personalizzabili:  
  
-   Il numero massimo di fasi per ogni entità del processo è 30.  
  
-   Il numero massimo di passaggi in ogni fase è 30.  
  
-   Il numero massimo di entità che possono partecipare al processo è 5.  

