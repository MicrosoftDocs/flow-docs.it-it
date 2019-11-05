---
title: Attendere l'approvazione in un flusso | Microsoft Docs
description: I flussi possono attendere che si verifichi un evento esterno, ad esempio un utente che approva o rifiuta una modifica, prima di eseguire un'azione, ad esempio l'invio di una notifica della decisione.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ea6be2d1deae080df58afd94c1f1e8d0c13c9fcd
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548364"
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Attendi approvazione in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Creare un flusso che, se si crea un elemento in SharePoint, invii un messaggio di posta elettronica di approvazione e quindi notificherà se l'elemento è stato approvato o rifiutato. Per seguire esattamente questa esercitazione, creare un semplice elenco di SharePoint come azione di trigger, ma è possibile usare un'altra origine dati, ad esempio Dropbox o OneDrive.

**Prerequisiti**

* Creare un semplice elenco di SharePoint denominato **Project tracker**, aggiungere una colonna denominata **title**, quindi aggiungere una colonna Person o Group denominata **assegnato a**.

   ![Immagine dell'elenco di SPO di Project tracker](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Aggiungere un evento per attivare il flusso

1. Accedere [Microsoft Flow](https://flow.microsoft.com), selezionare **flussi personali** nella barra di spostamento in alto e quindi selezionare **Crea da zero**.

1. Selezionare la casella **Cerca tra centinaia di connettori e trigger** , immettere **nuovo elemento**, quindi passare a **SharePoint-quando viene creato un elemento**.

1. Se richiesto, accedere a SharePoint.
1. In **Indirizzo sito**immettere l'URL del sito di SharePoint contenente l'elenco.

1. In **nome elenco**selezionare l'elenco creato in precedenza. Se si sta seguendo la procedura, il nome sarà **Tracker progetto**.

    ![Immagine del nome dell'elenco di SPO](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Aggiungere l'azione risultante

1. Selezionare il pulsante **nuovo passaggio** e quindi selezionare **Aggiungi un'azione.**

1. Nella casella **Cerca tutti i connettori e le azioni** Digitare o incollare **Invia messaggio**e quindi selezionare **Office 365 Outlook-Invia messaggio di posta elettronica con opzioni**.

1. Se richiesto, accedere a Office 365 Outlook.

1. Selezionare il campo **a** e quindi selezionare il token **assegnato a posta elettronica** .

    L'utente nella colonna **assegnato a** riceve il messaggio di posta elettronica per approvare o rifiutare gli elementi. Quando si crea un elemento per testare il flusso, specificare se stessi in questo campo. In questo modo, non solo si approva o rifiuta l'elemento, ma si riceve anche il messaggio di posta elettronica di notifica.

    > [!NOTE]
    > È possibile personalizzare i campi **oggetto** e **Opzioni utente** in base alle esigenze.

    ![Immagine dell'invio del messaggio di posta elettronica di approvazione al campo](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Aggiungere una condizione

1. Selezionare il pulsante **nuovo passaggio** e quindi selezionare **Aggiungi una condizione**.

    ![Immagine di Aggiungi una condizione](./media/wait-for-approvals/add-a-condition.png)
1. Selezionare la prima casella e quindi selezionare il token **SelectedOption** .
1. Selezionare l'ultima casella e quindi digitare **approva**.

    ![Immagine della scheda della condizione](./media/wait-for-approvals/condition-card-2.png)

1. Nell'area **se sì** selezionare **Aggiungi un'azione**.

1. Nella casella **Cerca tutti i connettori e le azioni** Digitare o incollare **Invia messaggio**e quindi selezionare **Office 365 Outlook-invia un messaggio di posta elettronica**.

1. Nel campo **a** immettere un destinatario come **creato da posta elettronica**.

1. Nella casella **oggetto** specificare un oggetto.

    Selezionare, ad esempio, **assegnato a DisplayName**, digitare **Approved** con uno spazio su ciascun lato, quindi selezionare **title**.

1. Nella casella **corpo** specificare il corpo di un messaggio di posta elettronica, ad esempio **pronto per procedere con la fase successiva del progetto.**

    > [!NOTE]
    > La persona che ha creato l'elemento nell'elenco di SharePoint riceverà una notifica se il progetto è stato approvato o rifiutato.

    ![Immagine di sì-Send-email](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. Nell'area **se no** , ripetere gli ultimi cinque passaggi, eccetto modificare l' **oggetto** e il **corpo** in modo da indicare che il progetto è stato rifiutato.

     ![Immagine di No-Send-email](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Terminare e testare il flusso

1. Assegnare un nome al flusso e quindi selezionare **Crea flusso**.

     ![Immagine di create-Flow](./media/wait-for-approvals/create-flow.png)
1. Creare un elemento nell'elenco di SharePoint.

    Un messaggio di posta elettronica di approvazione viene inviato al destinatario specificato. Quando il destinatario seleziona **approva** o **rifiuta** in tale messaggio di posta elettronica, si riceverà un messaggio di posta elettronica che indica la risposta.

## <a name="learn-more"></a>Ulteriori informazioni

* [Procedura dettagliata per le approvazioni moderne](modern-approvals.md)
* Creare [approvazioni sequenziali](sequential-modern-approvals.md)
* Creare [approvazioni parallele](parallel-modern-approvals.md)
* Approva [le richieste in viaggio](mobile-approvals.md)
