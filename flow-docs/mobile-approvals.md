---
title: Approvare le richieste in un dispositivo mobile | Microsoft Docs
description: Usare un dispositivo mobile per approvare le richieste create in Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b41397d74c7396081154526ad2e248cb293e2460
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689595"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Approvare le richieste nel dispositivo mobile tramite Microsoft Flow
Se un flusso identifica l'utente come responsabile approvazione ed è stata installata l'app per dispositivi mobili per Microsoft Flow, l'utente riceverà una notifica push ogni volta che viene richiesta la sua approvazione.

Questo articolo illustra in modo dettagliato alcuni scenari comuni che possono verificarsi durante la gestione di richieste di approvazione nell'app per dispositivi mobili per Microsoft Flow.

> [!NOTE]
> Le immagini in questo argomento sono relative a un dispositivo Android, ma l'esperienza in iOS è simile.
> 
> 

## <a name="prerequisites"></a>Prerequisiti
Per completare questa procedura dettagliata, è necessario quanto segue:

* Un dispositivo [Android](https://aka.ms/flowmobiledocsandroid) o [iOS](https://aka.ms/flowmobiledocsios) che esegue l'app per dispositivi mobili per Microsoft Flow.
* Essere designati come responsabile approvazione in un flusso di approvazione.
* Richieste in attesa di approvazione.

## <a name="view-pending-requests"></a>Visualizzare le richieste in sospeso
1. Aprire l'app per dispositivi mobili per Microsoft Flow.
   
    ![Avviare l'app per dispositivi mobili](./media/mobile-approvals/open-app.png)
2. Selezionare **APPROVAZIONI** nell'angolo superiore destro.
   
    ![Selezionare le approvazioni](./media/mobile-approvals/select-approvals.png)
3. Visualizzare tutte le approvazioni in sospeso:
   
    ![Visualizzare le richieste di approvazione in sospeso](./media/mobile-approvals/show-pending-approval-requests.png)

Se non sono presenti richieste di approvazione in sospeso, creare un [flusso di approvazione](modern-approvals.md), impostare se stessi come responsabile approvazione e quindi attivare il flusso. Le richieste di approvazione vengono visualizzate nel Centro approvazioni pochi secondi dopo l'attivazione del flusso e l'invio di una richiesta per l'approvazione.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Approvare le richieste e inserire un commento facoltativo
1. Se non è già stato fatto, seguire la procedura precedente per [visualizzare le richieste in sospeso](mobile-approvals.md#view-pending-requests).
2. Selezionare **APPROVA** nella richiesta da approvare.
   
    ![Selezionare Approva](./media/mobile-approvals/select-approve.png)
3. (Facoltativo) Selezionare **Aggiungi un commento (facoltativo)**.
   
    ![Selezionare Aggiungi un commento](./media/mobile-approvals/select-add-comment.png)
   
    Immettere un commento nella schermata **Aggiungi un commento**.
   
    ![Immettere il commento](./media/mobile-approvals/enter-comment-for-approval.png)
4. Selezionare **CONFERMA** nell'angolo superiore destro.
   
    ![Confermare che le operazioni sono state completate](./media/mobile-approvals/tap-confirm-button.png)
   
    La schermata relativa all'esito positivo dell'operazione viene visualizzata dopo la registrazione della decisione da parte del flusso.
   
    ![Schermata relativa all'esito positivo dell'operazione](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Rifiutare le richieste e inserire un commento facoltativo
Seguire la [procedura per l'approvazione di una richiesta](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), ma selezionare **RIFIUTA** nel secondo passaggio.

## <a name="learn-more"></a>Altre informazioni
[Creare flussi di approvazione moderni](modern-approvals.md).

