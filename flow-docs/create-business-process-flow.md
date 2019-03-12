---
title: Creare un processo aziendale in PowerApps | MicrosoftDocs
description: Informazioni su come creare un processo aziendale
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 33ae71ea6b0af6a94021f5b0a02690aae21f0043
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57463063"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Esercitazione: Creare un processo aziendale per la standardizzazione dei processi

Questa esercitazione illustra come creare un processo aziendale con PowerApps. Per altre informazioni sui motivi di utilizzo dei processi aziendali, vedere [Panoramica dei processi aziendali](business-process-flows-overview.md). Per informazioni sulla creazione di un flusso di attività per dispositivi mobili, vedere [Creare un flusso di attività per dispositivi mobili](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Quando un utente avvia un processo aziendale, le fasi e i passaggi del processo sono visualizzati nella barra del processo nella parte superiore di un modulo:  
  
 ![Processo aziendale con fasi](media/business-process-stages.png "Processo aziendale con fasi")  
  
 > [!TIP]
 >  Dopo aver creato la definizione di un processo aziendale, è possibile offrire il controllo su chi può creare, leggere, aggiornare o eliminare l'istanza del processo aziendale. Ad esempio, per i processi di assistenza, è possibile fornire accesso completo agli operatori del servizio clienti per la modifica dell'istanza del processo aziendale e fornire accesso di sola lettura per l'istanza ai rappresentanti per consentire loro di monitorare le attività post-vendita dei clienti. Per impostare la sicurezza per la definizione di un processo aziendale creato, selezionare **Abilita ruoli di sicurezza** sulla barra delle azioni.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Prerequisiti

È necessario [Flow - Piano 2](https://preview.flow.microsoft.com/pricing/) per creare flussi di processi aziendali. Alcuni piani di licenza di Dynamics 365 includono Flow - Piano 2.

## <a name="create-a-business-process-flow"></a>Creare un processo aziendale  
  
1. Aprire [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. Nel riquadro di spostamento a sinistra selezionare **Processi**. 
  
3.  Nella barra degli strumenti **Azioni** selezionare **Nuovo**.  
  
4.  Nella finestra di dialogo **Crea processo** compilare i campi obbligatori:  
  
    -   Immettere un nome di processo. Il nome del processo non deve essere univoco, ma deve essere significativo per gli utenti che necessitano di scegliere un processo. Il nome può essere modificato in un secondo momento.  
  
    -   Nell'elenco **Categoria** selezionare **Processo aziendale**.  
  
         Non è possibile modificare la categoria dopo aver creato il processo.  
  
    -   Nell'elenco **Entità** selezionare l'entità su cui si vuole basare il processo.  
  
         L'entità selezionata ha effetto sui campi disponibili per i passaggi che possono essere aggiunti alla prima fase del flusso del processo. Se non viene trovata l'entità desiderata, verificare che l'opzione Processi aziendali (i campi verranno creati) dell'entità sia impostata nella definizione dell'entità. Non è possibile apportare modifiche dopo aver salvato il processo.  
  
5. Selezionare **OK**.  
  
     Viene creato il nuovo processo e viene visualizzata la finestra di progettazione dei processi aziendali con una sola fase già creata.  
  
 ![Finestra del processo aziendale che mostra gli elementi principali](media/business-process-flow-window-showing-main-elements.png "Finestra del processo aziendale che mostra gli elementi principali")  
  
6. **Aggiungere le fasi.** Se gli utenti avanzeranno da una fase all'altra del processo aziendale:  
  
    1.  Trascinare un componente **Fase** dalla scheda **Componenti** e rilasciarlo sul segno più (+) nella finestra di progettazione.  
  
        ![Trascinare una fase del processo aziendale](media/drag-business-process-stage.png "Trascinare una fase del processo aziendale")  
  
    2.  Per impostare le proprietà di una fase, selezionare la fase e quindi impostare le proprietà nella scheda **Proprietà** nella parte destra della schermata:  
  
        -   Immettere un nome visualizzato.  
  
        -   Se si desidera, selezionare una categoria per la fase.  La categoria, ad esempio **Qualifica** o **Sviluppa**, viene visualizzata come freccia di espansione nella barra del processo.  
  
            ![Freccia di espansione della barra del processo aziendale](media/business-process-bar-chevron.png "Freccia di espansione della barra del processo aziendale")  
  
        -   Dopo aver modificato le proprietà, selezionare il pulsante **Applica**.  
  
7. **Aggiungere i passaggi a una fase.** Per visualizzare i passaggi di una fase, selezionare **Dettagli** nell'angolo inferiore destro della fase. Per aggiungere altri passaggi:  
  
    1.  Trascinare il componente **Passaggio** nella fase della scheda **Componenti**.  
  
        ![Aggiungere un passaggio a una fase di un processo aziendale](media/add-step-stage-business-process.png "Aggiungere un passaggio a una fase di un processo aziendale")  
  
    2.  Selezionare il passaggio e quindi impostare le proprietà nella scheda **Proprietà**:  
  
        1.  Immettere un nome visualizzato per il passaggio.  
  
        2.  Se si vuole che gli utenti immettano i dati per completare la fase, selezionare il campo appropriato dall'elenco a discesa.  
  
        3.  Selezionare **Obbligatorio** se gli utenti devono immettere un valore nel campo per completare il passaggio prima di passare alla fase successiva del processo.  
  
        4.  Al termine, selezionare **Applica**.  
  
8. **Aggiungere un ramo (condizione) al processo.** Per aggiungere una condizione per la creazione dei rami:  
  
    1.  Trascinare il componente **Condizione** dalla scheda **Componenti** a un segno più (+) tra due fasi.  
  
        ![Aggiungere una condizione a un processo aziendale](media/add-condition-business-process-flow.png "Aggiungere una condizione a un processo aziendale")  
  
    2.  Selezionare la condizione e quindi impostare le proprietà nella scheda **Proprietà**. Per altre informazioni sulle proprietà della creazione dei rami, vedere [Migliorare i processi aziendali con la creazione dei rami](enhance-business-process-flows-branching.md). Dopo aver impostato le proprietà per la condizione, selezionare **Applica**.  
  
9. **Aggiungere un flusso di lavoro.** Per richiamare un flusso di lavoro:  
  
    1.  Trascinare un componente **Flusso di lavoro** dalla scheda **Componenti** a una fase o all'elemento **Flusso di lavoro globale** nella finestra di progettazione.   L'elemento a cui aggiungere il componente viene determinato nel modo seguente:  
  
       - **Trascinare il componente in una fase** quando si vuole attivare il flusso di lavoro all'inizio o alla fine della fase. Il componente del flusso di lavoro deve essere basato sulla stessa entità primaria della fase.  
  
       - **Trascinare il componente nell'elenco Flusso di lavoro globale** quando si vuole attivare il flusso di lavoro nel momento in cui il processo viene attivato o archiviato (quando lo stato diventa **Completato** o **Abbandonato**). Il componente del flusso di lavoro deve essere basato sulla stessa entità primaria del processo.  
  
    2.  Selezionare il flusso di lavoro e quindi impostare le proprietà nella scheda **Proprietà**:  
  
       1.  Immettere un nome visualizzato.  
  
       2.  Selezionare quando deve essere attivato il flusso di lavoro.  
  
       3.  Cercare un flusso di lavoro su richiesta attivo esistente che corrisponde all'entità della fase oppure creare un nuovo flusso di lavoro selezionando **Nuovo**.  
  
       4.  Al termine, selezionare **Applica**.  
  
       Per altre informazioni sui flussi di lavoro, vedere [Processi del flusso di lavoro](../common-data-service/workflow-processes.md).  
  
10. Per convalidare il processo aziendale, selezionare **Convalida** sulla barra delle azioni.  
  
11. Per salvare il processo come bozza pur continuando a lavorare su di esso, selezionare **Salva** nella barra delle azioni.  
  
    > [!IMPORTANT]
    >  Fino a quando il processo è una bozza, gli utenti non potranno utilizzarlo.  
  
12. Per attivare il processo e renderlo disponibile per il team, selezionare **Attiva** sulla barra delle azioni.  

13. Per offrire il controllo sugli utenti che possono creare, leggere, aggiornare o eliminare l'istanza del processo aziendale, selezionare **Modifica ruoli di sicurezza** sulla barra dei comandi della finestra di progettazione. Ad esempio, per i processi di assistenza, è possibile fornire accesso completo agli operatori del servizio clienti per la modifica dell'istanza del processo aziendale e fornire accesso di sola lettura per l'istanza ai rappresentanti per consentire loro di monitorare le attività post-vendita dei clienti.

  Nella schermata **Ruoli di sicurezza** selezionare il nome di un ruolo per aprire la pagina di informazioni del ruolo di sicurezza. Selezionare la scheda Processi aziendali e quindi assegnare i privilegi appropriati nel processo aziendale per un ruolo di sicurezza.

  > [!NOTE]
  > I ruoli di sicurezza Amministratore di sistema e Addetto personalizzazione sistema hanno accesso ai nuovi processi aziendali per impostazione predefinita.

   ![Assegnare i privilegi a un processo aziendale](media/bpf-assign-privileges.png)

  Specificare i privilegi selezionando i pulsanti di opzione appropriati e facendo clic su Salva. Per altre informazioni sui privilegi, vedere [Privilegi del processo aziendale](business-process-flows-overview.md#BKMK_MultipleBPF).

  Successivamente, non dimenticare di assegnare il ruolo di sicurezza agli utenti appropriati nell'organizzazione.

> [!TIP] 
>  Di seguito sono riportati alcuni suggerimenti da tenere presente mentre si usa il flusso di attività nella finestra di progettazione:  
>   
> - Per acquisire uno snapshot di tutti gli elementi della finestra del processo aziendale, selezionare **Snapshot** sulla barra delle azioni. Questa operazione è utile ad esempio quando si vuole condividere e visualizzare i commenti sul processo di un membro del team.  
> - Usare la minimappa per passare rapidamente nelle diverse parti del processo. Questa operazione è utile nel caso di un processo complesso che fuoriesce dalla schermata.  
> - Per aggiungere una descrizione per il processo aziendale, selezionare **Dettagli** sotto il nome del processo nell'angolo sinistro della finestra del processo aziendale. È possibile usare un massimo di 2000 caratteri.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Modificare un processo aziendale  
 Per modificare i processi aziendali, aprire Esplora soluzioni, selezionare **Processi** e quindi selezionare il **Processo aziendale** dall'elenco dei processi che si vuole modificare.  
  
 Quando si seleziona il nome del processo aziendale da modificare dall'elenco dei processi, viene aperta la finestra di progettazione nella quale è possibile apportare le modifiche desiderate. Espandere **Dettagli** sotto il nome del processo per rinominarlo o aggiungere una descrizione e visualizzare informazioni aggiuntive.  
  
 ![Sezione dei dettagli di un processo aziendale espansa](media/business-process-flow-details.png "Sezione dei dettagli di un processo aziendale espansa")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Altre informazioni i sui processi aziendali
 **Modificare le fasi**  
I processi aziendali possono includere un massimo di 30 fasi.    
  
È possibile aggiungere o modificare le seguenti proprietà di una fase:  
  
- **Nome fase**  
  
- **Entità**. È possibile modificare l'entità di qualsiasi fase, ad eccezione della prima.  
  
- **Categoria fase**. Una categoria consente di raggruppare le fasi per tipo di azione. La categoria è utile per raggruppare i report in base alla fase cui appartengono. Le opzioni per la categoria di fase provengono dal set di opzioni globali Categoria fase. È possibile aggiungere altre opzioni al set di opzioni globali e, facoltativamente, modificare le etichette delle opzioni esistenti. Sebbene sia possibile anche eliminare le opzioni, è consigliabile mantenere le opzioni esistenti. Se si elimina un'opzione, non sarà possibile aggiungere di nuovo la stessa opzione. Se non si vuole che le opzioni venga usate, modificarne l'etichetta in ”Non usare”.  
  
- **Relazione**. Immettere una relazione quando la fase precedente del processo è basata su un'entità diversa. Per la fase attualmente in definizione, scegliere **Seleziona relazioni** per identificare una relazione da usare durante il passaggio da una fase all'altra. È consigliabile selezionare una relazione per i vantaggi seguenti:  
  
    -   Le relazioni includono spesso mapping di attributi definiti in base ai quali i dati vengono trasferiti automaticamente da un record all'altro, riducendo l'immissione dei dati.  
  
    -   Quando si seleziona **Fase successiva** sulla barra del processo per un record, tutti i record che usano la relazione appariranno nel flusso del processo, favorendo in questo modo il riutilizzo dei record nel processo. È anche possibile usare i flussi di lavoro per automatizzare la creazione dei record in modo che l'utente possa semplicemente selezionare il record anziché crearne uno per semplificare ulteriormente il processo.  
  
**Modificare i passaggi**  
 Ogni fase può avere un massimo di 30 passaggi.    
  
**Aggiungere un ramo**  
Per informazioni sull'aggiunta di un ramo a una fase, vedere [Migliorare i processi aziendali con la creazione dei rami](enhance-business-process-flows-branching.md).  
  
Per rendere disponibile un processo aziendale per gli utenti, è necessario ordinare il flusso del processo, abilitare i ruoli di sicurezza e attivarlo.  
  
**Impostare l'ordine del flusso di processo**  
 Quando sono presenti più processi aziendali per un'entità (tipo di record), è necessario specificare il processo da assegnare automaticamente ai nuovi record. Nella barra dei comandi selezionare **Flusso di elaborazione ordine**. Per i nuovi record o i record a cui non è ancora stato assegnato un flusso di processo, il primo processo aziendale a cui l'utente ha accesso corrisponde al flusso che verrà usato.  
  
**Abilitare i ruoli di sicurezza**  
L'accesso degli utenti a un processo aziendale dipende dal privilegio definito nel processo aziendale nel ruolo di sicurezza assegnato all'utente. 

Per impostazione predefinita, soltanto i ruoli **Amministratore di sistema** e **Addetto personalizzazione sistema** possono visualizzare un nuovo processo aziendale. 

Per specificare i privilegi in un processo aziendale, aprire il processo aziendale per la modifica e quindi selezionare **Modifica ruoli di sicurezza** sulla barra dei comandi della finestra di progettazione del processo aziendale. Vedere il passaggio 13 in [Creare un processo aziendale](#create-a-business-process-flow) descritto in precedenza in questo argomento.
  
**Attivare**  
Per consentire l'uso del processo aziendale, è necessario attivarlo. Nella barra dei comandi selezionare **Attiva**. Dopo aver confermato l'attivazione, il processo aziendale è pronto per l'uso. Se un processo aziendale include errori, non è possibile attivarlo fino a quando gli errori non vengono corretti.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Aggiungere un'azione su richiesta a un processo aziendale
L'aggiornamento di Dynamics 365 versione 9.0 (online) introduce una funzionalità del processo aziendale: l'automazione del processo aziendale con passaggi di azione. È possibile aggiungere un pulsante a un processo aziendale che attiva un'azione o un flusso di lavoro.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Aggiungere flussi di lavoro o azioni su richiesta usando un passaggio di azione
Si supponga che, come parte del processo di qualificazione delle opportunità, l'organizzazione Contoso richieda la revisione di tutte le opportunità da parte di un revisore specificato. Successivamente, l'organizzazione Contoso ha creato un'azione che: 

- Crea un record di attività che viene assegnato al revisore opportunità. 
- Aggiunge "Pronto per la revisione" all'argomento dell'opportunità. 

Contoso deve anche essere in grado di eseguire queste azioni su richiesta. Per integrare queste attività nel processo di qualificazione delle opportunità, è necessario che le azioni siano visualizzate nel processo aziendale dell'opportunità. Per abilitare questa funzionalità, selezionare **Come un passaggio di azione del processo aziendale**.
![Disponibile per l'esecuzione come processo aziendale.](media/action-available-to-run.png)

Il passaggio di azione viene quindi aggiunto al processo aziendale dell'opportunità di Contoso. Il flusso del processo viene quindi convalidato e aggiornato.

![Azione aggiunta al processo aziendale dell'opportunità.](media/add-action-to-bpf.png)

I membri del team di Contoso possono ora avviare l'azione dal passaggio del processo aziendale **Qualifica opportunità**, su richiesta, selezionando **Esegui**.

![Eseguire l'azione.](media/action-execute.png)

> [!IMPORTANT]
> - Per poter eseguire un'azione o un flusso di lavoro su richiesta, il processo aziendale deve includere un passaggio di azione. Se il passaggio di azione esegue un flusso di lavoro, è necessario configurare il flusso di lavoro per l'esecuzione su richiesta.
> - L'entità associata all'azione o al flusso di lavoro deve corrispondere all'entità associata al processo aziendale.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitazione all'uso dei passaggi di azione in un processo aziendale

- Le azioni non sono disponibili come passaggi di azione se i parametri di input o output sono tipi Entity, EntityCollection o OptionSet (elenco a discesa). Le azioni con più parametri di output EntityReference o qualsiasi numero di parametri di input EntityReference non sono disponibili come passaggi di azione. Le azioni non associate a un'entità primaria (azione globale) non sono disponibili come passaggi di azione.

  
## <a name="next-steps"></a>Passaggi successivi  
 [Panoramica sui processi aziendali](business-process-flows-overview.md) </br>   
 [Migliorare i processi aziendali con la creazione dei rami](enhance-business-process-flows-branching.md)

