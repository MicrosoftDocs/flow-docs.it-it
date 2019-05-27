---
title: Gestire le approvazioni di pagina di SharePoint con Microsoft Flow | Microsoft Docs
description: Informazioni su come gestire le approvazioni di pagina di SharePoint con Microsoft Flow...
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
ms.openlocfilehash: d5e01a3d2e13cc48107e19e0e2bbea3821437273
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061343"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Gestire le approvazioni di pagina di SharePoint con Microsoft Flow

Gli amministratori del sito di SharePoint è possono usare Microsoft Flow per richiedere le pagine del sito nuovo o aggiornato per essere approvata prima della pubblicazione.

In questo articolo si apprenderà come configurare il sito di SharePoint per usare un flusso per richiedere modifiche al sito per essere approvata prima della pubblicazione.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurare SharePoint per le approvazioni di pagina

### <a name="prerequisites"></a>Prerequisiti 

È necessario essere un amministratore di sito di SharePoint per eseguire le attività in questo articolo.

1. Accedere a SharePoint come un amministratore del sito.
1. Selezionare **pagine** dalla barra di spostamento.

    ![Selezionare il flusso di approvazione di pagina](media/customize-sharepoint-page-approvals/pages.png)

1. Selezionare **Flow** e quindi selezionare **Configura flusso di approvazione pagina**.
    
    ![Selezionare il flusso di approvazione di pagina](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Fornire un **il nome del flusso**, almeno un nome nel **responsabili approvazione** e quindi selezionare **Create**.
    
    ![Selezionare il flusso di approvazione di pagina](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Questo è tutto! A questo punto, ogni volta che una pagina viene aggiunto o modificata, passa una richiesta di approvazione per il **responsabili approvazione** è elencato nel flusso.

Il flusso di approvazione di pagina è proprio come qualsiasi altro flusso, in modo che sia elencato nel **flussi personali** scheda.

![Selezionare il flusso di approvazione di pagina](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Inviare una pagina di approvazione

Ora che è stato creato un flusso di approvazione di pagina, tutti gli utenti che aggiunge o modifica una pagina sarà necessario eseguire le operazioni seguenti:

 - Apportare una modifica al sito (aggiungere una nuova pagina, ad esempio) e quindi salvare la modifica.

     ![Invia una pagina di approvazione](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Attendere che un utente di approvare la modifica.
    
    ![Invia una pagina di approvazione](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Approva una pagina

I responsabili approvazione ricevono un messaggio di posta elettronica ogni volta che una richiesta di approvazione di pagina. È possibile approvare le richieste direttamente nel messaggio di posta elettronica (se i client di posta elettronica supporta messaggi interattivi) o aprire la pagina dal messaggio di posta elettronica per rivedere e quindi approvare la pagina in SharePoint.

## <a name="customize-page-approval-flows"></a>Personalizzare i flussi di approvazione di pagina

Poiché le approvazioni pagina usano Microsoft Flow dietro le quinte, il flusso di approvazione di pagina è disponibile per i proprietari del sito modificare e aggiungere una logica di business personalizzata nel flusso. Per modificare il flusso, è possibile selezionare il proprietario del sito **flussi** e quindi selezionare **vedere i flussi** nella libreria di pagine per trovare il flusso di approvazione di pagina.

## <a name="learn-more"></a>Altre informazioni

- [Flusso di approvazione di pagina](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurare l'approvazione di pagina](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
