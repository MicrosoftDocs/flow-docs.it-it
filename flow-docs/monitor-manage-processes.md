---
title: Monitorare e gestire i processi di flusso di lavoro con PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 00d20d361dd7b3db9f55d6b975c472bea0c4160e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548996"
---
# <a name="monitor-and-manage-workflow-processes"></a>Monitorare e gestire i processi del flusso di lavoro
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Per monitorare e gestire i processi, è necessario individuare il processo, valutarne lo stato ed eseguire le azioni necessarie per risolvere i problemi.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Monitoraggio dei flussi di lavoro in background  
 I flussi di lavoro in background generano record di processo di sistema per tenere traccia dello stato. È possibile accedere alle informazioni relative a questi processi di sistema in diverse posizioni all'interno dell'applicazione:  
  
 **[Impostazioni](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > processi di sistema**  
 Sono inclusi tutti i tipi di processi di sistema. È necessario filtrare i record in modo che il **tipo di processo di sistema** sia **Workflow**.  
  
 **Dal processo del flusso di lavoro**  
 Aprire la definizione del flusso di lavoro in background e passare alla scheda **elabora sessione** . Verrà visualizzato solo il processo di sistema per questo flusso di lavoro in background.  
  
 **Dal record**  
 È possibile modificare il modulo dell'entità in modo che la navigazione includa la relazione **processi in background** . Verrà visualizzato tutti i processi di sistema avviati nel contesto del record.  
  
> [!NOTE]
>  Se un processo di sistema asincrono (flusso di lavoro) ha esito negativo più volte consecutivamente, il sistema inizia a posticipare l'esecuzione del processo per intervalli di tempo più lunghi, in modo che l'amministratore o l'autore dell'app possa esaminare e risolvere il problema. Una volta riavviato il processo, l'esecuzione verrà ripresa normalmente.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Azioni sull'esecuzione di flussi di lavoro in background  
 Mentre è in esecuzione un flusso di lavoro in background, sono disponibili opzioni per **annullare**, **sospendere**o **posticipare** il flusso di lavoro. Se in precedenza è stato sospeso un flusso di lavoro, è possibile **riprenderlo** .  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Monitoraggio delle azioni e dei flussi di lavoro in tempo reale  
 I flussi di lavoro e le azioni in tempo reale non utilizzano i record dei processi di sistema perché si verificano immediatamente. Gli eventuali errori che si verificano verranno visualizzati all'utente dell'applicazione con l'intestazione dell' **errore del processo di business**.  
  
 Nessun log per le operazioni riuscite. È possibile abilitare la registrazione per gli errori selezionando l'opzione **Mantieni i registri per i processi del flusso di lavoro che ha rilevato errori** nell'area **conservazione log del flusso di lavoro** nella parte inferiore della scheda **Amministrazione** per il processo.  
  
 Per visualizzare il log degli errori per un processo specifico, aprire la definizione dell'azione o del flusso di lavoro in tempo reale e passare alla scheda **elabora sessione** . Verrà visualizzato solo gli errori registrati per questo processo.  
  
 Se si vuole visualizzare tutti gli errori per qualsiasi processo, passare a **ricerca avanzata** e creare una vista che mostri gli errori nell'entità della sessione di processo.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Stato dei processi del flusso di lavoro  
 Quando si visualizza un elenco di processi del flusso di lavoro, i singoli processi possono avere uno dei seguenti valori **per il motivo** **dello stato** e dello stato:  
  
|Stato|Motivo dello stato|  
|-----------|-------------------|  
|Pronto|In attesa di risorse|  
|Sospeso|In attesa|  
|Bloccato|In corso<br /><br /> Pausa<br /><br /> Annullamento|  
|Completato|completata<br /><br /> Fallito<br /><br /> Annullata|  

## <a name="deleting-process-log-records"></a>Eliminazione di record di log del processo

Se l'organizzazione utilizza flussi di lavoro in background o flussi del processo di business che vengono eseguiti di frequente, la quantità di record del log del processo può essere sufficientemente grande da causare problemi di prestazioni e utilizzare quantità di spazio di archiviazione significative. Per eliminare i record del log del processo non rimossi sufficientemente da uno dei processi di eliminazione di record bulk standard, è possibile utilizzare la funzionalità di eliminazione bulk dei processi di sistema per creare un processo di eliminazione di un record bulk personalizzato.

1. Passare a **impostazioni** > **Gestione dati** > **eliminazione di record in blocco**.
2. Dall'area di **eliminazione dei record in blocco** , selezionare **nuovo**. 
3. Nella pagina iniziale dell' **eliminazione guidata in blocco** selezionare **Avanti**.
4. Nell'elenco **Cerca** selezionare **processi di sistema**.
5. Le condizioni seguenti vengono utilizzate per creare un processo di eliminazione di record in blocco per eliminare i record del log del processo. 
 - Il **tipo di processo di sistema è uguale a Workflow**. Questo è destinato ai record del flusso di lavoro. 
 - **Stato uguale a completato**. Solo i flussi di lavoro completati sono validi per l'esecuzione del processo.
 - Il **motivo dello stato è uguale a succeeded**. Elimina i processi riusciti, annullati e non riusciti.
 - **Completato per più di X giorni 30**. Utilizzare il campo completato su per eliminare solo i record del log del processo del flusso di lavoro precedenti a 30 giorni.
 ![Custom-Bulk-Record-deletion. png](media/custom-bulk-record-deletion.png)
6. Fare clic su **Avanti**.
7. Impostare la frequenza con cui viene eseguito il processo di eliminazione in blocco. È possibile pianificare l'esecuzione del processo a intervalli prestabiliti o creare un processo di eliminazione bulk monouso [usando l'opzione immediatamente](#using-the-immediately-option). In questo esempio, un processo ricorrente è impostato per essere eseguito il 21 maggio 2018 e ogni 30 giorni dopo. 
![opzioni di eliminazione di record bulk](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Uso dell'opzione immediatamente

Si noti che è possibile eseguire un'eliminazione di massa sincrona immediata dei record selezionando l'opzione **immediatamente** . Questa operazione Delete viene eseguita con l'esecuzione diretta di SQL Server anziché passare ogni record attraverso la pipeline di eventi Delete, che può ridurre l'effetto sulle prestazioni del sistema. Si tratta di un'opzione valida se si desidera eliminare rapidamente i record del flusso di lavoro aggiuntivi anziché il processo di eliminazione bulk in attesa nella coda asincrona per l'elaborazione. 

L'opzione **immediatamente** è abilitata quando sono soddisfatte le condizioni seguenti: 
- Il processo di eliminazione bulk è per l'entità processi di sistema.
- I criteri di ricerca hanno il tipo di processo di sistema Condition uguale a Workflow. 
- L'utente che crea il processo di eliminazione bulk ha una profondità globale per il privilegio DELETE nell'entità AsyncOperation. Questo privilegio è associato al ruolo di sicurezza amministratore di sistema.  

L'eliminazione bulk sincrona eliminerà solo i record AsyncOperation nello stato Completed. Viene elaborato un massimo di 1 milione record per ogni chiamata. Sarà necessario eseguire il processo più volte se l'ambiente contiene più di 1 milione record da rimuovere.  
  
## <a name="next-steps"></a>Passaggi successivi   
 [Procedure consigliate per i processi del flusso di lavoro](best-practices-workflow-processes.md) <br />

