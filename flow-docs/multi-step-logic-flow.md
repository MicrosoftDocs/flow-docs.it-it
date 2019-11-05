---
title: Aggiungere un'opzione avanzata e più azioni | Microsoft Docs
description: Espandere un flusso per includere un'opzione avanzata, ad esempio l'impostazione della posta elettronica a priorità alta e aggiungere un'altra azione per lo stesso evento.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 668e69b1c8f1781cf5720443af8e48409f43d322
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548601"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Aggiungere più azioni e opzioni avanzate a un flusso
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Personalizzare un flusso aggiungendo una o più opzioni avanzate e più azioni per lo stesso trigger. Ad esempio, aggiungere un'opzione avanzata che invii un messaggio di posta elettronica come priorità alta. Oltre a inviare messaggi di posta elettronica quando un elemento viene aggiunto a un elenco di SharePoint, creare un file in Dropbox contenente le stesse informazioni.

## <a name="prerequisites"></a>Prerequisiti
* [Creare un flusso](get-started-logic-flow.md)

## <a name="add-another-action"></a>Aggiungi un'altra azione
In questa procedura verrà aggiunta un'azione all'interno del flusso. Questa azione salverà un file in Dropbox, archiviando l'elemento nell'elenco.

1. In [Flow.Microsoft.com](https://flow.microsoft.com)selezionare **flussi personali** nella barra di spostamento superiore.
2. Nell'elenco dei flussi selezionare il flusso che si desidera modificare.
3. Selezionare **nuovo passaggio**, quindi selezionare **Aggiungi un'azione**.
   
    ![Aggiunta compressa](./media/multi-step-logic-flow/add-action.png)
4. Nell'elenco delle azioni possibili, cercare **Crea file**, quindi fare clic su **Dropbox-crea file**.
   
    ![Cerca in Crea file](./media/multi-step-logic-flow/create-file-search.png)
5. Se richiesto, specificare le credenziali di Dropbox.
6. Selezionare l'icona della cartella sul lato destro della casella **percorso cartella** .
7. Individuare e selezionare la cartella in cui si desidera inserire il nuovo file.
   
    ![Cerca in Crea file](./media/multi-step-logic-flow/create-file-folder.png)
8. Immettere il nome del nuovo file nella casella **nome file** . Assicurarsi di aggiungere un'estensione, ad esempio ". txt", al nome del file. A questo punto, usare **TweetId** nel nome del file per assicurare l'univocità dei file. Potrebbe essere necessario selezionare **Visualizza altro** per trovare il token **TweetId** .
9. Aggiungere il testo che si desidera includere nel file digitando nella casella **contenuto file** . È anche possibile aggiungere token alla casella **contenuto file** .
   
    ![nome e contenuto del file](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Se si assegna al file un nome che corrisponde al nome di un file esistente (nella cartella selezionata), il file esistente verrà sovrascritto.
   > 
   > 
10. Selezionare **Aggiorna flusso**, disponibile nel menu nella parte superiore della schermata.
11. Inviare un tweet che contiene la parola chiave specificata.
    
     All'interno di un minuto, viene creato un file nell'account Dropbox.

## <a name="reorder-or-delete-an-action"></a>Riordinare o eliminare un'azione
* Per ricevere messaggi di posta elettronica dopo aver creato il file in Dropbox, spostare l'azione Dropbox trascinando la barra del titolo sopra l'azione di posta elettronica. Rilasciare l'azione Dropbox sulla freccia tra il trigger (**quando viene pubblicato un nuovo Tweet**) e l'azione di posta elettronica. (Il cursore indica se l'azione è posizionata correttamente).
  
  > [!NOTE]
  > Non è possibile spostare un passaggio prima di un altro se si usano output di tale passaggio.
  > 
  > 
  
    ![Elimina il menu](./media/multi-step-logic-flow/draggingaction.png)
* Per eliminare un'azione, selezionare i puntini di sospensione (...) accanto al bordo destro della barra del titolo per l'azione che si desidera eliminare, selezionare **Elimina**e quindi fare clic su **OK**.
  
    ![Elimina il menu](./media/multi-step-logic-flow/deletemenu.png)
  
     **Nota:** Non è possibile eliminare un'azione se si usano output in qualsiasi punto nel flusso. Rimuovere prima di tutto questi output dai campi, quindi è possibile eliminare l'azione.


## <a name="copy-and-paste-actions"></a>Copiare e incollare azioni

Se si desidera duplicare le azioni durante la progettazione di un flusso, è possibile copiarle e incollarle. Se, ad esempio, si sta compilando una condizione e si desiderano azioni simili nel lato **if sì** e il lato **if no** , anziché creare entrambe le azioni da zero, è possibile compilare la prima azione in un lato e quindi copiarla sull'altro lato.


### <a name="to-copy-an-action"></a>Per copiare un'azione
1. Selezionare il menu azione (... nella parte superiore destra dell'azione.
1. Selezionare **copia negli Appunti**. 
1. Selezionare il **nuovo passaggio** in cui si vuole che l'azione venga eseguita. 

     Si noti la scheda **Appunti** che consente di scegliere tra tutte le azioni copiate.
1. Selezionare l'elemento che si desidera incollare.

## <a name="add-advanced-options"></a>Aggiungi opzioni avanzate
Iniziare con un flusso con un'azione **Invia un messaggio di posta elettronica** .

1. Selezionare **Mostra opzioni avanzate**, che si trova nella parte inferiore della scheda **Invia un messaggio di posta elettronica** .
   
     Verranno quindi visualizzate le opzioni avanzate per l'invio di un messaggio di posta elettronica.
   
    ![Trigger di SharePoint](./media/multi-step-logic-flow/advanced.png)
2. Selezionare **alta** nell'elenco **importanza** , quindi selezionare **Nascondi opzioni avanzate** per nascondere le opzioni avanzate.
3. Selezionare **Aggiorna flusso**, disponibile nel menu nella parte superiore della schermata.
   
     Questo passaggio consente di salvare le modifiche.

