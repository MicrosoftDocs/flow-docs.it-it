---
title: Approva le richieste in un dispositivo mobile | Microsoft Docs
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
ms.openlocfilehash: a71d1e53199f0dacfc2086812cc3cd2fd9585f4d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548681"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Approvare le richieste sul dispositivo mobile usando Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Se un flusso identifica l'utente come responsabile approvazione ed è stata installata l'app per dispositivi mobili per Microsoft Flow, si riceverà una notifica push ogni volta che viene richiesta l'approvazione.

Questo articolo illustra alcuni scenari comuni che è probabile che si verifichino quando si gestiscono le richieste di approvazione nell'app per dispositivi mobili per Microsoft Flow.

> [!NOTE]
> Le immagini in questo argomento sono da un dispositivo Android; Tuttavia, l'esperienza su iOS è simile.
> 
> 

## <a name="prerequisites"></a>Prerequisiti
Per completare questa procedura dettagliata, è necessario:

* Un dispositivo [Android](https://aka.ms/flowmobiledocsandroid) o [iOS](https://aka.ms/flowmobiledocsios) che esegue l'app per dispositivi mobili per Microsoft Flow.
* Da designare come responsabile approvazione in un flusso di approvazione.
* Richieste di approvazione in sospeso.

## <a name="view-pending-requests"></a>Visualizza richieste in sospeso
1. Aprire l'app per dispositivi mobili per Microsoft Flow.
   
    ![avviare l'app per dispositivi mobili](./media/mobile-approvals/open-app.png)
2. Selezionare **approvazioni** nell'angolo superiore destro.
   
    ![Selezionare le approvazioni](./media/mobile-approvals/select-approvals.png)
3. Visualizza tutte le approvazioni in sospeso:
   
    ![vedere le richieste di approvazione in sospeso](./media/mobile-approvals/show-pending-approval-requests.png)

Se non sono presenti richieste di approvazione in sospeso, creare un [flusso di approvazione](modern-approvals.md), impostare se stessi come responsabile approvazione, quindi attivare il flusso. Le richieste di approvazione vengono visualizzate nel centro di approvazione pochi secondi dopo il trigger del flusso e inviano una richiesta di approvazione.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Approva le richieste e lascia un commento facoltativo
1. Se non è ancora stato fatto, seguire i passaggi precedenti per [visualizzare le richieste in sospeso](mobile-approvals.md#view-pending-requests).
2. Selezionare **approva** nella richiesta che si desidera approvare.
   
    ![Selezionare approva](./media/mobile-approvals/select-approve.png)
3. (Facoltativo) selezionare **Aggiungi commento (facoltativo)** .
   
    ![Selezionare Aggiungi un commento](./media/mobile-approvals/select-add-comment.png)
   
    Immettere un commento nella schermata **Aggiungi commento** .
   
    ![Immettere il commento](./media/mobile-approvals/enter-comment-for-approval.png)
4. Selezionare **conferma** nell'angolo superiore destro.
   
    ![confermare il completamento](./media/mobile-approvals/tap-confirm-button.png)
   
    Quando il flusso registra la decisione, viene visualizzata la schermata operazione completata.
   
    ![schermata operazione completata](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Rifiuta le richieste e lascia un commento facoltativo
Seguire i [passaggi per approvare una richiesta](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), ma selezionare **rifiuta** nel secondo passaggio.

## <a name="learn-more"></a>Ulteriori informazioni
[Creare flussi di approvazione moderni](modern-approvals.md).

