---
title: Procedure consigliate per la gestione dei processi del flusso di lavoro | MicrosoftDocs
description: Informazioni sui metodi di utilizzo consigliati per i flussi di lavoro
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
ms.openlocfilehash: c0a59a625f4d43d125bde6ddf6edd5da5b6f6430
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462787"
---
# <a name="best-practices-for-workflow-processes"></a>Procedure consigliate per i processi dei flussi di lavoro

Questo argomento descrive le procedure consigliate per la creazione e la gestione dei processi dei flussi di lavoro.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Evitare i cicli infiniti  
 È possibile che in un flusso di lavoro si crei una logica che avvia un ciclo infinito che esaurisce le risorse del server con effetti sulle prestazioni. La situazione tipica in cui può verificarsi un ciclo infinito è il caso di un flusso di lavoro configurato in modo che venga avviato quando viene aggiornato un attributo e che quindi aggiorna l'attributo stesso nella logica del flusso di lavoro. L'azione di aggiornamento attiva lo stesso flusso di lavoro che aggiorna il record e attiva il flusso di lavoro all'infinito.  
  
 I flussi di lavoro creati includono una logica per rilevare e arrestare i cicli infiniti. Se un processo del flusso di lavoro viene eseguito più di un certo numero di volte in un record specifico in un breve periodo di tempo, il processo non viene eseguito e genera l'errore seguente: **Il processo del flusso di lavoro è stato annullato perché il flusso di lavoro che lo ha avviato include un ciclo infinito. Correggere la logica del flusso di lavoro e riprovare**. Il limite di tentativi è 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Usare i modelli di flusso di lavoro  
 Se sono presenti flussi di lavoro simili e si prevede di creare più flussi di lavoro che seguono lo stesso modello, salvare il flusso di lavoro come modello di flusso di lavoro. In questo modo, la volta successiva in cui è necessario creare un flusso di lavoro simile, creare il flusso di lavoro usando il modello ed evitando di specificare tutte le condizioni e le azioni da zero.  
  
 Nella finestra di dialogo **Crea processo** scegliere **Nuovo processo da modello esistente (selezionare una voce dall'elenco)**.  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Usare flussi di lavoro figlio  
 Se si applica la stessa logica in flussi di lavoro o rami condizionali diversi, definire la logica come flusso di lavoro figlio in modo che non sia necessario replicarla manualmente in ogni flusso di lavoro o ramo condizionale. Ciò rende più semplice la gestione dei flussi di lavoro. Anziché esaminare più flussi di lavoro che potrebbero applicare la stessa logica, sarà sufficiente aggiornare un unico flusso di lavoro.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Eliminare automaticamente i processi del flusso di lavoro completati
Per i flussi di lavoro in background (asincroni), è consigliabile selezionare l'opzione **Elimina automaticamente processi del flusso di lavoro completati per risparmiare spazio su disco** nella definizione del flusso di lavoro. Se si seleziona questa casella di controllo, il sistema può eliminare i registri dei flussi di lavoro relativi alle esecuzioni completate per risparmiare spazio su disco. Si noti che i registri delle esecuzioni del flusso di lavoro non riuscite verranno sempre salvati per consentire l'individuazione e la risoluzione dei problemi.  

![Conservazione dei processi del flusso di lavoro](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Conservare i registri dei processi del flusso di lavoro in cui si sono verificati errori  
Per i flussi di lavoro che non vengono eseguiti in background (sincroni), è consigliabile selezionare l'opzione **Mantieni registri per i processi del flusso di lavoro con errori** nella definizione del flusso di lavoro. La selezione di questa opzione consente di salvare i registri delle esecuzioni del flusso di lavoro non riuscite per consentire l'individuazione e la risoluzione dei problemi. I registri delle esecuzioni del flusso di lavoro sincrone completate verranno sempre eliminati per risparmiare spazio su disco.   

![Opzioni Mantieni registri per i processi del flusso di lavoro con errori](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Limitare il numero di flussi di lavoro che aggiornano la stessa entità
L'esecuzione di più flussi di lavoro che aggiornano la stessa entità può causare problemi di blocco delle risorse. Si supponga di avere più flussi di lavoro dove ogni aggiornamento dell'entità attiva un aggiornamento all'account associato. L'esecuzione di più istanze di questi flussi di lavoro che tentano di aggiornare lo stesso record account contemporaneamente può causare problemi di blocco delle risorse. Si verificano errori di flusso di lavoro e viene registrato un messaggio di errore, ad esempio **Timeout SQL: Impossibile ottenere il blocco nella risorsa _nome risorsa_**. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Usare Note per tenere traccia delle modifiche  
 Quando si modificano i flussi di lavoro, usare la scheda Note e immettere le operazioni eseguite e i motivi. Ciò consente agli altri utenti di comprendere le modifiche apportate.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Panoramica dei processi del flusso di lavoro](workflow-processes.md)   
 [Configurare i processi del flusso di lavoro](configure-workflow-steps.md)   
 [Monitorare e gestire i processi del flusso di lavoro](monitor-manage-processes.md)
   
