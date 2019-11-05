---
title: Informazioni su come creare e gestire i flussi in Microsoft Teams | Microsoft Docs
description: Crea e Gestisci flussi per inviare messaggi su richiesta, @mention utenti e canali, pubblicare schede con opzioni di risposta e altro ancora.
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
ms.openlocfilehash: 34cb8577d57d70686fd9811db9146443b56a07b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547985"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow nei team
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

### <a name="prerequisites"></a>Prerequisiti

1. Accesso a Microsoft teams.
1. Accesso a Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Installare l'app Microsoft Flow in teams

Seguire questa procedura per installare l'app Microsoft Flow in Microsoft teams.

1. Accedere a Microsoft teams.

1. Toccare l'icona **app** nella parte inferiore sinistra della barra di spostamento teams.

    ![Selezionare le app](media/flows-teams/apps.png)

1. Selezionare l'app Microsoft **Flow** . Potrebbe essere necessario cercare **Flow** se non viene visualizzato.

    ![Selezionare l'app Microsoft Flow](media/flows-teams/select-flow-app.png)

1. Selezionare **Installa**.

    ![Pulsante Installa](media/flows-teams/select-install.png)

1. Microsoft Flow ora è installato.

    ![Installato](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Creare un flusso nei team

1. Accedere a Microsoft teams.

1. Selezionare il collegamento **app più aggiunte** (...) nella barra di spostamento e quindi selezionare l'app Microsoft **Flow** .

    ![Icona app aggiunta](media/flows-teams/added-apps-icon.png)

1. Se non è ancora stato fatto, potrebbe essere necessario eseguire l'accesso e concedere le autorizzazioni.

    ![Accedi](media/flows-teams/grant-permissions-sign-in.png)


    Si notino le schede seguenti:

    ![Pagina di destinazione del flusso](media/flows-teams/flow-landing-page.png)

    Nome|Scopo
    ----|-----|
    Conversazione|Interagire con il bot Microsoft Flow.
    Flussi|Creare e gestire i flussi.
    Approvazioni|Elenca le richieste di approvazione ricevute e inviate.
    Su|Visualizza la versione e altre informazioni sul Microsoft Flow.


    Verranno ora visualizzati tutti i flussi creati dalla finestra di progettazione Microsoft Flow (se presente). 

    È anche possibile creare flussi da un modello personalizzato o da un modello vuoto, esattamente come avviene dalla finestra di progettazione Microsoft Flow. 

## <a name="manage-approvals"></a>Gestisci approvazioni

È possibile gestire le [approvazioni](modern-approvals.md) in Microsoft teams, proprio come in Microsoft Flow. Per gestire le approvazioni, attenersi alla procedura seguente:

1. Accedere a Microsoft teams.
1. Selezionare la scheda **approvazioni** .

    ![Scheda Approvazioni](media/flows-teams/approvals-tab.png)

    Si noteranno le sottoschede seguenti:

    Scheda|Scopo
    ----|-----|
    Ricevuto|Elenca le richieste di approvazione ricevute ed è in attesa di un'azione da te.
    Inviati|Elenca le richieste di approvazione inviate ed è in attesa di un'azione da altri.
    Cronologia|Elenca le richieste di approvazione ricevute e inviate.
    Crea flusso di approvazione|Creare flussi di approvazione.

1. Per ulteriori informazioni, selezionare le schede **ricevuto**, **inviato**o **cronologia** .

    ![Scheda Approvazioni](media/flows-teams/approvals-tab-2.png)

1. Selezionare **Crea flusso di approvazione** per creare un flusso di approvazione.

    ![Scheda Approvazioni](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Usare il bot con i flussi

### <a name="list-and-launch-flows-with-the-bot"></a>Elencare e avviare i flussi con il bot

> [!TIP]
> Il bot elenca ed esegue i flussi attivati da una pianificazione o attivati manualmente senza l'input dell'utente.

1. Accedere a Microsoft teams.
1. Selezionare il collegamento **app più aggiunte** (...) nella barra di spostamento e quindi selezionare l'app Microsoft **Flow** .

    ![Icona app aggiunta](media/flows-teams/added-apps-icon.png)
    
1. Selezionare la scheda **conversazione** .

    ![Scheda conversazione](media/flows-teams/conversations-tab.png)

Nella scheda **conversazione** è possibile inviare comandi al bot, che risponde eseguendo le azioni che si desidera eseguire. Per elencare i flussi ed eseguire il flusso con indice 1, ad esempio, eseguire i comandi seguenti:

- ```List flows```: il bot Visualizza un elenco dei flussi, preceduti da un numero di indice.
- ```Run flow 1```-esegue il flusso numero 1. Qui *1* è il numero di indice del flusso che si vuole eseguire.

   ![Comandi bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Ottenere la descrizione dei flussi

Per ottenere la descrizione del flusso con indice 1 dall'elenco dei flussi, eseguire ```describe flow 1```. La risposta bot sarà simile a questa immagine:

   ![Descrivere i flussi](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Ottenere l'elenco dei comandi per il bot

Per ottenere l'elenco dei comandi gestiti dal bot, rivolgersi a questo comando: ```learn more``` 

La risposta bot sarà simile a questa immagine:

![Descrivere i flussi](media/flows-teams/bot-learn-more.png) 
