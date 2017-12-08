---
title: "Automatizzare le attività con la creazione di un flusso | Microsoft Docs"
description: "Creare un flusso per eseguire automaticamente una o più azioni, ad esempio l'invio di posta elettronica, quando si verificano determinati eventi, ad esempio un utente aggiunge una riga a un elenco di SharePoint."
services: 
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: deonhe
ms.openlocfilehash: fd6ed3973ed09442108bf780f76b750deea20eeb
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-in-microsoft-flow"></a>Creare un flusso in Microsoft Flow
<iframe width="560" height="315" src="https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Creare un flusso che esegue automaticamente una o più attività dopo che viene attivato da un evento. Ad esempio, creare un flusso di notifica via posta elettronica quando un utente invia un tweet che contiene una parola chiave specificata. In questo esempio, l'invio di un tweet è l'evento e l'invio di posta elettronica è l'azione.

## <a name="prerequisites"></a>Prerequisiti
* Un account in [flow.microsoft.com](https://flow.microsoft.com)
* Un account Twitter
* Credenziali di Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Specificare un evento per avviare il flusso
Prima di tutto, è necessario selezionare quale evento, o *trigger*, avvia il flusso.

1. In [flow.microsoft.com](https://flow.microsoft.com) selezionare **Flussi personali** nella barra di spostamento in alto e quindi scegliere **Crea da zero**.
   
    ![Opzione Flussi nella barra di spostamento a sinistra](./media/get-started-logic-flow/create-logic-flow.png)
2. Nella casella di testo **Cerca tutti i connettori e i trigger** digitare o incollare **Twitter**, quindi selezionare **Twitter - Quando viene pubblicato un nuovo tweet**.
   
    ![Evento di Twitter](./media/get-started-logic-flow/twitter-search.png)
3. Se il proprio account Twitter non è stato ancora connesso a Microsoft Flow, selezionare **Eseguire l'accesso per creare una connessione a Twitter.**, quindi fornire le credenziali.
   
    ![Accesso a Twitter](./media/get-started-logic-flow/twitter-signin.png)
4. Nella casella **Cerca testo** digitare la parola chiave da cercare.
   
    ![Parola chiave di Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Specificare un'azione
1. Selezionare **Nuovo passaggio**, quindi scegliere **Aggiungi un'azione**.
   
    ![Aggiungere un'azione](./media/get-started-logic-flow/add-action-icon.png)
2. Nella finestra **Cerca tutti i connettori e le azioni** digitare o incollare **invia e-mail**, quindi selezionare **Office 365 Outlook - Invia un messaggio di posta elettronica**.
   
    ![Elenco di azioni](./media/get-started-logic-flow/send-email.png)
3. Se richiesto, selezionare il pulsante di accesso e quindi fornire le credenziali.
4. Nel modulo visualizzato, digitare o incollare l'indirizzo di posta elettronica nella casella **A**, quindi selezionare il nome dall'elenco dei contatti visualizzato.
   
    ![Messaggio di posta elettronica vuoto](./media/get-started-logic-flow/blank-email.png)
5. Nella casella **Oggetto** digitare o incollare **Nuovo tweet da:**, quindi digitare uno spazio.
   
    ![Riga dell'oggetto con segnaposto](./media/get-started-logic-flow/message-token.png)
6. Nell'elenco dei token selezionare **Twittato da** per aggiungere un segnaposto a questo token.
   
    ![Aggiungi parametro](./media/get-started-logic-flow/add-parameter.png)
7. Scegliere o toccare la casella **Corpo** quindi scegliere o toccare **Testo tweet** per aggiungere un segnaposto a questo token.
8. (Facoltativo) Aggiungere altri token e/o altri contenuti al corpo del messaggio e-mail.
9. Nella parte superiore della schermata, assegnare un nome al flusso e selezionare **Crea flusso**.
   
    ![Selezionare il pulsante Crea flusso.](./media/get-started-logic-flow/create-button.png)
10. Selezionare **Fine** per aggiornare l'elenco dei flussi personali.
    
     ![Selezionare il pulsante Fine](./media/get-started-logic-flow/done-button.png)
11. Inviare un tweet con la parola chiave indicata.
    
     Entro un minuto, un messaggio di posta elettronica notificherà del nuovo tweet.

## <a name="manage-a-flow"></a>Gestire un flusso
1. In [flow.microsoft.com](https://flow.microsoft.com), selezionare **Flussi personali** nella barra di spostamento in alto.
2. Nell'elenco dei flussi, effettuare una delle operazioni seguenti:
   
   * Per sospendere un flusso, impostarlo su **Off**.
     
       ![Sospendere il flusso](./media/get-started-logic-flow/pause-flow.png)
   * Per riprendere un flusso, impostarlo su **On**.
     
       ![Riprendere il flusso](./media/get-started-logic-flow/resume-flow.png)
   * Per modificare un flusso, selezionare l'icona della matita corrispondente al flusso di cui che si vuole modificare.
     
       ![Selezionare un flusso](./media/get-started-logic-flow/select-flow.png)
   * Per eliminare un flusso, selezionare l'icona **...**, selezionare **Elimina**, quindi selezionare **Elimina** nella finestra del messaggio visualizzata.
     
       ![Icona Elimina](./media/get-started-logic-flow/delete-icon.png)
   * Per visualizzare la cronologia di esecuzione di un flusso, selezionare il flusso dalla pagina **Flussi personali** e quindi visualizzare la cronologia nella sezione **Cronologia di esecuzione** della pagina che viene aperta.
     
       ![cronologia di esecuzione](./media/get-started-logic-flow/run-history.png)
     
     Selezionare un'esecuzione del flusso dall'elenco delle esecuzioni per visualizzare gli input e output di ogni passaggio.

**Nota**: è possibile avere fino a 50 flussi nel proprio account. Se si hanno già 50 flussi, eliminarne uno prima di poterne creare un altro.

## <a name="next-steps"></a>Passaggi successivi
* [Aggiungere dei passaggi](multi-step-logic-flow.md), ad esempio diversi modi per ricevere una notifica, al flusso.
* [Eseguire attività in una pianificazione](run-tasks-on-a-schedule.md), quando si vuole che un'azione sia eseguita ogni giorno, in una determinata data o dopo un certo numero di minuti.
* [Aggiungere un flusso a un'app](https://powerapps.microsoft.com/tutorials/using-logic-flows/) per consentire all'app di avviare la logica nel cloud.
* [Introduzione ai flussi del team](create-team-flows.md) e invio di inviti ad altri utenti per collaborare alla progettazione dei flussi.
