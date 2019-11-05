---
title: Scopri come creare flussi che inviano schede adattive a Microsoft Teams | Microsoft Docs
description: Scopri come creare flussi che postano contenuti formattati in modo completo con schede adattive a Microsoft teams.
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
ms.openlocfilehash: 0aa5b4727bea569732fe5b76f717a87d8d7ddb02
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546509"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Usare schede adattive in Microsoft Teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

È possibile creare un flusso che invii [schede adattive](https://adaptivecards.io) a un canale di Microsoft teams. Con le schede adattive è possibile utilizzare la formattazione avanzata per rendere i post più chiari, interattivi e accattivanti. Le schede adattive possono contenere componenti quali immagini, grafici, testo formattato in modo RTF e altro ancora.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Creare un flusso che invii schede adattive a un team

Seguire questa procedura per creare un flusso che invii una scheda adattiva al canale generale nel team di strategia e pianificazione. Il flusso creato usa l'azione **Invia la tua scheda adattiva come bot di flusso a un canale (anteprima)** per pubblicare il contenuto della scheda adattiva sul canale settimanale del team.

1. Accedere a Microsoft teams.
1. Selezionare l'icona **Teams (team** ) nella barra di spostamento a sinistra e quindi selezionare la **strategia e** il team di pianificazione.

    ![Selezione team](media/create-adaptive-cards-teams/select-teams-team.png)

1. Selezionare la scheda **flusso** nella parte superiore della schermata.
1. Selezionare l'icona **+** (Crea da zero).
1. Cercare **ricorrenza**, quindi selezionare il trigger **ricorrenza** .

    ![Scheda ricorrenza](media/create-adaptive-cards-teams/select-recurrence.png)

1. Impostare la pianificazione come indicato di seguito per ripetere ogni settimana, per un fuso orario e un fuso orario di propria scelta:
    
    ![Scheda ricorrenza](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Selezionare **nuovo passaggio**.
1. Cercare **adattivo**, selezionare **Microsoft teams**e quindi selezionare l'azione **Invia la tua scheda adattiva come bot a un canale (anteprima)** .

   ![Scheda adattiva](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Fornire un **Team**, un **canale**e un **messaggio** sulla scheda **Invia il proprio dispositivo adattivo come bot a un canale (anteprima)** per indicare il team e il canale a cui verrà inviato il **messaggio** della scheda adattiva.

   ![Scheda adattiva](media/create-adaptive-cards-teams/adaptive-card-message.png)

   È possibile usare questo contenuto JSON di esempio per il **messaggio**:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Assegnare un nome al flusso e salvarlo.


## <a name="run-the-flow"></a>Eseguire il flusso

Si noti che, dopo la scadenza del tempo di ricorrenza, il flusso invia il contenuto della scheda adattivo al canale del team definito.

![Eseguire il flusso](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Ulteriori informazioni

- Introduzione agli [esempi di schede adattive](https://adaptivecards.io/samples/).
- Il modo più semplice per creare [contenuti di schede adattive](https://adaptivecards.io) .



