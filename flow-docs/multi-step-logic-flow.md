---
title: Aggiungere un'opzione avanzata e più azioni | Microsoft Docs
description: Espandere un flusso in modo da includere un'opzione avanzata, ad esempio l'impostazione di posta elettronica a priorità elevata e l'aggiunta di un'altra azione per lo stesso evento.
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
ms.openlocfilehash: f6c936cbf5a2bd481adb52ec9b01545fb9ba7b0b
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "23442117"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Aggiungere più azioni e opzioni avanzate a un flusso
Personalizzare un flusso aggiungendo una o più opzioni avanzate e più azioni per lo stesso trigger. Ad esempio, aggiungere un'opzione avanzata che invii un messaggio di posta elettronica con priorità elevata. Oltre a inviare posta elettronica quando un elemento viene aggiunto a un elenco di , creare in Dropbox un file che contenga le stesse informazioni.

## <a name="prerequisites"></a>Prerequisiti
* [Creare un flusso](get-started-logic-flow.md)

## <a name="add-another-action"></a>Aggiungere un'altra azione
In questa procedura si aggiungerà un'azione nel mezzo del flusso. Questa azione salverà un file in Dropbox, archiviando l'elemento nell'elenco.

1. In [flow.microsoft.com](https://flow.microsoft.com), selezionare **Flussi personali** nella barra di spostamento in alto.
2. Nell'elenco dei flussi, selezionare il flusso da modificare.
3. Selezionare **Nuovo passaggio**, quindi scegliere **Aggiungi un'azione**.
   
    ![Pulsante di aggiunta compresso](./media/multi-step-logic-flow/add-action.png)
4. Nell'elenco di possibili azioni, cercare **Crea file**, quindi fare clic su **Dropbox - Create file** (Dropbox - Crea file).
   
    ![ricerca di crea file](./media/multi-step-logic-flow/create-file-search.png)
5. Se richiesto, fornire le credenziali di Dropbox.
6. Selezionare l'icona della cartella a destra della casella **Percorso cartella**.
7. Trovare e selezionare la cartella in cui si desidera inserire il nuovo file.
   
    ![ricerca di crea file](./media/multi-step-logic-flow/create-file-folder.png)
8. Immettere il nome del nuovo file nella casella**Nome file**. Assicurarsi di aggiungere un'estensione, ad esempio ".txt", al nome del file. In questo caso, viene aggiunta la dicitura **TweetId** nel nome del file per garantire l'univocità dei file. Potrebbe essere necessario selezionare **See more**  (Vedi altri) per trovare il token **TweetId**.
9. Aggiungere il testo che deve essere contenuto nel file digitandolo nella casella **Contenuto file**. È inoltre possibile aggiungere i token nella casella **Contenuto file**.
   
    ![nome file e contenuti](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Se al file viene assegnato un nome che corrisponde a quello di un file esistente (nella cartella selezionata), il file esistente verrà sovrascritto.
   > 
   > 
10. Selezionare **Aggiorna flusso**, che si trova nel menu in alto della schermata.
11. Inviare un tweet che contiene la parola chiave specificata.
    
     Entro un minuto, viene creato un file nell'account Dropbox.

## <a name="reorder-or-delete-an-action"></a>Riordinare o eliminare un'azione
* Per ricevere messaggi di posta elettronica dopo aver creato il file in Dropbox, spostare l'azione di Dropbox trascinando la barra del titolo sopra l'azione di posta elettronica. Rilascia l'azione Dropbox sopra la freccia tra il trigger (**Quando viene pubblicato un nuovo tweet**) e l'azione di posta elettronica. (Il cursore indica se l'azione è posizionata correttamente).
  
  > [!NOTE]
  > Se si usa qualsiasi output di tale passaggio non è possibile spostare un passaggio prima di un altro.
  > 
  > 
  
    ![Eliminare il menu](./media/multi-step-logic-flow/draggingaction.png)
* Per eliminare un'azione, selezionare i puntini di sospensione (...) accanto al bordo destro della barra del titolo per l'azione che si vuole eliminare, selezionare **Elimina**, quindi selezionare **OK**.
  
    ![Eliminare il menu](./media/multi-step-logic-flow/deletemenu.png)
  
     **Nota:** non è possibile eliminare un'azione se si usano i relativi output in qualsiasi punto nel flusso. È prima di tutto necessario rimuovere tali output dai campi, quindi è possibile eliminare l'azione.

## <a name="add-advanced-options"></a>Aggiungere le opzioni avanzate
Iniziare con un flusso che includa un'azione **Invia un messaggio di posta elettronica**.

1. Selezionare **Mostra opzioni avanzate**, che si trova nella parte inferiore della scheda **Invia un messaggio di posta elettronica**.
   
     Le opzioni avanzate per l'invio di un messaggio di posta elettronica saranno quindi disponibili.
   
    ![Trigger di SharePoint](./media/multi-step-logic-flow/advanced.png)
2. Selezionare **Elevata** dall'elenco **Priorità**, quindi selezionare **Nascondi opzioni avanzate** per nascondere le opzioni avanzate.
3. Selezionare **Aggiorna flusso**, che si trova nel menu in alto della schermata.
   
     Questo passaggio consente di salvare le modifiche.

