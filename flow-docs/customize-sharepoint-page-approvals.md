---
title: Gestire le approvazioni delle pagine di SharePoint con Microsoft Flow | Microsoft Docs
description: Informazioni su come gestire le approvazioni delle pagine di SharePoint con Microsoft Flow..
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 1b328b604f9b199c2303dde3a0aa00898f188ada
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547639"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Gestione delle approvazioni delle pagine di SharePoint con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Gli amministratori del sito di SharePoint possono utilizzare Microsoft Flow per richiedere l'approvazione di pagine del sito nuove o aggiornate prima della pubblicazione.

In questo articolo si apprenderà come configurare il sito di SharePoint per l'uso di un flusso per richiedere l'approvazione delle modifiche apportate al sito prima che siano attive.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurare SharePoint per le approvazioni della pagina

### <a name="prerequisites"></a>Prerequisiti 

Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore del sito di SharePoint.

1. Accedere a SharePoint come amministratore del sito.
1. Selezionare **pagine** dalla barra di spostamento.

    ![Selezionare il flusso di approvazione della pagina](media/customize-sharepoint-page-approvals/pages.png)

1. Selezionare **Flow** , quindi selezionare **Configura flusso di approvazione pagina**.
    
    ![Selezionare il flusso di approvazione della pagina](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Specificare un **nome di flusso**, almeno un nome nella casella **responsabili approvazione** , quindi selezionare **Crea**.
    
    ![Selezionare il flusso di approvazione della pagina](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Questo è tutto! A questo punto, ogni volta che viene aggiunta o modificata una pagina, viene inviata una richiesta di approvazione ai **responsabili approvazione** elencati nel flusso.

Il flusso di approvazione della pagina è analogo a qualsiasi altro flusso, quindi è elencato nella scheda **flussi personali** .

![Selezionare il flusso di approvazione della pagina](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Invia una pagina per l'approvazione

Ora che è stato creato un flusso di approvazione della pagina, tutti gli utenti che aggiungono o modificano una pagina dovranno eseguire le operazioni seguenti:

 - Apportare una modifica al sito (ad esempio, aggiungere una nuova pagina), quindi salvare la modifica.

     ![Invia pagina per l'approvazione](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Attendere che qualcuno approvi la modifica.
    
    ![Invia pagina per l'approvazione](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Approva una pagina

I responsabili approvazione ricevono un messaggio di posta elettronica ogni volta che è presente una richiesta di approvazione della pagina. Possono approvare le richieste direttamente nel messaggio di posta elettronica (se il client di posta elettronica supporta i messaggi di utilità) o aprire la pagina dal messaggio di posta elettronica da rivedere e quindi approvare la pagina in SharePoint.

## <a name="customize-page-approval-flows"></a>Personalizzare i flussi di approvazione della pagina

Poiché le approvazioni di pagina usano Microsoft Flow dietro le quinte, il flusso di approvazione della pagina è disponibile per i proprietari del sito per modificare e aggiungere qualsiasi logica di business personalizzata nel flusso. Per modificare il flusso, il proprietario del sito può selezionare **flussi** e quindi selezionare **Visualizza flussi** nella libreria di pagine per trovare il flusso di approvazione della pagina.

## <a name="learn-more"></a>Ulteriori informazioni

- [Flusso di approvazione della pagina](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurare l'approvazione della pagina](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
