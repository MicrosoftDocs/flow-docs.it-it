---
title: Creare flussi dal pannello di avvio di OneDrive for business | Microsoft Docs
description: Creare flussi dal pannello di avvio di OneDrive for business.
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
ms.date: 08/25/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d7ed30741fcc85fea87f5be2d76a8150a0c42100
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548588"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>Creare flussi dal pannello di avvio di OneDrive for business
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Analogamente al [pannello Microsoft Flow Launch in SharePoint](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/), è possibile eseguire i flussi in file specifici in OneDrive for business. 

Questa funzionalità consente all'utente che esegue il flusso di usare le proprie credenziali, che è particolarmente applicabile per i flussi creati da un reparto IT. 

Gli utenti possono anche ottenere richieste di input di runtime come il **responsabile approvazione** o il **messaggio**, che può essere di tipo testo, file, messaggio di posta elettronica, valore booleano o numero.

In questa procedura dettagliata verrà creato un flusso semplice che usa uno dei molti modelli di [OneDrive for business](https://flow.microsoft.com/search/?q=OneDrive) per richiedere l'approvazione di un file dal responsabile del richiedente.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>Creare un flusso che richiede l'approvazione del responsabile per un file in OneDrive for business

1. Accedere a OneDrive for business.
1. Trovare, quindi selezionare il file in cui si vuole creare il flusso.
1. Selezionare il collegamento **Mostra azioni** (tre punti).
1. Selezionare **flow** > **creare un flusso**.

     ![Crea flusso](./media/onedrive-launch-panel/create-flow.png) 

1. Selezionare uno dei modelli.

    In questo esempio selezionare la **richiesta di approvazione del responsabile per il modello di file selezionato** .

     >[!TIP]
     >Accedere a tutti i connettori che richiedono l'accesso.

1. Selezionare **continua**.
1. Apportare le modifiche desiderate al modello, quindi salvare il flusso con un nome che si ricorda con facilità.

## <a name="run-the-flow"></a>Eseguire il flusso

1. Accedere a OneDrive for business.
1. Trovare, quindi selezionare il file in cui è richiesta l'approvazione del responsabile.
1. Selezionare il collegamento **Mostra azioni** (tre punti).
1. Selezionare **Flow**. Verrà visualizzato il flusso creato in precedenza.
1. Selezionare il flusso creato in precedenza.

     ![Eseguire il flusso](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>Mentre questa procedura dettagliata illustra come creare un flusso da un modello, è anche possibile creare un flusso da zero per usare uno dei centinaia di connettori disponibili in Microsoft Flow.

## <a name="learn-more"></a>Ulteriori informazioni

- [Inizia a usare Microsoft Flow](getting-started.md) 
- [Creazione di flussi in più passaggi](multi-step-logic-flow.md)
