---
title: Creare un flusso di promemoria per gli elementi di SharePoint | Microsoft Docs
description: Creare flussi che promemoria di scadenza date per gli elementi di SharePoint.
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
ms.openlocfilehash: b0f1aa80fb92c9718d2b0697d3abb0b0d2478013
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061113"
---
# <a name="sharepoint-remind-me"></a>SharePoint un promemoria

Raccolte ed elenchi di SharePoint consentono di definire colonne di metadati personalizzati per tenere traccia delle date. Con l'integrazione di Microsoft Flow con SharePoint, è possibile creare facilmente flussi di promemoria, in base alle colonne di data/ora in SharePoint. Con i flussi di promemoria, viene visualizzato un avviso di posta elettronica personali un numero predeterminato di giorni prima che una data in qualsiasi elemento o documento in SharePoint.

## <a name="prerequisites"></a>Prerequisiti
- Accesso a Microsoft SharePoint Online.
- Un elenco di SharePoint, o una raccolta con una colonna DateTime.
- Avere accesso a Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Creare un flusso di promemoria

 1. Creare un [elenco di SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) con almeno una colonna di tipo DateTime nella visualizzazione corrente. 
 1. Selezionare **Flow** > **impostare un promemoria** > **data disattivato** (si tratta della colonna con il valore DateTime per il promemoria).

     ![Selezionare il flusso di promemoria](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Fornire una **il nome del flusso** e il numero di giorni prima della voce di colonna di data/ora quando si desidera ricevere l'avviso di promemoria sul **impostare un promemoria** carta.

    ![Impostare i dettagli dei flussi di promemoria](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Selezionare **Create** nel **imposta un promemoria** carta.

1. Si riceverà il messaggio seguente, che indica che il flusso è stato creato:

    ![Flusso del promemoria creato](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Verificare che i promemoria ricevuti

Si riceverà un promemoria tramite posta elettronica, in base il **ricorda questo molti giorni in anticipo** apportate in ingresso il **impostare un promemoria** flusso creato in precedenza. 

## <a name="edit-your-flow"></a>Modificare il flusso

Il flusso di promemoria è simile a qualsiasi altro flusso, in modo che è possibile accedere e modificare tramite [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Altre informazioni

- Guida introduttiva [Microsoft Flow](https://flow.microsoft.com).
- Impostare una [flow promemoria](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) in SharePoint.


