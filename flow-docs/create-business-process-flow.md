---
title: Creare un flusso del processo di business in PowerApps | MicrosoftDocs
description: Informazioni su come creare un flusso del processo di business
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3bd154935e06031b031432e10fa977f23e1a2c54
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546527"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Esercitazione: creare un flusso del processo di business per standardizzare i processi
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Questa esercitazione illustra come creare un flusso del processo di business con PowerApps. Per ulteriori informazioni sui motivi per cui si utilizzano i flussi del processo di business, vedere [Cenni preliminari sui flussi dei processi aziendali](business-process-flows-overview.md). Per informazioni sulla creazione di un flusso di attività per dispositivi mobili, vedere [creare un flusso di attività per dispositivi mobili](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Quando un utente avvia un flusso del processo di business, le fasi e i passaggi del processo vengono visualizzati nella barra dei processi nella parte superiore di un modulo:  
  
 ![Processo di business con fasi](media/business-process-stages.png "Processo di business con fasi")  
  
 > [!TIP]
 >  Dopo aver creato una definizione del flusso del processo di business, è possibile fornire il controllo sugli utenti che possono creare, leggere, aggiornare o eliminare l'istanza del flusso del processo di business. Per i processi relativi ai servizi, ad esempio, è possibile fornire l'accesso completo ai rappresentanti del servizio clienti per modificare l'istanza di flusso del processo di business, ma fornire l'accesso in sola lettura all'istanza per i rappresentanti di vendita, in modo da poter monitorare le attività post-vendite per la loro clienti. Per impostare la sicurezza per una definizione del flusso del processo di business creata, selezionare **Abilita ruoli di sicurezza** sulla barra delle azioni.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Prerequisiti

Per creare flussi del processo di business, è necessario [Flow Plan 2](https://preview.flow.microsoft.com/pricing/) . Alcuni piani di licenze Dynamics 365 includono Flow piano 2.

## <a name="create-a-business-process-flow"></a>Creare un flusso del processo di business  
  
1. Aprire [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. Nel riquadro di spostamento a sinistra selezionare **processi**. 
  
3.  Sulla barra degli strumenti **azioni** selezionare **nuovo**.  
  
4.  Nella finestra di dialogo **Crea processo** completare i campi obbligatori:  
  
    -   Immettere un nome di processo. Il nome del processo non deve necessariamente essere univoco, ma deve essere significativo per gli utenti che devono scegliere un processo. Questa operazione può essere modificata in un secondo momento.  
  
    -   Nell'elenco **categoria** selezionare flusso del **processo di business**.  
  
         Non è possibile modificare la categoria dopo aver creato il processo.  
  
    -   Nell'elenco **entità** selezionare l'entità su cui si vuole basare il processo.  
  
         L'entità selezionata influisce sui campi disponibili per i passaggi che è possibile aggiungere alla prima fase del flusso di processo. Se non si trova l'entità desiderata, assicurarsi che nell'entità sia impostata l'opzione flussi del processo di business (campi che verranno creati) nella definizione dell'entità. Non è possibile modificare questa operazione dopo aver salvato il processo.  
  
5. Fare clic su **OK**.  
  
     Viene creato il nuovo processo e la finestra di progettazione del flusso del processo di business si apre con una singola fase già creata.  
  
 ![Finestra flusso del processo di business che Mostra gli elementi principali](media/business-process-flow-window-showing-main-elements.png "Finestra flusso del processo di business che Mostra gli elementi principali")  
  
6. **Aggiungere fasi.** Se gli utenti passeranno da una fase aziendale a un'altra nel processo:  
  
    1.  Trascinare un componente della **fase** dalla scheda **componenti** e rilasciarlo in un segno + nella finestra di progettazione.  
  
        ![Trascinare una fase del processo di business](media/drag-business-process-stage.png "Trascinare una fase del processo di business")  
  
    2.  Per impostare le proprietà di una fase, selezionare la fase, quindi impostare le proprietà nella scheda **Proprietà** sul lato destro della schermata:  
  
        -   Immettere un nome visualizzato.  
  
        -   Se necessario, selezionare una categoria per la fase.  La categoria, ad esempio **idoneo** o **sviluppo**, viene visualizzata come una freccia di espansione nella barra del processo.  
  
            ![Freccia di espansione barra del processo di business](media/business-process-bar-chevron.png "Freccia di espansione barra del processo di business")  
  
        -   Al termine della modifica delle proprietà, selezionare il pulsante **applica** .  
  
7. **Aggiungere passaggi a una fase.** Per visualizzare i passaggi in una fase, selezionare **Details (dettagli** ) nell'angolo in basso a destra della fase. Per aggiungere altri passaggi:  
  
    1.  Trascinare il componente **passaggio** nella fase dalla scheda **componenti** .  
  
        ![Aggiungere un passaggio a una fase in un processo di business](media/add-step-stage-business-process.png "Aggiungere un passaggio a una fase in un processo di business")  
  
    2.  Selezionare il passaggio, quindi impostare le proprietà nella scheda **Proprietà** :  
  
        1.  Immettere un nome visualizzato per il passaggio.  
  
        2.  Se si desidera che gli utenti immettano i dati per completare un passaggio, selezionare il campo appropriato dall'elenco a discesa.  
  
        3.  Selezionare **obbligatorio** se gli utenti devono compilare il campo per completare il passaggio prima di passare alla fase successiva del processo.  
  
        4.  Al termine, selezionare **applica** .  
  
8. **Aggiungere un ramo (condizione) al processo.** Per aggiungere una condizione di diramazione:  
  
    1.  Trascinare il componente **condizione** dalla scheda **componenti** in un segno + tra due fasi.  
  
        ![Aggiungere una condizione a un flusso del processo di business](media/add-condition-business-process-flow.png "Aggiungere una condizione a un flusso del processo di business")  
  
    2.  Selezionare la condizione, quindi impostare le proprietà nella scheda **Proprietà** . Per altre informazioni sulle proprietà di diramazione, vedere [migliorare i flussi dei processi aziendali con la diramazione](enhance-business-process-flows-branching.md). Al termine dell'impostazione delle proprietà per la condizione, selezionare **applica**.  
  
9. **Aggiungere un flusso di lavoro.** Per richiamare un flusso di lavoro:  
  
    1.  Trascinare un componente **del flusso di lavoro** dalla scheda **componenti** in una fase o nell'elemento del **flusso di lavoro globale** nella finestra di progettazione.   Quello a cui si aggiunge l'oggetto dipende dagli elementi seguenti:  
  
       - **Trascinarlo in una fase** quando si desidera attivare il flusso di lavoro all'ingresso o all'uscita della fase. Il componente del flusso di lavoro deve essere basato sulla stessa entità primaria della fase.  
  
       - **Trascinarlo nell'elemento del flusso di lavoro globale** quando si desidera attivare il flusso di lavoro quando il processo viene attivato o quando il processo viene archiviato (quando lo stato diventa **completato** o **abbandonato**). Il componente del flusso di lavoro deve essere basato sulla stessa entità primaria del processo.  
  
    2.  Selezionare il flusso di lavoro, quindi impostare le proprietà nella scheda **Proprietà** :  
  
       1.  Immettere un nome visualizzato.  
  
       2.  Selezionare quando il flusso di lavoro deve essere attivato.  
  
       3.  Cercare un flusso di lavoro attivo su richiesta esistente che corrisponda all'entità stage o creare un nuovo flusso di lavoro selezionando **nuovo**.  
  
       4.  Al termine, selezionare **applica** .  
  
       Per ulteriori informazioni sui flussi di lavoro, vedere [processi del flusso di lavoro](../common-data-service/workflow-processes.md).  
  
10. Per convalidare il flusso del processo di business, selezionare **convalida** sulla barra delle azioni.  
  
11. Per salvare il processo come bozza mentre si continua a utilizzarlo, selezionare **Salva** nella barra delle azioni.  
  
    > [!IMPORTANT]
    >  Finché un processo è una bozza, gli utenti non saranno in grado di usarlo.  
  
12. Per attivare il processo e renderlo disponibile al team, selezionare **attiva** sulla barra delle azioni.  

13. Per fornire il controllo sugli utenti che possono creare, leggere, aggiornare o eliminare l'istanza del flusso del processo di business, selezionare **Modifica ruoli di sicurezza** sulla barra dei comandi della finestra di progettazione. Per i processi relativi ai servizi, ad esempio, è possibile fornire l'accesso completo ai rappresentanti del servizio clienti per modificare l'istanza di flusso del processo di business, ma fornire l'accesso in sola lettura all'istanza per i rappresentanti di vendita, in modo da poter monitorare le attività post-vendite per la loro clienti.

  Nella schermata **ruoli di sicurezza** selezionare il nome di un ruolo per aprire la pagina informazioni sui ruoli di sicurezza. Selezionare la scheda flussi del processo di business e quindi assegnare i privilegi appropriati al flusso del processo di business per un ruolo di sicurezza.

  > [!NOTE]
  > Per impostazione predefinita, l'amministratore di sistema e i ruoli di sicurezza di System verbi possono accedere ai nuovi flussi del processo di business.

   ![Assegnare privilegi a un flusso del processo di business](media/bpf-assign-privileges.png)

  Specificare i privilegi selezionando i pulsanti di opzione appropriati, quindi fare clic su Salva. Per ulteriori informazioni sui privilegi, vedere [privilegi di flusso del processo di business](business-process-flows-overview.md#BKMK_MultipleBPF).

  Quindi, non dimenticare di assegnare il ruolo di sicurezza agli utenti appropriati nell'organizzazione.

> [!TIP] 
>  Ecco alcuni suggerimenti da tenere presenti quando si lavora al flusso attività nella finestra di progettazione:  
>   
> - Per creare uno snapshot di tutti gli elementi nella finestra flusso del processo di business, selezionare **snapshot** sulla barra delle azioni. Questa operazione è utile, ad esempio, se si desidera condividere e ottenere commenti sul processo da un membro del team.  
> - Utilizzare la mini-mappa per spostarsi rapidamente a diverse parti del processo. Questa operazione è utile quando si dispone di un processo complesso che scorre fuori dallo schermo.  
> - Per aggiungere una descrizione per il processo di business, selezionare **Dettagli** sotto il nome del processo nell'angolo sinistro della finestra flusso del processo di business. È possibile utilizzare fino a 2000 caratteri.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Modificare un flusso del processo di business  
 Per modificare i flussi del processo di business, aprire Esplora soluzioni, selezionare **processi**, quindi selezionare il **flusso del processo di business** dall'elenco dei processi che si desidera modificare.  
  
 Quando si seleziona il nome del flusso del processo di business che si desidera modificare dall'elenco dei processi, questo viene aperto nella finestra di progettazione, in cui è possibile effettuare gli aggiornamenti desiderati. Espandere **Details** sotto il nome del processo per rinominarlo o aggiungere una descrizione e visualizzare informazioni aggiuntive.  
  
 ![Sezione dettagli espansa di un flusso del processo di business](media/business-process-flow-details.png "Sezione dettagli espansa di un flusso del processo di business")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Altre informazioni sui flussi del processo di business
 **Modificare le fasi**  
I flussi del processo di business possono avere fino a 30 fasi.    
  
È possibile aggiungere o modificare le proprietà seguenti di una fase:  
  
- **Nome fase**  
  
- **Entità**. È possibile modificare l'entità per qualsiasi fase ad eccezione della prima.  
  
- **Categoria della fase**. Una categoria consente di raggruppare le fasi in base a un tipo di azione. È utile per i report che raggruppano i record in base alla fase in cui si trovano. Le opzioni per la categoria Stage provengono dal set di opzioni globale della categoria stage. Se lo si desidera, è possibile aggiungere opzioni aggiuntive a questo set di opzioni globale e modificare le etichette delle opzioni esistenti. Se lo si desidera, è anche possibile eliminare queste opzioni, ma si consiglia di mantenute le opzioni esistenti. Non sarà possibile aggiungere di nuovo la stessa opzione se viene eliminata. Se non si vuole che vengano usati, modificare l'etichetta in "non usare".  
  
- **Relazione**. Immettere una relazione quando la fase precedente del processo si basa su un'entità diversa. Per la fase attualmente definita, scegliere **Seleziona relazioni** per identificare una relazione da usare quando si esegue il passaggio tra le due fasi. Si consiglia di selezionare una relazione per i vantaggi seguenti:  
  
    -   Per le relazioni sono spesso definite mappe attributi che riportano automaticamente i dati tra record, riducendo al minimo l'immissione di dati.  
  
    -   Quando si seleziona **fase successiva** sulla barra del processo per un record, tutti i record che usano la relazione verranno elencati nel flusso del processo, favorendo così il riutilizzo dei record nel processo. Inoltre, è possibile utilizzare i flussi di lavoro per automatizzare la creazione di record in modo che l'utente lo selezioni semplicemente anziché crearne uno per semplificare ulteriormente il processo.  
  
**Modifica passaggi**  
 Ogni fase può avere fino a 30 passaggi.    
  
**Aggiungi ramo**  
Per informazioni sull'aggiunta di un ramo a una fase, vedere [migliorare i flussi dei processi aziendali con la diramazione](enhance-business-process-flows-branching.md).  
  
Per rendere disponibile un flusso del processo di business affinché gli utenti usino, è necessario ordinare il flusso del processo, abilitare i ruoli di sicurezza e attivarlo.  
  
**Imposta ordine di flusso del processo**  
 Quando si dispone di più di un flusso del processo di business per un'entità (tipo di record), è necessario impostare il processo assegnato automaticamente ai nuovi record. Nella barra dei comandi selezionare **Ordina flusso di elaborazione**. Per i nuovi record o record a cui non è ancora associato un flusso di processo, il primo flusso del processo di business a cui un utente può accedere è quello che verrà usato.  
  
**Abilita ruoli di sicurezza**  
Gli utenti possono accedere a un flusso del processo di business a seconda del privilegio definito nel flusso del processo di business nel ruolo di sicurezza assegnato all'utente. 

Per impostazione predefinita, solo i ruoli di sicurezza **amministratore sistema** e **sistema verbi** possono visualizzare un nuovo flusso del processo di business. 

Per specificare i privilegi per un flusso del processo di business, aprire il flusso del processo di business per la modifica, quindi selezionare **Modifica ruoli di sicurezza** sulla barra dei comandi della finestra di progettazione del flusso del processo di business. Vedere il passaggio 13 in [creare un flusso del processo di business](#create-a-business-process-flow) elencato in precedenza in questo argomento.
  
**Attivare**  
Prima che chiunque possa usare il flusso del processo di business, è necessario attivarlo. Nella barra dei comandi selezionare **attiva**. Una volta confermata l'attivazione, il flusso del processo di business è pronto per l'utilizzo. Se un flusso del processo di business contiene errori, non sarà possibile attivarlo fino a quando non vengono corretti gli errori.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Aggiungere un'azione su richiesta a un flusso del processo di business
L'aggiornamento di Dynamics 365 (online), versione 9,0 introduce una funzionalità di flusso del processo di business: automazione del flusso dei processi di business con passaggi di azione. È possibile aggiungere un pulsante a un flusso del processo di business che attiverà un'azione o un flusso di lavoro.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Aggiungere azioni o flussi di lavoro su richiesta usando un passaggio dell'azione
Si supponga che, nell'ambito del processo di qualificazione dell'opportunità, l'organizzazione Contoso richieda tutte le opportunità di essere esaminate da un revisore designato. Successivamente, l'organizzazione Contoso ha creato un'azione che: 

- Crea un record di attività assegnato al revisore dell'opportunità. 
- Accoda "pronto per la revisione" all'argomento relativo alle opportunità. 

Inoltre, Contoso deve essere in grado di eseguire queste azioni su richiesta. Per integrare queste attività nel processo di qualificazione delle opportunità, le azioni devono essere visualizzate nel flusso del processo di business opportunità. Per abilitare questa funzionalità, selezionare **come passaggio azione flusso del processo di business**.
![disponibile per l'esecuzione come flusso del processo di business.](media/action-available-to-run.png)

Successivamente, il passaggio dell'azione viene aggiunto al flusso del processo di business dell'opportunità di contoso. Il flusso del processo viene quindi convalidato e aggiornato.

![Azione aggiunta al flusso del processo di business opportunità.](media/add-action-to-bpf.png)

A questo punto, i membri del Salesforce di Contoso possono avviare l'azione dal passaggio **qualifica** del processo di business, su richiesta, selezionando **Esegui**.

![Eseguire l'azione.](media/action-execute.png)

> [!IMPORTANT]
> - Per poter eseguire un'azione o un flusso di lavoro su richiesta, il flusso del processo di business deve includere un passaggio dell'azione. Se il passaggio dell'azione esegue un flusso di lavoro, il flusso di lavoro deve essere configurato per l'esecuzione su richiesta.
> - L'entità associata all'azione o al flusso di lavoro deve essere identica a quella associata al flusso del processo di business.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitazione dell'uso dei passaggi dell'azione in un flusso del processo di business

- Le azioni non sono disponibili come passaggi dell'azione se i parametri di input o di output sono tipi Entity, EntityCollection o OptionS (elenco a discesa). Le azioni con più di un parametro di output EntityReference o un numero qualsiasi di parametri di input EntityReference non sono disponibili come passaggi dell'azione. Le azioni non associate a un'entità primaria (azione globale) non sono disponibili come passaggi dell'azione.

## <a name="instant-flows-in-business-process-flows"></a>Flussi istantanei nei flussi del processo di business

È possibile eseguire un **flusso istantaneo** per automatizzare attività ripetitive, generare documenti, tenere traccia delle approvazioni e altro ancora, dall'interno di una fase in un processo di business.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Aggiungere un flusso istantaneo come passaggio di un processo di business

Supponiamo che tu venda le stampanti e usi il **processo lead to Opportunity Sales** per chiudere le offerte. Nell'ambito di questo processo, si desidera che il responsabile del team riveda e approvi le proposte che il team di vendita riunisce in una fase precedente del flusso del processo di business prima di condividerlo con il cliente.

A tale scopo, è necessario eseguire due operazioni:
1. Creare un flusso istantaneo che richiede la revisione e l'approvazione della proposta da parte del team.
1. Aggiungere il flusso istantaneo come passaggio nel **processo lead to Opportunity Sales**.

> [!TIP]
> Solo i [flussi compatibili](https://docs.microsoft.com/flow/overview-solution-flows) con la soluzione possono essere aggiunti come passaggio di un processo di business. 

### <a name="build-an-instant-flow"></a>Creazione di un flusso istantaneo

1. In Microsoft Flow selezionare **soluzioni** nel menu di navigazione.
1. Selezionare **soluzione predefinita** dall'elenco di soluzioni visualizzato. 
1. Selezionare il menu **+ nuovo** , quindi selezionare **flusso** dall'elenco visualizzato.
1. Cercare e quindi selezionare il connettore **Common Data Service** .
1. Cercare e quindi selezionare il trigger **quando un record è selezionato** nell'elenco dei trigger **Common Data Service** .
1. Impostare **ambiente** su **predefinito**e quindi impostare **nome entità** in modo da **condurre il processo vendite opportunità**.
1. Aggiungere un campo di input di testo per l'utente per immettere il collegamento alla proposta.

   ![Trigger di flusso istantaneo](media/instant-flow-trigger.png "Trigger di flusso istantaneo")

   Sono necessarie informazioni dell'istanza del flusso del processo di business per fornire il contesto per la richiesta di approvazione, quindi seguire questa procedura per eseguire questa operazione.

1. Aggiungere l'azione **analizza JSON** . 
1. Per impostare il **contenuto** su **entità** , selezionarlo nell'elenco dei valori dinamici per il trigger **quando è selezionato un record** .
1. Incollare il contenuto seguente nel campo **schema** .

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   L'aspetto dovrebbe essere simile al seguente:

   ![Analizza JSON](media/instant-flow-json-date.png "Analizza JSON")

  1. Aggiungere l'azione **Ottieni record** dal connettore **Common Data Service** .
  1. Impostare **Environment** su **(Current)** , **nome entità** per **condurre il processo Sales opportunity**e l' **identificatore dell'elemento** a **BPFFlowStageEntityRecordID**.

     ![Aggiungere un record](media/instant-flow-add-record.png)

     Ora che sono disponibili i dati, definire il processo di approvazione aggiungendo l'azione **Avvia e attendi un'approvazione (v2)** e quindi inserendo le informazioni rilevanti. Se non si ha familiarità, vedere altre informazioni sulle [approvazioni]( sequential-modern-approvals.md) .

     > [!TIP]
     > - Usare la selezione contenuto dinamico per aggiungere campi dall'azione **Ottieni record** per aggiungere informazioni rilevanti alla richiesta di approvazione, in modo che i responsabili approvazione possano conoscere facilmente la richiesta. 
     > - Per fornire un contesto ulteriore per la fase attiva in cui si trova il processo di business, aggiungere il campo **BPFActiveStageLocalizedName** dall'elenco di valori dinamici.

     La scheda **Avvia e attendi un'approvazione (v2)** potrebbe avere un aspetto simile al seguente:

      ![Scheda di approvazione](media/instant-flow-add-approval-action.png)

1. Infine, salvare il flusso e quindi attivarlo.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Aggiungere questo flusso come passaggio nel processo lead to Opportunity Sales.

Ora che è stato creato il flusso istantaneo, è sufficiente aggiungerlo al flusso del processo di business. 

1. Aprire il **processo lead to Opportunity Sales** nella finestra di progettazione del flusso del processo di business. 
1. Trascinare e rilasciare il **passaggio del flusso (anteprima)** dall'elenco di **componenti** nella fase **proposto** .
1. Selezionare quindi l'icona di ricerca nel campo **Seleziona un flusso** per elencare tutti i flussi che è possibile aggiungere a un flusso del processo di business.
1. Selezionare un flusso dall'elenco e quindi salvare le modifiche selezionando il pulsante **applica** nella parte inferiore del riquadro proprietà.
1. Infine, selezionare il pulsante **Aggiorna** per fare in modo che questo processo di business scorra con il nuovo passaggio di flusso istantaneo disponibile per gli utenti.
  
## <a name="next-steps"></a>Passaggi successivi

 - [Panoramica sui flussi del processo di business](business-process-flows-overview.md)  
 - [Migliorare i flussi di processi aziendali con la diramazione](enhance-business-process-flows-branching.md)
 - [Panoramica delle approvazioni](sequential-modern-approvals.md)
 - [Procedura dettagliata per l'aggiunta di un flusso istantaneo a un flusso del processo di business](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


