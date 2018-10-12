---
title: Aggiungere un flusso di lavoro su richiesta a un processo aziendale
description: ''
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: aa061d5e2f668e8950a6cdab89992996f64c6fe8
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689618"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Aggiungere un flusso di lavoro su richiesta a un processo aziendale

È possibile attivare i flussi di lavoro su richiesta dall'interno di un processo aziendale. È possibile ad esempio aggiungere un flusso di lavoro su richiesta a un processo aziendale in modo che venga creata un'attività come un compito o un messaggio di posta elettronica per ogni fase completata. 

Un flusso di lavoro diventa attivato in base alla posizione in cui è stato rilasciato nella finestra di progettazione del processo aziendale.
- Processi di fasi su richiesta. Quando il flusso di lavoro viene rilasciato in una fase del processo aziendale, il flusso di lavoro viene attivato all'inizio o alla fine della fase. 
- Processi globali su richiesta. Quando il flusso di lavoro viene rilasciato nell'area **Flusso di lavoro globale**, il flusso di lavoro viene attivato all'attivazione o all'archiviazione del processo (quando lo stato diventa Applicato, Completato, Riattivato o Abbandonato). 

Quando si aggiunge un flusso di lavoro a un processo aziendale tenere presente i requisiti seguenti.
- Per i flussi di lavoro aggiunti a una fase: è possibile usare solo flussi su richiesta attivi creati per la stessa entità della fase in cui è stato aggiunto il flusso di lavoro.  
- Per i flussi di lavoro globali: è possibile usare solo flussi di lavoro su richiesta attivi creati per l'entità primaria del processo aziendale.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Aggiungere un flusso di lavoro su richiesta a un fase del processo aziendale

Per aggiungere un flusso di lavoro su richiesta dalla finestra di progettazione del processo aziendale, trascinare il componente del flusso di lavoro in una fase del processo o nella sezione dei flussi di lavoro globali. 

Nel sito [PowerApps](https://web.powerapps.com) selezionare **Basata su modello** nella parte inferiore sinistra del riquadro di spostamento. 

Aprire la finestra di progettazione del processo aziendale. Questa operazione può essere eseguita in due modi.
- Se il processo aziendale è già stato aggiunto a un'app, passare ad **App**, accanto all'app desiderata selezionare **…** e quindi scegliere **Modifica**. Nella finestra di progettazione dell'app selezionare il processo aziendale e quindi ![Open business process flow designer](media/dynamics365-open-designer.PNG) (Apri finestra di progettazione processo aziendale).  
- In alternativa, aprire [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), nel riquadro di spostamento sinistro selezionare **Processi** e quindi selezionare il processo aziendale desiderato. 

Decidere se si vuole che il flusso di lavoro su richiesta venga attivato da uno dei seguenti eventi del processo aziendale. 
- Processi di fasi su richiesta. Attiva il flusso di lavoro all'inizio o alla fine della fase. 
- Processi globali su richiesta. Attiva il flusso di lavoro all'attivazione o all'archiviazione del processo (quando lo stato diventa Applicato, Completato, Riattivato o Abbandonato). 

Nell'esempio seguente un flusso di lavoro su richiesta denominato **My on demand workflow** (Flusso di lavoro su richiesta personale) viene aggiunto a **Stage 1** (Fase 1) del processo aziendale. 

1. Espandere la fase 1 per visualizzare la sezione **Processo attivato**. 
2. Selezionare la scheda **Componenti** e trascinare **Flusso di lavoro** nella sezione **Processo attivato**.
    ![Aggiungere un flusso di lavoro a una fase](media/add-workflow-to-bpf-1.png) In alternativa, è possibile trascinare **Flusso di lavoro** nella sezione **Flusso di lavoro globale** per attivare il flusso di lavoro all'attivazione o all'archiviazione del processo.
 ![Aggiungere un flusso di lavoro all'attivazione o all'archiviazione del processo](media/add-workflow-to-bpf-global.png)
3. Nella casella di ricerca della scheda **Proprietà** immettere e cercare il nome del flusso di lavoro su richiesta da aggiungere alla fase del processo aziendale e quindi selezionare **Applica**.
    ![Immettere il nome e selezionare Applica](media/add-workflow-to-bpf-2.png)
4. Nella scheda **Proprietà** in **Trigger** selezionare **Inserimento fase** o **Uscita fase**.  
    ![Selezionare il trigger del flusso di lavoro](media/workflow-trigger.png)
   
    In alternativa, quando si rilascia il flusso di lavoro nella sezione **Flusso di lavoro globale**, le opzioni di trigger sono **Processo applicato**, **Processo riattivato**, **Processo abbandonato** e **Processo completato**.

5. Selezionare **Aggiorna** nella barra degli strumenti della finestra di progettazione del processo aziendale.
 
## <a name="next-steps"></a>Passaggi successivi
[Usare i processi Flusso di lavoro per automatizzare i processi che non richiedono l'iterazione dell'utente](workflow-processes.md) <br/>
[Esercitazione: Creare un processo aziendale per la standardizzazione dei processi](create-business-process-flow.md) <br/>
[Automazione dei processi aziendali in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
