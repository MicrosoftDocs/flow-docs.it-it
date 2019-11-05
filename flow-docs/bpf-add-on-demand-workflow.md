---
title: Aggiungere un flusso di lavoro su richiesta a un flusso del processo di business
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
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
ms.openlocfilehash: ab30f745d6465cff9551854034c25130697144ba
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546105"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Aggiungere un flusso di lavoro su richiesta a un flusso del processo di business
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

È possibile attivare flussi di lavoro su richiesta dall'interno di un flusso del processo di business. Ad esempio, è possibile aggiungere un flusso di lavoro su richiesta a un flusso del processo di business in modo che un'attività, ad esempio un'attività o un messaggio di posta elettronica, venga creata ogni volta che viene completata una fase. 

Un flusso di lavoro viene attivato in base alla posizione in cui il flusso di lavoro viene rilasciato nella finestra di progettazione del flusso del processo
- Processi in fase di richiesta. Quando il flusso di lavoro viene rilasciato in una fase del flusso del processo di business, il flusso di lavoro viene attivato all'immissione o all'uscita della fase. 
- Processi globali su richiesta. Quando il flusso di lavoro viene rilasciato nell'area **flussi di lavoro globali** , il flusso di lavoro viene attivato durante l'attivazione del processo o l'archiviazione dei processi (quando lo stato passa a uno stato applicato, completato, riattivato o abbandonato). 

Si notino i requisiti seguenti quando si aggiunge un flusso di lavoro a un flusso del processo di business.
- Per i flussi di lavoro aggiunti a una fase: è possibile usare solo flussi di lavoro attivi su richiesta creati per la stessa entità della fase in cui si aggiunge il flusso di lavoro.  
- Per i flussi di lavoro globali: è possibile usare solo flussi di lavoro attivi su richiesta creati per l'entità primaria del flusso del processo di business.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Aggiungere un flusso di lavoro su richiesta a una fase di flusso del processo di business

Per aggiungere un flusso di lavoro su richiesta dalla finestra di progettazione del flusso del processo di business, trascinare il componente del flusso di lavoro in una fase di elaborazione o nella sezione flussi di lavoro globali. 

Nel sito [PowerApps](https://web.powerapps.com) selezionare basato su **modello** (in basso a sinistra del riquadro di spostamento). 

Aprire la finestra di progettazione del flusso del processo di business. Questa operazione può essere eseguita in uno dei due modi seguenti.
- Se il flusso del processo di business è già stato aggiunto a un'app **, passare ad app, accanto**all'app desiderata selezionare **...** e quindi selezionare **modifica**. Nella finestra di progettazione dell'app selezionare il flusso del processo di business e quindi selezionare ![aprire la finestra di progettazione del flusso del processo di business](media/dynamics365-open-designer.PNG).  
- In caso contrario, aprire [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), nel riquadro di spostamento a sinistra selezionare **processi**, quindi selezionare il flusso del processo di business desiderato. 

Decidere se si desidera che il flusso di lavoro su richiesta venga attivato da uno dei seguenti eventi del flusso del processo di business. 
- Processi in fase di richiesta. Attiva il flusso di lavoro all'immissione o all'uscita della fase. 
- Processi globali su richiesta. Attiva il flusso di lavoro durante l'attivazione del processo o l'archiviazione del processo (quando lo stato passa a uno stato applicato, completato, riattivato o abbandonato). 

Nell'esempio seguente viene aggiunto un flusso di lavoro su richiesta denominato flusso di lavoro **su richiesta** alla **fase 1** del flusso del processo di business. 

1. Espandere la fase 1 per visualizzare la sezione del **processo attivata** . 
2. Selezionare la scheda **componenti** e trascinare **Workflow** nella sezione **processo attivato** .
    ![aggiungere un flusso di lavoro a una fase](media/add-workflow-to-bpf-1.png) in alternativa, è possibile trascinare il **flusso di lavoro** nella sezione **flussi di lavoro globali** , che attiva il flusso di lavoro durante l'attivazione del processo o l'archiviazione dei processi.
 ![aggiungere WORFKLOW per elaborare l'attivazione o l'archiviazione](media/add-workflow-to-bpf-global.png)
3. Nella casella di ricerca della scheda **Proprietà** immettere e cercare il nome del flusso di lavoro su richiesta che si desidera aggiungere alla fase del flusso del processo di business e quindi selezionare **applica**.
    ![immettere il nome e selezionare Applica](media/add-workflow-to-bpf-2.png)
4. Nella scheda **Proprietà** in **trigger** Selezionare la **voce della fase** o l'uscita di una **fase**.  
    ![selezionare il trigger del flusso di lavoro](media/workflow-trigger.png)
   
    In alternativa, quando si rilascia il flusso di lavoro nella sezione **flussi di lavoro globali** , le opzioni del trigger sono **processo applicato**, **processo riattivato**, **processo abbandonato**e **processo completato**.

5. Selezionare **Aggiorna** nella barra degli strumenti della finestra di progettazione del flusso del processo di business.
 
## <a name="next-steps"></a>Passaggi successivi
[Usare i processi del flusso di lavoro per automatizzare i processi che non richiedono l'interazione dell'utente](workflow-processes.md) <br/>
[Esercitazione: creare un flusso del processo di business per standardizzare i processi](create-business-process-flow.md) <br/>
[Automazione del flusso del processo di business in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
