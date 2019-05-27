---
title: Creare un flusso di attività per dispositivi mobili con PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 7f15f11a4e66d80762384f8183af7973fcca76bf
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456190"
---
# <a name="create-a-mobile-task-flow"></a>Creare un flusso di attività per dispositivi mobili

Progettare un flusso in Dynamics 365 per i telefoni o Dynamics 365 per i tablet basato sulle attività comuni eseguite dagli utenti. Ad esempio, se gli utenti devono eseguire regolarmente una serie di passaggi di completamento dopo le riunioni con i clienti, creare un flusso di attività. Quando gli utenti toccano la nuova attività nell'app per dispositivi mobili, il flusso li guiderà dall'inizio alla fine in modo che non dimentichino un passaggio importante.  
  
 I flussi di attività possono usare moduli e logica a più entità e possono includere una logica dei moduli eseguita nelle pagine del flusso di attività.  
  
## <a name="create-a-task-flow"></a>Creare un flusso di attività
  
1. Assicurarsi di avere il ruolo di sicurezza Amministratore di sistema o Addetto personalizzazione sistema o autorizzazioni equivalenti. Se si usa Dynamics 365 Customer Engagement, anche i ruoli di sicurezza Responsabile, Vicepresidente o Responsabile aziendale possono creare flussi di attività per dispositivi mobili. 
  
2. Aprire [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e selezionare **Processi**.  
  
3.  Nella barra degli strumenti **Azioni** selezionare **Nuovo**.  
  
4.  Nella finestra di dialogo **Crea processo** compilare i campi obbligatori:  
  
    -   Immettere un nome di processo.  
  
    -   Nell'elenco **Categoria** selezionare **Processo aziendale**.  
  
    -   Nell'elenco **Entità** selezionare l'entità desiderata.  
  
5.  Selezionare l'opzione **Esegui processo come flusso di attività (Mobile online)**.  
  
6.  Selezionare **OK**.
  
     La finestra di progettazione del flusso di attività viene aperta in una nuova finestra.  
  
     ![Finestra di progettazione del flusso di attività](media/task-flow-designer-window.png "Finestra di progettazione del flusso di attività") 
  
7.  Se gli utenti procederanno da una pagina all'altra nell'ordine, trascinare il componente **Pagina** dalla scheda **Componenti** sul lato destro della schermata e rilasciarlo sul segno + nella posizione appropriata. Per aggiungere un nome per una pagina, selezionare la pagina, selezionare la scheda **Proprietà**, digitare un nuovo nome e quindi selezionare **Applica**.  
  
8.  Per aggiungere un ramo al flusso delle attività, trascinare il componente **Condizione** dalla scheda **Componenti** e rilasciarlo sul segno + nella posizione appropriata. Per impostare le proprietà per la condizione, selezionare la condizione, impostare le proprietà nella scheda **Proprietà** e quindi selezionare **Applica**.  
  
    > [!NOTE]
    >  Mentre si aggiungono pagine e condizioni al flusso di attività, viene visualizzata una minimappa nell'angolo inferiore sinistro della finestra che mostra tutte le pagine e le condizioni del flusso di attività.  
  
9. Per aggiungere un campo, un'etichetta o un'etichetta di sezione a una pagina, trascinare **Campo**, **Etichetta** o **Etichetta di sezione** dalla scheda **Componenti** alla pagina appropriata. Per modificare le proprietà per uno di questi elementi, selezionare l'elemento, impostare le proprietà nella scheda **Proprietà** e quindi selezionare **Applica**.  
  
10. Per convalidare il flusso di attività, selezionare **Convalida** sulla barra delle azioni.  
  
11. Per salvare il processo come bozza, selezionare **Salva** nella parte superiore della schermata. Fino a quando il processo rimane una bozza, gli utenti non potranno usarlo.  
  
12. Per attivare il flusso di attività in modo che gli utenti possano usarlo, selezionare **Attiva**.  
  
> [!TIP]
>  Di seguito sono riportati alcuni suggerimenti da tenere presente mentre si usa il flusso di attività nella finestra di progettazione:  
>   
> -  Per acquisire uno snapshot di tutti gli elementi della finestra del flusso di attività, selezionare **Snapshot** sulla barra delle azioni.  
> -  Per connettere un componente valido a un altro componente valido nella finestra di progettazione, selezionare **Connettore** sulla barra delle azioni.  
> -  È possibile ingrandire o ridurre le immagini sulla schermata selezionando i pulsanti **Aumenta il livello di zoom** o **Riduci il livello di zoom** nell'angolo superiore destro della schermata. Selezionare il pulsante **Adatta a canvas** per ingrandire le immagini alla dimensione massima possibile nella schermata.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Creare un processo aziendale](create-business-process-flow.md)   

