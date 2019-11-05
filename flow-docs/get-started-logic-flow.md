---
title: Automatizzare le attività creando un flusso | Microsoft Docs
description: Creare un flusso che esegua automaticamente una o più azioni, ad esempio l'invio di messaggi di posta elettronica, quando si verificano eventi come quelli che aggiungono una riga a un elenco di SharePoint.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 494a5f978b7792fa971a53cfda85addd9b78f929
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548317"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Creare un flusso in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Creare un flusso che esegua una o più attività automaticamente dopo che è stato attivato da un evento. Ad esempio, creare un flusso che invia una notifica tramite posta elettronica quando un utente invia un tweet che contiene una parola chiave specificata. In questo esempio, l'invio di un tweet è l'evento e l'invio della posta elettronica è l'azione.

## <a name="prerequisites"></a>Prerequisiti

* Un account in [Flow.Microsoft.com](https://flow.microsoft.com)
* Un account Twitter
* Credenziali di Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Specificare un evento per avviare il flusso

Prima di tutto, è necessario selezionare l'evento, o *trigger*, che avvia il flusso.

1. In [Flow.Microsoft.com](https://flow.microsoft.com)selezionare **flussi personali** nella barra di spostamento in alto e quindi selezionare **Crea da zero**.

    ![Opzione Flows nella barra di spostamento a sinistra](./media/get-started-logic-flow/create-logic-flow.png)
1. Selezionare la casella **Cerca tra centinaia di connettori e trigger** nella parte inferiore della schermata, immettere **Twitter** nella casella **Cerca tutti i connettori e i trigger**, quindi selezionare **Twitter-quando viene pubblicato un nuovo Tweet**.

    ![Evento Twitter](./media/get-started-logic-flow/twitter-search.png)

1. Se l'account Twitter non è ancora stato connesso a Microsoft Flow, selezionare **Accedi a Twitter**e quindi specificare le credenziali.

1. Nella casella di **testo Cerca** Digitare la parola chiave che si desidera trovare.

    ![Parola chiave Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Specificare un'azione

1. Selezionare **nuovo passaggio**, quindi selezionare **Aggiungi un'azione**.

    ![Aggiungi azione](./media/get-started-logic-flow/add-action-icon.png)

1. Nella finestra di dialogo **Cerca tutti i connettori e le azioni**Digitare o incollare **Invia messaggio**e quindi selezionare **Office 365 Outlook-invia un messaggio di posta elettronica**.

    ![Elenco di azioni](./media/get-started-logic-flow/send-email.png)

1. Se richiesto, selezionare il pulsante di accesso e quindi specificare le credenziali.

1. Nel modulo visualizzato, digitare o incollare l'indirizzo di posta elettronica nella casella **a** , quindi selezionare il nome dall'elenco dei contatti visualizzato.

    ![Messaggio di posta elettronica vuoto](./media/get-started-logic-flow/blank-email.png)
1. Nella casella **oggetto** Digitare o incollare **nuovo Tweet da:** , quindi digitare uno spazio.

    ![Riga dell'oggetto con segnaposto](./media/get-started-logic-flow/message-token.png)
1. Nell'elenco dei token selezionare il token **tweeted by** per aggiungere un segnaposto.

    ![Aggiungi parametro](./media/get-started-logic-flow/add-parameter.png)
1. Selezionare la casella **corpo** e quindi selezionare il token di **testo Tweet** per aggiungere un segnaposto.
1. opzionale Aggiungere altri token, altro contenuto o entrambi al corpo del messaggio di posta elettronica.
1. Nella parte superiore della schermata assegnare un nome al flusso e quindi selezionare **Crea flusso**.

    ![Selezionare il pulsante Crea flusso](./media/get-started-logic-flow/create-button.png)
1. Selezionare **fine** per aggiornare l'elenco dei flussi.

     ![Selezionare il pulsante fine](./media/get-started-logic-flow/done-button.png)
1. Inviare un tweet con la parola chiave indicata o attendere che qualcun altro invii un tweet di questo tipo.

     Entro un minuto dalla pubblicazione del tweet, un messaggio di posta elettronica informa l'utente del nuovo Tweet.

> [!TIP]
> Usare l'azione **Invia messaggio di posta elettronica (v2)** per formattare la posta elettronica in cui si Personalizza il tipo di carattere, usare grassetto, corsivo o sottolineatura, personalizzare il colore e evidenziare e creare elenchi o collegamenti e altro ancora.

![Posta elettronica Rich Edit](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Gestire un flusso

1. In [Flow.Microsoft.com](https://flow.microsoft.com)selezionare **flussi personali** nella barra di spostamento superiore.
1. Nell'elenco dei flussi eseguire una delle operazioni seguenti:

   * Per sospendere un flusso, impostare l'interruttore su **disattivato**.

       ![Sospendi flusso](./media/get-started-logic-flow/pause-flow.png)
   * Per riprendere un flusso, impostare l'interruttore **su on**.

       ![Riprendere il flusso](./media/get-started-logic-flow/resume-flow.png)
   * Per modificare un flusso, selezionare l'icona a matita che corrisponde al flusso che si vuole modificare.

       ![Selezionare il flusso](./media/get-started-logic-flow/select-flow.png)
   * Per eliminare un flusso, selezionare l'icona **...** , selezionare **Elimina**e quindi fare clic su **Elimina** nella finestra di messaggio visualizzata.

       ![Icona Elimina](./media/get-started-logic-flow/delete-icon.png)
   * Per visualizzare la cronologia di esecuzione di un flusso, selezionare il flusso dalla pagina **flussi personali** e quindi visualizzare la cronologia nella sezione **cronologia di esecuzione** della pagina visualizzata.

       ![cronologia di esecuzione](./media/get-started-logic-flow/run-history.png)

     Selezionare un'esecuzione del flusso dall'elenco di esecuzioni per visualizzare gli input e gli output di ogni passaggio.

> [!NOTE]
> È possibile avere fino a 600 flussi nell'account. Se sono già presenti 600 flussi, eliminarne uno prima di creare un altro flusso.
>
>

## <a name="next-steps"></a>Passaggi successivi

* [Aggiungere i passaggi](multi-step-logic-flow.md), ad esempio modi diversi per ricevere una notifica, al flusso.
* [Eseguire le attività in base a una pianificazione](run-scheduled-tasks.md), quando si vuole che un'azione venga eseguita ogni giorno, in una determinata data o dopo un certo numero di minuti.
* [Aggiungere un flusso a un'app](https://powerapps.microsoft.com/tutorials/using-logic-flows/) per consentire all'app di avviare la logica nel cloud.
* [Inizia a usare i flussi del team](create-team-flows.md) e invita altri utenti a collaborare con te per progettare i flussi.
