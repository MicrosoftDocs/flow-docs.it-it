---
title: Creare un flusso di attività per dispositivi mobili con PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ccd3b6c0e8cf97a490d01bb9ba5e5c3c4043fda5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546437"
---
# <a name="create-a-mobile-task-flow"></a>Creare un flusso di attività per dispositivi mobili
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Progettare un flusso in Dynamics 365 per telefoni o Dynamics 365 per i tablet basati sulle attività comuni eseguite dagli utenti. Se, ad esempio, è necessario eseguire regolarmente una serie di passaggi di completamento dopo le riunioni dei client, creare un flusso attività. Quando gli utenti toccano la nuova attività nell'app per dispositivi mobili, li comporterà dall'inizio alla fine, in modo che non dimentichino un passaggio importante.  
  
 I flussi di attività possono usare i moduli e la logica multientità e possono avere la logica del modulo che viene eseguita nelle pagine del flusso di attività.  
  
## <a name="create-a-task-flow"></a>Creare un flusso attività
  
1. Assicurarsi di disporre dell'amministratore di sistema o del ruolo di sicurezza verbi di sistema o di autorizzazioni equivalenti. Il Manager, il vicepresidente o il CEO-Business Manager, i ruoli di sicurezza possono anche creare flussi di attività per dispositivi mobili. 
  
2. Aprire [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e selezionare **processi**.  
  
3.  Sulla barra degli strumenti **azioni** selezionare **nuovo**.  
  
4.  Nella finestra di dialogo **Crea processo** completare i campi obbligatori:  
  
    -   Immettere un nome di processo.  
  
    -   Nell'elenco **categoria** selezionare flusso del **processo di business**.  
  
    -   Nell'elenco **entità** selezionare l'entità desiderata.  
  
5.  Selezionare l'opzione **Esegui processo come flusso attività (mobile online)** .  
  
6.  Fare clic su **OK**.
  
     La finestra di progettazione del flusso attività viene aperta in una nuova finestra.  
  
     ![Finestra di progettazione flusso attività](media/task-flow-designer-window.png "Finestra di progettazione flusso attività") 
  
7.  Se gli utenti si spostano da una pagina a un'altra in ordine, trascinare il componente della **pagina** dalla scheda **componenti** sul lato destro dello schermo e rilasciarlo sul segno + nel punto appropriato. Per aggiungere un nome per una pagina, selezionare la pagina, selezionare la scheda **Proprietà** , digitare un nuovo nome e quindi selezionare **applica**.  
  
8.  Per aggiungere un ramo al flusso attività, trascinare il componente **condizione** dalla scheda **componenti** e rilasciarlo sul segno + nel punto appropriato. Per impostare le proprietà per la condizione, selezionare la condizione, impostare le proprietà nella scheda **Proprietà** e quindi selezionare **applica**.  
  
    > [!NOTE]
    >  Quando si aggiungono pagine e condizioni al flusso attività, viene visualizzata una mini mappa nell'angolo inferiore sinistro della finestra che Mostra tutte le pagine e le condizioni nel flusso attività.  
  
9. Per aggiungere un'etichetta di campo, etichetta o sezione a una pagina, trascinare un **campo**, un' **etichetta**o un' **etichetta di sezione** dalla scheda **componenti** alla pagina appropriata. Per modificare le proprietà di uno di questi elementi, selezionare l'elemento, impostare le proprietà nella scheda **Proprietà** e quindi selezionare **applica**.  
  
10. Per convalidare il flusso attività, selezionare **convalida** sulla barra delle azioni.  
  
11. Per salvare il processo come bozza, selezionare **Salva** nella parte superiore della schermata. (Purché un processo sia una bozza, gli utenti non saranno in grado di usarlo).  
  
12. Per attivare il flusso attività in modo che gli utenti possano utilizzarlo, selezionare **Activate (attiva**).  
  
> [!TIP]
>  Ecco alcuni suggerimenti da tenere presenti quando si lavora al flusso attività nella finestra di progettazione:  
>   
> -  Per creare uno snapshot di tutti gli elementi nella finestra flusso attività, selezionare **snapshot** sulla barra delle azioni.  
> -  Per connettere un componente valido a un altro componente valido nella finestra di progettazione, selezionare **connettore** sulla barra delle azioni.  
> -  È possibile fare in modo che le immagini sulla schermata siano maggiori o minori selezionando il pulsante **Aumenta livello di zoom** o **Diminuisci livello di zoom** nell'angolo superiore destro dello schermo. Selezionare il pulsante **adatta all'area di disegno** per saltare le immagini fino alle dimensioni massime che si adattano allo schermo.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Creare un flusso del processo di business](create-business-process-flow.md)   

