---
title: Usare i flussi del processo di business tramite codice | MicrosoftDocs
description: Informazioni su come usare i flussi del processo di business a livello di codice per creare processi aziendali più efficienti e ottimizzati.
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
ms.openlocfilehash: 5ce11084cb9a430899fd0a4b672e009c0dc22d25
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547744"
---
# <a name="work-with-business-process-flows-using-code"></a>Usare i flussi del processo di business tramite codice
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Un *flusso del processo di business* consente di creare vendite, servizi e altri processi aziendali più efficienti e ottimizzati. Viene creata una visualizzazione del processo di business inserendo controlli speciali nella parte superiore dei moduli dell'entità. Gli utenti sono guidati attraverso diverse fasi di processi di vendita, marketing o servizio per il completamento. Ogni processo supporta più fasi e passaggi. È possibile aggiungere o rimuovere passaggi, modificare l'ordine delle fasi o aggiungere nuove entità al flusso del processo di business.  
  
Diverse istanze di flusso del processo di business possono essere eseguite contemporaneamente sullo stesso record di entità. Gli utenti possono passare tra istanze di processi aziendali simultanee e riprendere il lavoro in una fase corrente del processo. 

In questo argomento vengono fornite informazioni su come è possibile utilizzare i flussi dei processi di business a livello di codice.

> [!NOTE]
> Non è necessario scrivere codice per lavorare con i flussi del processo di business. Per informazioni sull'utilizzo dell'interfaccia utente per la creazione e la gestione di flussi di processi aziendali, vedere [Cenni preliminari sui flussi dei processi aziendali](../business-process-flows-overview.md)  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Prerequisiti per il flusso del processo di business 

Le entità e le entità personalizzate che hanno aggiornato i moduli dell'interfaccia utente possono partecipare al flusso del processo di business. Le entità dell'interfaccia utente aggiornate hanno la proprietà <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> impostata su `true`. 

Per abilitare un'entità per il flusso del processo di business, impostare la proprietà <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> su `true`.

> [!IMPORTANT]
>  L'abilitazione di un'entità per il flusso del processo di business è un processo unidirezionale. Non è possibile invertirlo.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definire il flusso del processo di business
  
Utilizzare la finestra di progettazione del flusso del processo di business visivo per definire un flusso del processo di business. Altre informazioni: [creare un flusso del processo di business](../create-business-process-flow.md)

Per impostazione predefinita, viene creato un record di flusso del processo di business nello stato `Draft`.  

Una definizione del flusso del processo di business viene archiviata nell'entità <xref:Microsoft.Dynamics.CRM.workflow> e le informazioni sulla fase per il flusso del processo di business vengono archiviate nell'entità <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Attivare il flusso del processo di business  
 Prima di poter usare il flusso di processo, è necessario attivarlo. Per attivarla, è necessario disporre del privilegio `prvActivateBusinessProcessFlow` per l'entità `Workflow`. Utilizzare il messaggio <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> per impostare lo stato del record `Workflow` entità su `Activated`. Ulteriori informazioni: [esecuzione di operazioni specializzate mediante Update](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > È inoltre possibile utilizzare la finestra di progettazione del flusso del processo di business per attivare un flusso del processo di business. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entità del flusso del processo di business 
 Una volta attivata la definizione del flusso del processo di business modificando lo stato del record di entità `Workflow` corrispondente o utilizzando la finestra di progettazione del flusso del processo di business, viene creata automaticamente un'entità personalizzata con il nome seguente per archiviare l'attività attivata istanze del flusso di processo: " *\<activesolutionprefix >* _ *\<UniqueName >* ", dove UniqueName deriva dal nome specificato.  
  
 Se, ad esempio, è stato specificato "My Custom BPF" come nome della definizione del flusso del processo di business e si utilizza il server di pubblicazione predefinito (nuovo) per la soluzione attiva, il nome dell'entità personalizzata creata per archiviare le istanze del processo sarà "new_mycustombpf".  
  
 Se il valore `uniquename` non è disponibile per una definizione del flusso del processo di business, ad esempio se il flusso del processo di business è stato importato come parte della soluzione da una versione precedente, il nome predefinito dell'entità personalizzata sarà "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  I record di flusso del processo di business di esempio usano entità di sistema per archiviare i record dell'istanza del flusso del processo di business corrispondente.  
>   
>  Tuttavia, qualsiasi nuova definizione di flusso del processo di business creata utilizzerà entità personalizzate per archiviare i record di istanza, come illustrato in precedenza. 

È possibile recuperare il nome dell'entità del flusso del processo di business usando uno dei modi seguenti:

- Uso **dell'interfaccia utente**: usare l'interfaccia utente di personalizzazione per passare all'entità del flusso del processo di business:

    ![](media/bpf-entity-name.png)
- **Usando l'API Web**: usare la richiesta seguente:

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
- **Utilizzo del servizio organizzazione**: utilizzare l'esempio di codice seguente:

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
> La proprietà <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> è `true` per le entità del flusso del processo di business. È possibile recuperare tutte le entità del flusso del processo di business nell'istanza eseguendo la richiesta API Web seguente:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Gestire la sicurezza per i flussi dei processi aziendali

L'entità personalizzata creata automaticamente quando si attiva un flusso del processo di business per archiviare le istanze del flusso del processo di business rispetta il modello di sicurezza standard come per qualsiasi altra entità personalizzata in Common Data Service. Ciò implica che i privilegi concessi a tali entità definiscono le autorizzazioni di runtime per gli utenti per i flussi del processo di business.

L'entità del flusso del processo di business personalizzato dispone dell'ambito dell'organizzazione. I normali privilegi di creazione, recupero, aggiornamento ed eliminazione di questa entità definiscono gli utenti autorizzati in base ai rispettivi ruoli assegnati. Per impostazione predefinita, quando viene creata l'entità personalizzata del flusso del processo di business, solo l' **amministratore di sistema** e i ruoli di sicurezza di **verbi di sistema** sono autorizzati ad accedervi ed è necessario concedere esplicitamente le autorizzazioni per la nuova entità del flusso del processo di business (per esempio, **BPF personalizzato**) per altri ruoli di sicurezza, come richiesto.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Creazione, recupero, aggiornamento ed eliminazione di record di entità del flusso del processo di business (istanze di processo)  
 L'entità personalizzata creata automaticamente durante l'attivazione di una definizione del flusso del processo di business archivia tutte le istanze del processo per la definizione del flusso del processo di business. L'entità personalizzata supporta la creazione e la gestione a livello di codice standard di record (istanze di processo) tramite l'API Web e l'endpoint CRM 2011.

> [!IMPORTANT]
> Il passaggio a un'altra istanza del processo per un record di entità è supportato solo tramite l'interfaccia utente (client) o a livello di codice usando le informazioni disponibili in questa sezione. Non è più possibile usare il messaggio di `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> o <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) per cambiare a livello di codice i processi (impostare un altro flusso del processo di business come istanza di processo attiva) per il record dell'entità di destinazione. 

 Si consideri l'esempio seguente in cui è presente un flusso del processo di business tra entità, ovvero "My Custom BPF", con 3 fasi: S1: account, S2: account e S3: Contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Recuperare tutti i record (istanze) per un'entità del flusso del processo di business
 Se il nome dell'entità flusso del processo di business è "new_mycustombpf", utilizzare la query seguente per recuperare tutti i record (istanze di processo) per l'entità del flusso del processo di business:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

A questo punto, è possibile che non si ottengano istanze nella risposta perché non sono presenti. Eseguire questa richiesta dopo aver creato un'istanza della definizione del flusso del processo di business più avanti in questo argomento.

> [!NOTE]
> Per informazioni su come recuperare il nome dell'entità del flusso del processo di business, vedere la sezione precedente, [entità del flusso del processo di business](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Creare un record di entità del flusso del processo di business (istanza del processo) 

Creare un record dell'entità di flusso del processo di business (istanza del processo) a livello di codice se si desidera passare a un altro flusso del processo di business per un record di entità senza utilizzare l'interfaccia utente. 

Per creare un record di entità del flusso del processo di business, è necessario specificare i valori seguenti: 
- Associare il record dell'entità di flusso del processo di business a un record di entità primario impostando la proprietà di navigazione a valore singolo utilizzando l'annotazione `@odata.bind`. Per individuare il nome della proprietà di navigazione che punta al record di entità primario per la definizione del flusso del processo di business, utilizzare il [documento CSDL $Metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Associare il record dell'entità di flusso del processo di business a una fase valida specificata nella definizione del flusso del processo di business impostando la proprietà di navigazione a valore singolo utilizzando l'annotazione `@odata.bind`. Per individuare il nome della proprietà di navigazione (in genere `activestageid`) che punta al record della fase per la definizione del flusso del processo di business, utilizzare il [documento $Metadata CSDL](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    Inoltre, è possibile recuperare informazioni su tutte le fasi per una definizione del flusso del processo di business usando la richiesta API Web seguente, presupponendo che l'ID della definizione del flusso del processo di business sia 2669927e-8AD6-4f95-8a9a-f1008af6956f:

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

Successivamente, utilizzare la richiesta seguente per creare un'istanza della definizione del flusso del processo di business per un record di account (ID = a176be9e-9a68-E711-80e7-00155d41e206) e il set di fasi attivo come prima fase dell'istanza del processo, S1 (ID = 9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

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

Si noti che se si desidera creare un'istanza della definizione del flusso del processo di business con la fase attiva impostata come una fase ***diversa*** dalla prima fase, è necessario specificare anche `traversedpath` nella richiesta. Il percorso attraversato è la stringa delimitata da virgole degli ID di fase del processo che rappresentano le fasi visitate dell'istanza del flusso del processo di business. La richiesta seguente crea un'istanza per un record di account (ID = 679b2464-71B5-E711-80f5-00155d513100) e un set di fasi attivo come seconda fase, S2 (ID = 19a11fc0-3398-4214-8522-cb2a97f66e4b).

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

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Aggiornare un record dell'entità di flusso del processo di business (istanza del processo)

È possibile aggiornare un'istanza del processo per passare alla fase successiva o precedente, abbandonare un'istanza di processo, riattivare un'istanza di processo o terminare un'istanza del processo. 

#### <a name="stage-navigation"></a>Spostamento della fase

Per passare a una fase diversa, è necessario aggiornare un record dell'istanza del processo per modificare il relativo ID di fase attivo e aggiornare di conseguenza il percorso attraversato. Si noti che è necessario passare alla fase successiva o precedente durante l'aggiornamento di un'istanza del flusso del processo di business.

Per eseguire la navigazione nella fase, è necessario l'ID dell'istanza del flusso del processo di business che si desidera aggiornare. Per recuperare tutte le istanze del flusso del processo di business, vedere [il recupero di tutti i record (istanze) per un'entità del flusso del processo di business](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) in precedenza.

Supponendo che l'ID dell'istanza di processo che si vuole aggiornare sia dc2ab599-306d-E811-80ff-00155d513100, usare la richiesta seguente per aggiornare la fase attiva da S1 a S2:

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

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Modificare lo stato di un'istanza di processo: Interrompi, riattiva o fine 

Un'istanza di processo può avere uno degli Stati seguenti: **attivo**, **terminato**o **interrotto**. Lo stato è determinato dagli attributi seguenti nel record dell'istanza del processo:

- **statecode**: Visualizza lo stato dell'istanza del processo.

    |valore|Etichetta|
    |-----|-----|
    |0    |Active|
    |1    |Inattivo|

- **statusCode**: Visualizza informazioni sullo stato dell'istanza del processo.

    |valore|Etichetta|
    |-----|-----|
    |1    |Active|
    |2    |Termine|
    |3    |Interrotta|

Quindi, per **interrompere** un'istanza del processo, usare la richiesta seguente per impostare i valori `statecode` e `statuscode` in modo appropriato:

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
> È possibile interrompere un'istanza di processo in qualsiasi fase.

Analogamente, per riattivare un'istanza di processo, sostituire i valori `statecode` e `statuscode` nel codice precedente rispettivamente con **0** e **1** .

Infine, per impostare lo stato di un'istanza del processo come **completato**, che è possibile solo nell'ultima fase di un'istanza del processo, sostituire i valori `statecode` e `statuscode` nel codice precedente rispettivamente con **0** e **2** .

#### <a name="cross-entity-navigation"></a>Navigazione tra entità

Per la navigazione tra le entità in questo esempio, è necessario impostare la fase attiva dell'istanza del processo sull'ultima fase S3 (ID = a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), aggiornare il percorso attraversato di conseguenza e impostare un record di contatto come record di entità primaria in base a definizione del flusso del processo di business.

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

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Eliminare un record di entità del flusso del processo di business (istanza del processo)

Usare la richiesta API Web seguente:

**Richiesta**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Risposta**

Se il record è presente, si otterrà una risposta normale con lo stato 204 per indicare che l'eliminazione è stata completata. Se l'entità non viene trovata, verrà ottenuta una risposta con lo stato 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Usare i messaggi RetrieveProcessInstances e RetrieveActivePath

Utilizzare il messaggio di `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) per recuperare tutte le istanze del flusso del processo di business per un record di entità in tutte le definizioni del processo di business. Le istanze del flusso del processo di business restituite per un'entità vengono ordinate in base all'attributo `modifiedon` per l'istanza. Ad esempio, l'istanza di flusso del processo di business modificata più di recente sarà il *primo* record nella raccolta restituita. L'istanza di flusso del processo di business modificata più di recente è quella attiva nell'interfaccia utente per un record di entità.  
  
Ogni record dell'istanza di flusso del processo di business restituito per un record di entità in seguito all'utilizzo del `RetrieveProcessInstances` messaggio archivia l'ID della fase attiva nell'attributo `processstageid` che può essere utilizzato per trovare la fase attiva e quindi passare alla fase precedente o successiva. A tale scopo, è necessario innanzitutto trovare il percorso attivo di un'istanza del flusso del processo di business e le fasi disponibili nell'istanza del flusso di processo usando il messaggio di `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Dopo aver creato la fase attiva e le informazioni sul percorso attivo per un'istanza del flusso del processo di business, è possibile usare le informazioni per passare a una fase precedente o successiva nel percorso attivo. La navigazione in avanti delle fasi deve essere eseguita in sequenza, ovvero è consigliabile passare solo alla fase successiva nel percorso attivo.   
  
 Per l'esempio completo del codice che illustra l'utilizzo di questi due metodi e la navigazione delle fasi usando il [servizio organizzazione](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), vedere [esempio: usare i flussi del processo di business](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Applicare il flusso del processo di business durante la creazione di un record di entità

In questa sezione vengono fornite informazioni sul comportamento predefinito per l'applicazione automatica dei flussi del processo di business ai nuovi record di entità creati in Common Data Service e sul modo in cui è possibile eseguirne l'override per applicare un flusso del processo di business di propria scelta per i nuovi record di entità.

Per impostazione predefinita, per un'entità a cui sono stati definiti più flussi del processo di business, il sistema applica un flusso del processo di business al nuovo record di entità usando la logica in più passaggi seguente:
1. Identificare tutti i flussi del processo di business applicabili al nuovo record di entità in base all'attributo **Workflow. PrimaryEntity** dei record di definizione del flusso del processo di business.
2. Identificare le definizioni del flusso del processo di business a cui l'utente corrente ha accesso. Per informazioni sul modo in cui l'accesso a un flusso del processo di business è determinato e gestito, vedere [gestire la sicurezza per i flussi del processo di business](#BPFSecurity) più indietro in questo argomento.<br/>  
3. Tutte le definizioni dei flussi del processo di business nel sistema sono soggette a un ordine globale per entità. L'ordine del flusso del processo di business viene archiviato nell'attributo **Workflow. ProcessOrder** . Le definizioni del flusso del processo di business per un'entità vengono ordinate in base a questo ordine e viene selezionato quello con il valore di ordine inferiore.
4. Infine, se il record dell'entità viene creato da un'app aziendale (modulo app), viene applicato un ulteriore livello di filtro per selezionare il flusso del processo di business da applicare automaticamente al nuovo record di entità. Quando si lavora in un'app, gli utenti possono accedere solo a entità rilevanti, flussi di processi aziendali, viste e moduli a cui hanno accesso in virtù dei ruoli di sicurezza assegnati all'app aziendale. 
    - Se l'app aziendale non contiene alcun flusso del processo di business, il flusso del processo di business viene applicato come spiegato fino al passaggio 3.
    - Se l'app aziendale dispone di uno o più flussi del processo di business, saranno applicabili solo i flussi del processo di business presenti nell'app. In questo caso, quando l'utente lavora all'interno di un contesto dell'applicazione aziendale, l'elenco dei flussi del processo di business dal passaggio 3 viene filtrato ulteriormente in base a quelli che fanno parte dell'app aziendale che sono presenti all'interno del modulo app e vengono ordinati in base all'ordine di elaborazione. 
    - Se non è disponibile alcun flusso del processo di business in un'app aziendale per l'entità o uno a cui l'utente può accedere, non viene applicato alcun flusso del processo di business per il nuovo record di entità.

È possibile eseguire l'override della logica predefinita dei flussi del processo di business per essere applicati automaticamente ai nuovi record di entità. A tale scopo, impostare l'attributo **ProcessID** dell'entità su uno dei valori seguenti durante la creazione di un nuovo record di entità:
- Impostare su **GUID. Empty** per ignorare l'impostazione di un flusso del processo di business per i nuovi record di entità. È possibile eseguire questa operazione se si esegue la creazione bulk di record di entità, ma non si desidera che il flusso del processo di business venga applicato a tali record.
- Impostarla su un'entità di flusso del processo di business specifica, come riferimento a un'entità. In questo caso, il sistema applicherà il flusso del processo di business specificato anziché la logica predefinita.

Se non si imposta un valore per l'attributo **ProcessID** durante la creazione di un nuovo record di entità, il sistema applicherà la logica predefinita come illustrato in precedenza.

> [!NOTE]
> L'override della logica predefinita dei flussi del processo di business viene applicato automaticamente ai nuovi record di entità è supportato solo a livello di codice. Questa operazione non può essere eseguita tramite l'interfaccia utente.

## <a name="legacy-process-related-attributes-in-entities"></a>Attributi legacy correlati al processo nelle entità

Gli attributi relativi ai processi legacy, ad esempio **ProcessID**, **StageId**e **TraversedPath**, sulle entità abilitate per i flussi del processo di business sono già deprecati. La modifica di questi attributi correlati al processo legacy per i record di entità di destinazione non garantisce la coerenza dello stato del flusso del processo di business e ***non*** è uno scenario supportato. Il modo consigliato consiste nell'usare gli attributi dell'entità flusso del processo di business, come illustrato in precedenza nella sezione [creare, recuperare, aggiornare ed eliminare i record di entità del flusso del processo di business (istanze di processo)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances)

L'unica eccezione è la modifica a livello di codice dell'attributo **ProcessID** durante la creazione di un record di entità per eseguire l'override dell'applicazione predefinita del flusso del processo di business nel nuovo record, come illustrato nella sezione precedente: [Apply business flusso del processo durante la creazione di un record di entità](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Supporto programmabilità lato client per flussi del processo di business  
 È disponibile un oggetto sul lato client che è possibile usare per interagire con i flussi del processo di business negli script del modulo. I flussi del processo di business attivano eventi lato client ogni volta che un processo viene applicato a un record, la fase viene modificata o il relativo stato viene modificato in `Active`, `Finished`o `Aborted`. Altre informazioni: [formContext. Data. Process (riferimento all'API client)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Numero massimo di processi, fasi e passaggi  
 Per entità, il valore predefinito per il numero massimo di flussi del processo di business attivato è 10. È possibile specificare un valore diverso usando l'attributo `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Tuttavia, se il valore è maggiore di 10, è possibile che si verifichi una riduzione delle prestazioni del sistema quando si alternano processi o si apre un record a cui è assegnato un flusso del processo di business. Questo può essere particolarmente evidente se i processi si estendono su più entità.  
  
 Le impostazioni seguenti non sono personalizzabili:  
  
-   Il numero massimo di fasi per entità nel processo è 30.  
  
-   Il numero massimo di passaggi in ogni fase è 30.  
  
-   Il numero massimo di entità che possono partecipare al flusso del processo è 5.  

