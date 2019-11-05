---
title: Flussi di lavoro di Common Data Service classici | MicrosoftDocs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 42ac7bd75268010a8d7e2bf88a600621504dda39
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548325"
---
# <a name="classic-common-data-service-workflows"></a>Flussi di lavoro di Common Data Service classici 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I flussi di lavoro automatizzano i processi aziendali senza un'interfaccia utente. Le persone usano in genere i processi di flusso di lavoro per avviare l'automazione che non richiede alcuna interazione con l'utente.

> [!IMPORTANT]
> Usare i flussi anziché i flussi di lavoro classici per automatizzare i processi aziendali. Altre informazioni: [sostituire i flussi di lavoro di Common Data Service classici con i flussi](replace-workflows-with-flows.md)  
  
 Ogni processo del flusso di lavoro è associato a una singola entità. Quando si configurano i flussi di lavoro, è necessario considerare quattro aree principali:  
  
-   Quando avviarli?  
  
-   Devono essere eseguiti come flusso di lavoro in tempo reale o come flusso di lavoro in background?  
  
-   Quali azioni devono essere eseguite?  
  
-   In quali condizioni devono essere eseguite le azioni?  
  
 In questo argomento viene illustrato come trovare i processi del flusso di lavoro e viene descritto quando avviarli e se devono essere eseguiti come in tempo reale o in background. Per informazioni sulle azioni che devono eseguire e sulle condizioni, vedere Configurazione dei [processi del flusso di lavoro](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Dove si personalizzano i processi del flusso di lavoro?  
 È possibile visualizzare i flussi di lavoro all'interno dell'organizzazione visualizzando il nodo **processi** nella **soluzione predefinita** e filtrando i processi che dispongono del **flusso di lavoro**di **categoria** .  
  
 ![Processi filtrati in base al flusso di lavoro in Dynamics 365](media/workflow-processes-filtered.PNG "Processi filtrati in base al flusso di lavoro in Dynamics 365")  
  
 A seconda del modo in cui viene compilata l'app, gli utenti possono creare o modificare i flussi di lavoro nell'app. 
 
Gli sviluppatori possono creare flussi di lavoro usando le informazioni contenute nel [Common Data Service Guida](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) per gli sviluppatori e le soluzioni acquistate possono includere flussi di lavoro che è possibile modificare.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Proprietà del flusso di lavoro  
 In Esplora soluzioni selezionare **processi** , quindi fare clic su **nuovo**.  
  
 Quando si crea un flusso di lavoro, nella finestra di dialogo **Crea processo** è necessario impostare tre proprietà che tutti i processi hanno:  
  
 ![Creazione di un flusso di lavoro in Dynamics 365](media/create-workflow.PNG "Creazione di un flusso di lavoro in Dynamics 365")  
  
 **Nome processo**  
 Non è necessario che il nome del processo del flusso di lavoro sia univoco, ma se si prevede di avere un numero elevato di flussi di lavoro, è consigliabile utilizzare una convenzione di denominazione per distinguere chiaramente i processi. È possibile che si desideri applicare i prefissi standard al nome del flusso di lavoro. Il prefisso può descrivere la funzione del flusso di lavoro o del reparto all'interno dell'azienda. In questo modo sarà possibile raggruppare elementi simili nell'elenco dei flussi di lavoro.  
  
 **Categoria**  
 Questa proprietà stabilisce che si tratta di un processo del flusso di lavoro.  
  
 **Entità**  
 Ogni processo del flusso di lavoro deve essere impostato su una singola entità. Non è possibile modificare l'entità dopo la creazione del processo del flusso di lavoro.  
  
 **Esegui questo flusso di lavoro in background (scelta consigliata)**  
 Questa opzione viene visualizzata quando si seleziona flusso di lavoro come categoria. Questa impostazione determina se il flusso di lavoro è un flusso di lavoro in tempo reale o in background. I flussi di lavoro in tempo reale vengono eseguiti immediatamente in modo sincrono e i flussi di lavoro in background vengono eseguiti in modo asincrono. Le opzioni di configurazione disponibili variano a seconda della scelta effettuata per questa impostazione. I flussi di lavoro in background consentono condizioni di attesa che non sono disponibili per i flussi di lavoro in tempo reale. Fino a quando non si usano tali condizioni di attesa, in un secondo momento è possibile convertire i flussi di lavoro in background in flussi di lavoro in tempo reale e flussi di lavoro in tempo reale in flussi di lavoro in background. Per ulteriori informazioni sulle condizioni di attesa, vedere [impostazione delle condizioni per le azioni del flusso di lavoro](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 È **anche possibile specificare** se creare un nuovo flusso di lavoro da zero o scegliere di iniziare da un modello esistente. Quando si sceglie **nuovo processo da un modello esistente (Select from list)** , è possibile scegliere tra i processi di flussi di lavoro disponibili salvati in precedenza come modello di processo.  
  
 Dopo aver creato il flusso di lavoro o averne modificato uno esistente, si avranno le proprietà aggiuntive seguenti:  
  
 ![Scheda generale in un flusso di lavoro](media/create-workflow-general-tab.PNG "Scheda generale in un flusso di lavoro")  
  
 **Attiva come**  
 È possibile scegliere il **modello di processo** per creare un punto di partenza avanzato per altri modelli. Se si sceglie questa opzione, dopo aver attivato il flusso di lavoro non verrà applicato, ma sarà disponibile per la selezione nella finestra di dialogo **Crea processo** se si seleziona **tipo**: **nuovo processo da un modello esistente (Seleziona da elenco)**  
  
 I modelli di processo risultano utili quando si dispone di una serie di processi del flusso di lavoro simili e si desidera definirli senza duplicare la stessa logica.  
  
> [!NOTE]
>  La modifica di un modello di processo non comporta la modifica dei comportamenti di altri processi del flusso di lavoro creati in precedenza utilizzandoli come modello. Un nuovo flusso di lavoro creato usando un modello è una copia del contenuto nel modello.  
  
 **Disponibile per l'esecuzione**  
 Questa sezione contiene opzioni che descrivono come il flusso di lavoro è disponibile per l'esecuzione.  
  
 **Esegui questo flusso di lavoro in background (scelta consigliata)**  
 Questa casella di controllo riflette l'opzione selezionata durante la creazione del flusso di lavoro. Questa opzione è disabilitata, ma è possibile modificarla dal menu **azioni** scegliendo **Converti in un flusso di lavoro in tempo reale** o **Converti in un flusso di lavoro in background**.  
  
 **Come processo su richiesta**  
 Scegliere questa opzione se si desidera consentire agli utenti di eseguire il flusso di lavoro dal comando **Esegui flusso di lavoro** .  
  
 **Come processo figlio**  
 Scegliere questa opzione se si desidera consentire l'avvio del flusso di lavoro da un altro flusso di lavoro.  
  
 **Conservazione del processo del flusso di lavoro**  
 Questa sezione contiene un'opzione per eliminare un flusso di lavoro dopo il completamento dell'esecuzione del flusso di lavoro.  
  
 **Elimina automaticamente i processi del flusso di lavoro completati (per risparmiare spazio su disco)**  
 Scegliere questa opzione se si desidera che un processo del flusso di lavoro completato venga eliminato automaticamente.  
  
> [!NOTE]
>  I processi del flusso di lavoro non vengono eliminati immediatamente al completamento, ma subito dopo, tramite un processo batch.  
  
 **Ambito**  
 Per le entità di proprietà dell'utente, le opzioni sono **organizzazione**, **padre: business unit figlio**, **Business Unit**o **utente**. Per le entità di proprietà dell'organizzazione l'unica opzione è **Organization**.  
  
 Se l'ambito è **Organization**, la logica del flusso di lavoro può essere applicata a qualsiasi record dell'organizzazione. In caso contrario, il flusso di lavoro può essere applicato solo a un subset di record che rientrano nell'ambito.  
  
> [!NOTE]
>  Il valore di ambito predefinito è **User**. Assicurarsi di verificare che il valore di ambito sia appropriato prima di attivare il flusso di lavoro.  
  
 **Inizia quando**  
 Utilizzare le opzioni in questa sezione per specificare quando un flusso di lavoro deve essere avviato automaticamente. È possibile configurare un flusso di lavoro in tempo reale da eseguire prima di determinati eventi. Si tratta di una funzionalità molto potente perché il flusso di lavoro può arrestare l'azione prima che si verifichi. Altre informazioni: [uso dei flussi di lavoro in tempo reale](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Sono disponibili le opzioni seguenti:  
  
- **Il record viene creato**  
  
- **Registrare le modifiche dello stato**  
  
- **Record assegnato**  
  
- **Modifica campi di record**  
  
- **Il record è stato eliminato**  
  
> [!NOTE]
>  Tenere presente che le azioni e le condizioni definite per il flusso di lavoro non sono in grado di riconoscere quando viene eseguito il flusso di lavoro. Se, ad esempio, si definisce un flusso di lavoro per l'aggiornamento del record, questa azione non può essere eseguita da un flusso di lavoro in tempo reale prima che il record venga creato. Non è possibile aggiornare un record che non esiste. Analogamente, un flusso di lavoro in background non può aggiornare un record che è stato eliminato, anche se è possibile definire questa azione per il flusso di lavoro. Se si configura un flusso di lavoro per eseguire un'azione che non può essere eseguita, l'operazione avrà esito negativo e l'intero flusso di lavoro avrà esito negativo.  
  
 **Esegui come**  
 Questa opzione è disponibile solo se è stata deselezionata l'opzione **Esegui flusso di lavoro in background (scelta consigliata)** quando è stato creato il flusso di lavoro o se in seguito si è convertito un flusso di lavoro in background in un flusso di lavoro in tempo reale.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contesto di sicurezza dei processi del flusso di lavoro  
 Quando un flusso di lavoro in background viene configurato come processo su richiesta e viene avviato da un utente tramite il comando **Esegui flusso di lavoro** , le azioni che il flusso di lavoro può eseguire sono limitate a quelle che l'utente può eseguire in base ai privilegi e ai livelli di accesso definiti da i ruoli di sicurezza impostati per l'account utente.  
  
 Quando un flusso di lavoro in background viene avviato in base a un evento, il flusso di lavoro funziona nel contesto della persona che lo possiede, in genere la persona che ha creato il flusso di lavoro.  
  
 Per i flussi di lavoro in tempo reale è presente l'opzione **Execute As** ed è possibile scegliere se il flusso di lavoro deve applicare il contesto di sicurezza del proprietario del flusso di lavoro o l'utente che ha apportato modifiche al record. Se il flusso di lavoro include azioni che non possono essere eseguite da tutti gli utenti in base ai vincoli di sicurezza, è necessario scegliere di eseguire il flusso di lavoro come proprietario del flusso di lavoro.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Attivare un flusso di lavoro  
 I flussi di lavoro possono essere modificati solo quando vengono disattivati. Prima che un flusso di lavoro possa essere utilizzato manualmente o venga applicato a causa di eventi da attivare. Per poter attivare un flusso di lavoro, è necessario che contenga almeno un passaggio. Per informazioni sulla configurazione dei passaggi, vedere [configurazione dei processi del flusso di lavoro](configure-workflow-steps.md)  
  
 Un flusso di lavoro può essere attivato o disattivato solo dal proprietario del flusso di lavoro o da un **utente con Act per conto di un altro privilegio utente** , ad esempio l'amministratore di sistema.  Il motivo è che un utente malintenzionato potrebbe modificare il flusso di lavoro di un utente senza che sia consapevole della modifica. È possibile riassegnare un flusso di lavoro di cui si è proprietari cambiando il proprietario. Questo campo si trova nella scheda **Amministrazione** . Se non si è l'amministratore di sistema ed è necessario modificare un flusso di lavoro di proprietà di un altro utente, è necessario disattivarlo e assegnarlo all'utente. Al termine della modifica del flusso di lavoro, è possibile assegnarlo di nuovo in modo che possa attivarlo.  
  
 I flussi di lavoro in tempo reale richiedono che l'utente disponga del privilegio **attiva processi in tempo reale** . Poiché i flussi di lavoro in tempo reale hanno un maggiore rischio di influire sulle prestazioni del sistema, è necessario assegnare questo privilegio solo agli utenti che possono valutare il rischio potenziale.  
  
 I flussi di lavoro vengono salvati quando vengono attivati, pertanto non è necessario salvarli prima di attivarli.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Configurazione dei processi del flusso di lavoro](configure-workflow-steps.md)  <br/>
[Aggiungere un flusso di lavoro su richiesta a un flusso del processo di business](bpf-add-on-demand-workflow.md) 

