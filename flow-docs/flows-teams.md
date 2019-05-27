---
title: Informazioni su come creare e gestire flussi in Microsoft Teams | Microsoft Docs
description: Creare e gestire flussi per pubblicare messaggi on demand, @mention utenti e canali, pubblicare schede con opzioni di risposta e altro ancora.
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
ms.openlocfilehash: 4987d1f4fb504c0279540eb86dcb6ad1b983ff4a
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061849"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow in Teams

### <a name="prerequisites"></a>Prerequisiti

1. Avere accesso a Microsoft Teams.
1. Avere accesso a Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Installare l'app Microsoft Flow in Teams

Seguire questa procedura per installare l'app Microsoft Flow in Microsoft Teams.

1. Eseguire l'accesso a Microsoft Teams.

1. Toccare l'icona **App** nell'angolo in basso a sinistra della barra di spostamento di Teams.

    ![Selezionare le app](media/flows-teams/apps.png)

1. Selezionare l'app **Flow**. Potrebbe essere necessario cercare **Flow** se l'app non è visualizzata.

    ![Selezionare l'app Flow](media/flows-teams/select-flow-app.png)

1. Selezionare **Installa**.

    ![Pulsante Installa](media/flows-teams/select-install.png)

1. Microsoft Flow è ora installato.

    ![Installato](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Creare un flusso in Teams

1. Eseguire l'accesso a Microsoft Teams.

1. Selezionare il collegamento **Ulteriori app aggiunte** (...) nella barra di spostamento e quindi selezionare l'app **Flow**.

    ![Icona App aggiunte](media/flows-teams/added-apps-icon.png)

1. Se non è ancora stato fatto, potrebbe essere necessario eseguire l'accesso e concedere le autorizzazioni.

    ![Accedi](media/flows-teams/grant-permissions-sign-in.png)


    Prestare attenzione alle schede seguenti:

    ![Pagina di destinazione di Flow](media/flows-teams/flow-landing-page.png)

    Nome|Scopo
    ----|-----|
    Conversazione|Interagire con il bot di Flow.
    Flussi|Creare e gestire i flussi.
    Approvazioni|Elenca le richieste di approvazione ricevute e inviate.
    Informazioni su|Visualizza la versione e altre informazioni su Microsoft Flow.


    È ora possibile visualizzare tutti i flussi creati dalla finestra di progettazione di Microsoft Flow (se presenti). 

    È anche possibile creare flussi da un modello personalizzato o da un modello vuoto, proprio come si farebbe dalla finestra di progettazione di Microsoft Flow. 

## <a name="manage-approvals"></a>Gestire le approvazioni

È possibile gestire le [approvazioni](modern-approvals.md) in Microsoft Teams esattamente come in Microsoft Flow. Seguire questa procedura per gestire le approvazioni:

1. Eseguire l'accesso a Microsoft Teams.
1. Selezionare la scheda **Approvazioni**.

    ![Scheda Approvazioni](media/flows-teams/approvals-tab.png)

    Si noteranno le sottoschede seguenti:

    Scheda|Scopo
    ----|-----|
    Ricevute|Elenca le richieste di approvazione che sono state ricevute e che sono in attesa di un'azione da parte dell'utente.
    Inviate|Elenca le richieste di approvazione che sono state inviate e che sono in attesa di un'azione da parte di altri utenti.
    Cronologia|Elenca le richieste di approvazione ricevute e inviate.
    Crea flusso di approvazione|Creare flussi di approvazione.

1. Fare clic sulle schede **Ricevute**, **Inviate** o **Cronologia** per altre informazioni.

    ![Scheda Approvazioni](media/flows-teams/approvals-tab-2.png)

1. Fare clic su **Crea flusso di approvazione** per creare un flusso di approvazione.

    ![Scheda Approvazioni](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Usare il bot con i flussi

### <a name="list-and-launch-flows-with-the-bot"></a>Elencare e avviare i flussi con il bot

> [!TIP]
> Il bot elenca ed esegue i flussi attivati da una pianificazione o attivati manualmente senza input dell'utente.

1. Eseguire l'accesso a Microsoft Teams.
1. Selezionare il collegamento **Ulteriori app aggiunte** (...) nella barra di spostamento e quindi selezionare l'app **Flow**.

    ![Icona App aggiunte](media/flows-teams/added-apps-icon.png)
    
1. Selezionare la scheda **Conversazione**.

    ![Scheda Conversazione](media/flows-teams/conversations-tab.png)

Nella scheda **Conversazione** è possibile inviare comandi al bot, che risponde eseguendo le azioni che l'utente specifica di eseguire. Ad esempio, per elencare i flussi ed eseguire il flusso con indice 1, eseguire i comandi seguenti:

- ```List flows``` - Il bot visualizza un elenco dei flussi, preceduti da un numero di indice.
- ```Run flow 1``` - Esegue il flusso numero 1. In questo caso *1* è il numero di indice del flusso che si vuole eseguire.

   ![Comandi del bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Ottenere la descrizione per i flussi

Per ottenere la descrizione per il flusso con indice 1 dall'elenco dei flussi, eseguire ```describe flow 1```. La risposta del bot sarà simile a questa immagine:

   ![Descrivere i flussi](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Ottenere l'elenco dei comandi per il bot

Per ottenere l'elenco dei comandi gestiti dal bot, eseguire questo comando: ```learn more``` 

La risposta del bot sarà simile a questa immagine:

![Descrivere i flussi](media/flows-teams/bot-learn-more.png) 
