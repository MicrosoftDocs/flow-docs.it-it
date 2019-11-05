---
title: Procedure consigliate per la gestione dei processi flusso di lavoro | MicrosoftDocs
description: Informazioni sui modi consigliati per usare i flussi di lavoro
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ad9935b171568b62376232f450a62dbda4752cac
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546031"
---
# <a name="best-practices-for-workflow-processes"></a>Procedure consigliate per i processi del flusso di lavoro
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Questo argomento contiene le procedure consigliate per la creazione e la gestione dei processi del flusso di lavoro  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Evitare cicli infiniti  
 È possibile creare la logica in un flusso di lavoro che avvia un ciclo infinito, che utilizza le risorse del server e influisca sulle prestazioni. La situazione tipica in cui può verificarsi un ciclo infinito è se si dispone di un flusso di lavoro configurato per l'avvio quando un attributo viene aggiornato e quindi aggiorna tale attributo nella logica del flusso di lavoro. L'azione di aggiornamento attiva lo stesso flusso di lavoro che aggiorna il record e attiva di nuovo il flusso di lavoro.  
  
 I flussi di lavoro creati includono la logica per rilevare e arrestare i cicli infiniti. Se un processo del flusso di lavoro viene eseguito più di un determinato numero di volte in un record specifico in un breve periodo di tempo, il processo ha esito negativo con l'errore seguente: **questo processo del flusso di lavoro è stato annullato perché il flusso di lavoro che ha avviato l'operazione include un ciclo infinito. Correggere la logica del flusso di lavoro e riprovare**. Il limite di volte è 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Usare i modelli di flusso di lavoro  
 Se si dispone di flussi di lavoro simili e si prevede di creare più flussi di lavoro che seguono lo stesso modello, salvare il flusso di lavoro come modello di flusso di lavoro. In questo modo, la volta successiva che è necessario creare un flusso di lavoro simile, creare il flusso di lavoro usando il modello ed evitare di immettere tutte le condizioni e le azioni da zero.  
  
 Nella finestra di dialogo **Crea processo** scegliere **nuovo processo da un modello esistente (selezionare dall'elenco)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Usare i flussi di lavoro figlio  
 Se si applica la stessa logica in flussi di lavoro diversi o in branch condizionali, definire tale logica come flusso di lavoro figlio, in modo da non dover replicare manualmente tale logica in ogni flusso di lavoro o ramo condizionale. Ciò consente di semplificare la gestione dei flussi di lavoro. Anziché esaminare molti flussi di lavoro che potrebbero applicare la stessa logica, è possibile aggiornare un solo flusso di lavoro.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Elimina automaticamente i processi del flusso di lavoro completati
Per i flussi di lavoro in background (asincroni), è consigliabile selezionare l'opzione **Elimina automaticamente i processi del flusso di lavoro completati (per risparmiare spazio su disco)** nella definizione del flusso di lavoro. Selezionando questa casella si consente al sistema di eliminare i log del flusso di lavoro per eseguire le esecuzioni riuscite per risparmiare spazio. Si noti che i log delle esecuzioni del flusso di lavoro non riuscite verranno sempre salvati per la risoluzione dei problemi.  

![Conservazione del processo del flusso di lavoro](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Mantieni i registri per i processi del flusso di lavoro che hanno rilevato errori  
Per i flussi di lavoro che non vengono eseguiti in background (sincrono), è consigliabile selezionare l'opzione **Mantieni i registri per i processi del flusso di lavoro che ha rilevato errori** nella definizione del flusso di lavoro. La selezione di questa opzione consente di salvare i log da esecuzioni del flusso di lavoro non riuscite per la risoluzione dei problemi. I log delle esecuzioni dei flussi di lavoro sincroni con esito positivo verranno sempre eliminati per risparmiare spazio.   

![Opzione Mantieni registri per flussi di lavoro non riusciti](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Limitare il numero di flussi di lavoro che aggiornano la stessa entità
L'esecuzione di più flussi di lavoro che aggiorna la stessa entità può causare problemi di blocco delle risorse. Immaginate diversi flussi di lavoro in esecuzione dove ogni aggiornamento dell'opportunità attiva un aggiornamento per l'account associato. Più istanze di questi flussi di lavoro in esecuzione e che tentano di aggiornare lo stesso record di account nello stesso momento possono causare problemi di blocco delle risorse. Si verificano errori del flusso di lavoro e viene registrato un messaggio di errore, ad esempio **timeout SQL: Impossibile ottenere il blocco sul _nome della risorsa_risorsa**. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Usare le note per tenere traccia delle modifiche  
 Quando si modificano i flussi di lavoro, è necessario usare la scheda note e digitare quanto è stato fatto e perché è stato fatto. Ciò consente a un altro utente di comprendere le modifiche apportate.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Panoramica dei processi di flusso di lavoro](workflow-processes.md)   
 [Configurare i processi del flusso di lavoro](configure-workflow-steps.md)   
 [Monitorare e gestire i processi del flusso di lavoro](monitor-manage-processes.md)
   
