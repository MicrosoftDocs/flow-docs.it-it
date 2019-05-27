---
title: Monitorare e gestire i processi del flusso di lavoro con PowerApps | MicrosoftDocs
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
ms.openlocfilehash: 007caa66731870f359e8cb33ba0919390d3196cd
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64465793"
---
# <a name="monitor-and-manage-workflow-processes"></a>Monitorare e gestire i processi del flusso di lavoro

Per monitorare e gestire i processi, è necessario individuare il processo, valutare lo stato ed eseguire le azioni necessarie per risolvere i problemi.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Monitoraggio dei flussi di lavoro in background  
 I flussi di lavoro in background generano record Processo di sistema per tenere traccia del relativo stato. È possibile accedere alle informazioni su questi processi di sistema in diverse posizioni all'interno dell'applicazione:  
  
 **[Impostazioni](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Processi di sistema**  
 Sono inclusi tutti i tipi di processi di sistema. È necessario applicare un filtro per visualizzare i record in cui **Tipo processo di sistema** è impostato su **Flusso di lavoro**.  
  
 **Dal processo del flusso di lavoro**  
 Aprire la definizione del flusso di lavoro in background e passare alla scheda **Sessione del processo**. Verranno visualizzati solo i processi di sistema del flusso di lavoro in background.  
  
 **Dal record**  
 È possibile modificare il modulo dell'entità in modo che la navigazione includa la relazione **Processi in background**. Verranno visualizzati tutti i processi di sistema avviati nel contesto del record.  
  
> [!NOTE]
>  Se un processo di sistema asincrono (flusso di lavoro) ha esito negativo più volte consecutivamente, il sistema inizia a posticipare l'esecuzione del processo per intervalli di tempo sempre più lunghi per consentire all'amministratore o all'autore dell'app di individuare e risolvere il problema. Quando il processo viene nuovamente eseguito correttamente, verrà ripristinata la normale esecuzione.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Azioni su flussi di lavoro in background in esecuzione  
 Durante l'esecuzione di un flusso di lavoro in background è possibile **annullare**, **sospendere** o **posticipare** il flusso di lavoro. Se un flusso di lavoro è stato precedentemente sospeso, è possibile **riprenderne** l'esecuzione.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Monitoraggio dei flussi in tempo reale e delle azioni  
 I flussi di lavoro in tempo reale e le azioni non usano record Processo di sistema poiché vengono eseguiti immediatamente. Gli eventuali errori verranno visualizzati per l'utente nell'applicazione con l'intestazione **Errore processo aziendale**.  
  
 Non sono disponibili registri per le operazioni completate. È possibile abilitare la registrazione degli errori selezionando l'opzione **Mantieni registri per i processi del flusso di lavoro con errori** nell'area **Conservazione registro flusso di lavoro** nella parte inferiore della scheda **Amministrazione** del processo.  
  
 Per visualizzare il registro degli errori di un processo specifico, aprire la definizione del flusso di lavoro in tempo reale o dell'azione e passare alla scheda **Sessione del processo**. Verranno visualizzati soltanto gli errori registrati per il processo.  
  
 Per una visualizzazione di tutti gli errori di tutti i processi, passare a **Ricerca avanzata** e creare una visualizzazione che mostra gli errori dell'entità della sessione del processo.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Stato dei processi del flusso di lavoro  
 Quando si visualizza un elenco dei processi del flusso di lavoro, i singoli processi possono avere uno dei seguenti valori **Stato** e **Motivo stato**:  
  
|Stato|Motivo stato|  
|-----------|-------------------|  
|Pronto|In attesa di risorse|  
|Sospeso|In attesa|  
|Bloccato|In corso<br /><br /> Sospensione in corso<br /><br /> Annullamento in corso|  
|Completato|Riuscito<br /><br /> Non riuscito<br /><br /> Annullato|  

## <a name="deleting-process-log-records"></a>Eliminazione dei record del registro del processo

Se l'organizzazione usa flussi di lavoro in background o processi aziendali eseguiti di frequente, la quantità di record del registro del processo può aumentare causando problemi di prestazioni e occupando una grande quantità di memoria. Per eliminare i record del registro del processo non rimossi da uno dei processi di eliminazione in blocco dei record standard è possibile usare la funzione dei processi di eliminazione in blocco per creare un processo di eliminazione in blocco dei record personalizzato.

1. Passare a **Impostazioni** > **Gestione dati** > **Eliminazione in blocco record**.
2. Dall'area **Eliminazione in blocco record** selezionare **Nuovo**. 
3. Nella pagina iniziale **Eliminazione in blocco guidata** selezionare **Avanti**.
4. Nell'elenco **Cerca** selezionare **Processi di sistema**.
5. Le condizioni seguenti vengono usate per creare un processo di eliminazione in blocco dei record per eliminare i record del registro del processo. 
 - **Tipo processo di sistema uguale a Flusso di lavoro**. Si applica ai record del flusso di lavoro. 
 - **Stato uguale a Completato**. Il processo può essere eseguito solo sui flussi di lavoro completati.
 - **Motivo stato uguale a Riuscito**. Eliminare i processi riusciti, annullati e non riusciti.
 - **Data completamento Oltre 30 giorni fa**. Usare il campo Data completamento per eliminare solo i record del registro del processo del flusso di lavoro completati più di 30 giorni fa.
 ![custom-bulk-record-deletion.png](media/custom-bulk-record-deletion.png)
6. Fare clic su **Avanti**.
7. Impostare la frequenza con cui verrà eseguito il processo di eliminazione in blocco. È possibile pianificare il processo in modo che venga eseguito a intervalli prestabiliti o creare un processo di eliminazione in blocco da eseguire una sola volta con l'[Uso dell'opzione Immediatamente](#using-the-immediately-option). In questo esempio, un processo ricorrente è impostato per essere eseguito il 21 maggio 2018 e successivamente ogni 30 giorni. 
![Opzioni di eliminazione in blocco dei record](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Uso dell'opzione Immediatamente

Si noti che è possibile eseguire un'eliminazione in blocco sincrona immediata dei record selezionando l'opzione **Immediatamente**. Questa eliminazione viene eseguita con l'esecuzione di SQL Server diretta senza far passare ogni record attraverso la pipeline dell'evento di eliminazione riducendo così l'impatto sulle prestazioni del sistema. Questa opzione è utile se si vuole eliminare rapidamente i record del flusso di lavoro anziché attendere l'elaborazione del processo di eliminazione in blocco nella coda asincrona. 

L'opzione **Immediatamente** viene abilitata quando le condizioni seguenti hanno valore true: 
- Il processo di eliminazione in blocco si applica all'entità Processi di sistema.
- Nei criteri di ricerca la condizione prevede un tipo di processo di sistema uguale a Flusso di lavoro. 
- L'utente che crea il processo di eliminazione in blocco ha il privilegio di eliminazione globale per l'entità AsyncOperation. Il ruolo di sicurezza Amministratore di sistema ha questo privilegio.  

L'eliminazione in blocco sincrona eliminerà solo i record di AsyncOperation con stato Completato. Per ogni chiamata vengono elaborati un massimo di un milione di record. Se l'ambiente include più di un milione di record da eliminare sarà necessario eseguire il processo più volte.  
  
## <a name="next-steps"></a>Passaggi successivi   
 [Procedure consigliate per i processi dei flussi di lavoro](best-practices-workflow-processes.md) <br />

