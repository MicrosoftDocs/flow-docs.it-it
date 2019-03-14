---
title: Flussi di lavoro classici di Common Data Service (CDS) per le app | MicrosoftDocs
ms.custom: ''
ms.date: 08/06/2018
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
ms.openlocfilehash: 5f3e2145741c96d20f73ff74f5fd6cc6c1cbb52e
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462911"
---
# <a name="classic-common-data-service-cds-for-apps-workflows"></a>Flussi di lavoro classici di Common Data Service (CDS) per le app 

I flussi di lavoro automatizzano i processi aziendali senza un'interfaccia utente. Gli utenti usano in genere i processi del flusso di lavoro per avviare un'automazione che non richiede alcuna interazione dell'utente.  
  
 Ogni processo del flusso di lavoro è associato a una singola entità. Quando si configurano i flussi di lavoro è necessario prendere in considerazioni quattro aree principali:  
  
-   Quando avviare i flussi?  
  
-   I flussi devono essere eseguiti come flussi in tempo reale o in background?  
  
-   Quali azioni devono eseguire?  
  
-   In quali condizioni devono essere eseguite le azioni?  
  
 Questo argomento descrive come individuare i processi del flusso di lavoro, quando avviarli e se eseguirli in tempo reale o in background. Per informazioni sulle azioni che devono essere eseguite dai flussi e sulle condizioni, vedere [Configurazione dei processi del flusso di lavoro](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Dove si personalizzano i processi del flusso di lavoro?  
 È possibile visualizzare i flussi di lavoro dell'organizzazione visualizzando il nodo **Processi** nella **Soluzione predefinita** e applicando un filtro ai processi con **Categoria** **Flusso di lavoro**.  
  
 ![Processi filtrati in base al flusso di lavoro in Dynamics 365](media/workflow-processes-filtered.PNG "Processi filtrati in base al flusso di lavoro in Dynamics 365")  
  
 A seconda del modo in cui è compilata l'app, gli utenti possono creare o modificare i flussi di lavoro nell'app. 
 
Gli sviluppatori possono creare flussi di lavoro usando le informazioni incluse in [Dynamics 365 Customer Engagement Developer Guide](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-guide) (Guida per sviluppatori di Dynamics 365 Customer Engagement) e le soluzioni acquistate possono includere flussi di lavoro che è possibile modificare.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Proprietà del flusso di lavoro  
 In Esplora soluzioni selezionare **Processi** e fare clic su **Nuovo**.  
  
 Quando si crea un flusso di lavoro la finestra di dialogo **Crea processo** richiede di impostare tre proprietà presenti in tutti i processi:  
  
 ![Creazione di un flusso di lavoro in Dynamics 365](media/create-workflow.PNG "Creazione di un flusso di lavoro in Dynamics 365")  
  
 **Nome processo**  
 Sebbene il nome del processo del flusso di lavoro non debba essere univoco, se si prevede di avere numerosi flussi di lavoro, è possibile usare una convenzione di denominazione per differenziare in modo chiaro i processi. È possibile applicare prefissi standard al nome del flusso di lavoro. Il prefisso può descrivere la funzione del flusso di lavoro o il reparto all'interno della società. Ciò consentirà di raggruppare gli elementi simili nell'elenco dei flussi di lavoro.  
  
 **Categoria**  
 Questa proprietà definisce il processo come processo del flusso di lavoro.  
  
 **Entità**  
 Ogni processo del flusso di lavoro deve essere impostato su una singola entità. L'entità non può essere modificata dopo aver creato il processo del flusso di lavoro.  
  
 **Esegui flusso di lavoro in background (scelta consigliata)**  
 Questa opzione viene visualizzata quando si seleziona Flusso di lavoro come categoria. Questa impostazione determina se il flusso di lavoro è un flusso di lavoro in tempo reale o in background. I flussi di lavoro in tempo reale vengono eseguiti immediatamente (in modo sincrono) e i flussi di lavoro in background vengono eseguiti in modo asincrono. Le opzioni di configurazione disponibili variano a seconda dell'opzione selezionata per questa impostazione. I flussi di lavoro in background consentono condizioni di attesa che non sono disponibili per i flussi di lavoro in tempo reale. Se le condizioni di attesa non vengono usate, sarà possibile convertire i flussi di lavoro in background in flussi di lavoro in tempo reale e viceversa. Per altre informazioni sulle condizioni di attesa, vedere [Impostazione delle condizioni per le azioni del flusso di lavoro](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 È anche disponibile l'opzione **Tipo** che consente di specificare se creare un nuovo flusso di lavoro da zero o usare un modello esistente. Quando si seleziona **Nuovo processo da modello esistente (selezionare una voce dall'elenco)** è possibile scegliere uno dei processi Flusso di lavoro esistente precedentemente salvato come modello di processo.  
  
 Dopo aver creato il flusso di lavoro o se si modifica un flusso di lavoro esistente, saranno disponibili le proprietà aggiuntive seguenti:  
  
 ![Scheda Generale in un flusso di lavoro](media/create-workflow-general-tab.PNG "Scheda Generale in un flusso di lavoro")  
  
 **Attiva come**  
 È possibile scegliere **Modello di processo** per creare un punto iniziale avanzato per altri modelli. Se si seleziona questa opzione, dopo aver attivato il flusso di lavoro, il flusso non verrà applicato ma potrà essere selezionato nella finestra di dialogo **Crea processo** quando si seleziona **Tipo**: **Nuovo processo da modello esistente (selezionare una voce dall'elenco)**  
  
 I modelli di processo sono particolarmente utili quando sono presenti numerosi processi del flusso di lavoro simili e si vuole definirli senza duplicare la stessa logica.  
  
> [!NOTE]
>  La modifica di un modello di processo non cambia i comportamenti degli altri processi del flusso di lavoro creati in precedenza usandolo come modello. Un nuovo flusso di lavoro creato usando un modello è una copia del contenuto del modello.  
  
 **Disponibile per l'esecuzione**  
 Questa sezione contiene le opzioni che descrivono in che modo il flusso di lavoro è disponibile per essere eseguito.  
  
 **Esegui flusso di lavoro in background (scelta consigliata)**  
 Questa casella di controllo riflette l'opzione selezionata durante la creazione del flusso di lavoro. Questa opzione è disabilitata, ma è possibile modificarla dal menu **Azioni** scegliendo **Converti in un flusso di lavoro in tempo reale** o **Converti in un flusso di lavoro in background**.  
  
 **Come processo su richiesta**  
 Scegliere questa opzione se si vuole consentire agli utenti di eseguire questo flusso di lavoro dal comando **Esegui flusso di lavoro**.  
  
 **Come processo figlio**  
 Scegliere questa opzione se si vuole consentire che il flusso di lavoro sia disponibile per essere avviato da un altro flusso di lavoro.  
  
 **Conservazione processi di flusso di lavoro**  
 Questa sezione contiene un'opzione per l'eliminazione di un flusso di lavoro al termine della sua esecuzione.  
  
 **Elimina automaticamente processi del flusso di lavoro completati per risparmiare spazio su disco**  
 Scegliere questa opzione se si vuole che un processo del flusso di lavoro completato venga eliminato automaticamente.  
  
> [!NOTE]
>  I processi del flusso di lavoro non vengono eliminati immediatamente dopo il completamento, ma subito dopo, tramite un processo batch.  
  
 **Ambito**  
 Per le entità di proprietà dell'utente, le opzioni sono **Organizzazione**, **Business Unit padre-figlio**, **Business Unit** o **Utente**. Per le entità di proprietà dell'organizzazione l'unica opzione è **Organizzazione**.  
  
 Se l'ambito è **Organizzazione**, la logica del flusso di lavoro può essere applicata a tutti i record nell'organizzazione. In caso contrario, il flusso di lavoro può essere applicato solo a un subset di record che rientrano nell'ambito.  
  
> [!NOTE]
>  Il valore di ambito predefinito è **Utente**. Verificare che il valore di ambito sia appropriato prima di attivare il flusso di lavoro.  
  
 **Avvia in caso di**  
 Usare le opzioni di questa sezione per specificare quando un flusso di lavoro deve essere avviato automaticamente. È possibile configurare un flusso di lavoro in tempo reale in modo che venga eseguito prima di determinati eventi. Questa funzionalità è molto utile poiché il flusso di lavoro può interrompere l'azione prima che venga eseguita. Altre informazioni: [Uso dei flussi di lavoro in tempo reale](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Le opzioni disponibili sono:  
  
- **Creazione record**  
  
- **Modifica stato record**  
  
- **Assegnazione record**  
  
- **Modifica campi record**  
  
- **Eliminazione record**  
  
> [!NOTE]
>  Tenere presente che le azioni e le condizioni definite per il flusso di lavoro non considerano il momento in cui il flusso di lavoro viene eseguito. Ad esempio, se si definisce un flusso di lavoro per aggiornare il record, questa azione non può essere eseguita da un flusso di lavoro in tempo reale prima che il record venga creato. Non è possibile aggiornare un record che non esiste. Analogamente, un flusso di lavoro in background non può aggiornare un record che è stato eliminato, anche se è possibile definire questa azione per il flusso di lavoro. Se si configura un flusso di lavoro per l'esecuzione di un'azione che non può essere eseguita, viene restituito un errore e l'intero flusso di lavoro non viene eseguito.  
  
 **Esecuzione come**  
 Questa opzione è disponibile solo se è stata deselezionata l'opzione **Esegui flusso di lavoro in background (scelta consigliata)** durante la creazione del flusso di lavoro oppure se successivamente un flusso di lavoro in background è stato convertito in flusso di lavoro in tempo reale.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contesto di sicurezza dei processi del flusso di lavoro  
 Quando un flusso di lavoro in background è configurato come processo su richiesta e avviato da un utente tramite il comando **Esegui flusso di lavoro**, il flusso di lavoro può eseguire solo le azioni che possono essere eseguite dall'utente in base ai privilegi e ai livelli di accesso definiti dai ruoli di sicurezza impostato per l'account utente.  
  
 Quando un flusso di lavoro in background viene avviato in base a un evento, il flusso di lavoro opera nel contesto dell'utente proprietario, in genere l'utente che ha creato il flusso di lavoro.  
  
 Per i flussi di lavoro in tempo reale è disponibile l'opzione **Esecuzione come** ed è possibile scegliere se il flusso di lavoro deve applicare il contesto di sicurezza del proprietario del flusso di lavoro o dell'utente che ha apportato le modifiche al record. Se il flusso di lavoro include azioni che non possono essere eseguite da alcun utente in base ai limiti di sicurezza, è consigliabile scegliere di eseguire il flusso di lavoro come proprietario del flusso di lavoro.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Attivare un flusso di lavoro  
 I flussi di lavoro possono essere modificati solo mentre sono disattivati. Affinché un flusso di lavoro possa essere usato manualmente o applicato a causa di determinati eventi è necessario prima attivarlo. Affinché un flusso di lavoro possa essere attivato è necessario che contenga almeno un passaggio. Per informazioni sulla configurazione dei passaggi, vedere [Configurazione dei processi del flusso di lavoro](configure-workflow-steps.md)  
  
 Un flusso di lavoro può essere attivato o disattivato solo dal proprietario del flusso di lavoro o da un utente con il privilegio **Agisce per conto di un altro utente**, ad esempio l'amministratore di sistema.  Questo per impedire che un utente malintenzionato possa modificare il flusso di lavoro di un altro utente senza che quest'ultimo sia a conoscenza della modifica. È possibile riassegnare un flusso di lavoro di cui si è proprietari modificando il proprietario. Il campo è disponibile nella scheda **Amministrazione**. Se non si è l'amministratore di sistema e si vuole modificare un flusso di lavoro di proprietà di un altro utente, è necessario che l'altro utente disattivi il flusso di lavoro e lo assegni. Al termine della modifica del flusso di lavoro, è possibile riassegnare il flusso di lavoro all'utente per consentirgli di riattivarlo.  
  
 Per i flussi di lavoro in tempo reale è necessario che l'utente abbia il privilegio **Attiva processi in tempo reale**. Poiché i flussi di lavoro in tempo reale hanno un maggiore rischio di impatto sulle prestazioni del sistema, è consigliabile assegnare questo privilegio solo alle persone in grado di valutare il rischio potenziale.  
  
 Poiché i flussi di lavoro vengono salvati quando vengono attivati, non è necessario salvarli prima di attivarli.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Configurazione dei processi del flusso di lavoro](configure-workflow-steps.md)  <br/>
[Aggiungere un flusso di lavoro su richiesta a un processo aziendale](bpf-add-on-demand-workflow.md) 

