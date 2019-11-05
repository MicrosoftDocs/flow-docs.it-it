---
title: Creare un flusso di promemoria per gli elementi di SharePoint | Microsoft Docs
description: Creazione di flussi che consentono di ricordare le date di scadenza per gli elementi di SharePoint.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/30/2019
ms.author: deonhe
ms.openlocfilehash: c7c87df5288ba58d303de441b41e7493cd713f4a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547558"
---
# <a name="sharepoint-remind-me"></a>Avviso di SharePoint
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Gli elenchi e le librerie di SharePoint consentono di definire colonne di metadati personalizzate per tenere traccia delle date. Con l'integrazione di Microsoft Flow con SharePoint, è possibile creare facilmente flussi di promemoria in base alle colonne DateTime in SharePoint. Con i flussi di promemoria, si riceve un avviso di posta elettronica personale per un numero predeterminato di giorni prima di una data in un documento o in un elemento in SharePoint.

## <a name="prerequisites"></a>Prerequisiti
- Accesso a Microsoft SharePoint Online.
- Un elenco di SharePoint o una raccolta con una colonna DateTime.
- Accesso a Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Creare un flusso di promemoria

 1. Creare un [elenco di SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) con almeno una colonna DateTime nella visualizzazione corrente. 
 1. Selezionare **Flow** > **impostare un promemoria** > **Data disattivato** (si tratta della colonna con DateTime per il promemoria).

     ![Selezionare il flusso di promemoria](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Specificare un **nome di flusso** e il numero di giorni prima della voce della colonna DateTime quando si desidera ricevere l'avviso di promemoria sulla scheda di **promemoria impostata** .

    ![Imposta i dettagli del flusso di promemoria](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Selezionare **Crea** nella scheda **imposta un promemoria** .

1. Si riceverà il messaggio seguente, che indica che il flusso è stato creato:

    ![Flusso di promemoria creato](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Conferma promemoria ricevuti

Si riceverà un promemoria tramite posta elettronica, in base alla voce **ricorda questo numero di giorni** prima che è stato creato un flusso di **promemoria** creato in precedenza. 

## <a name="edit-your-flow"></a>Modificare il flusso

Il flusso di promemoria è analogo a qualsiasi altro flusso, quindi è possibile accedervi e modificarlo tramite [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Ulteriori informazioni

- Introduzione a [Microsoft Flow](https://flow.microsoft.com).
- Impostare un [flusso di promemoria](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) in SharePoint.


