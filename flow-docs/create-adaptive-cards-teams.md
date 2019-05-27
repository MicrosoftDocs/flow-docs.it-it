---
title: Informazioni su come creare flussi che registra le schede adattive per Microsoft Teams | Microsoft Docs
description: Informazioni su come creare flussi che pubblica il contenuto con formattazione complessa con le schede adattive a Microsoft Teams.
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
ms.openlocfilehash: d6bb4bb55fe876db1d8b64c157d3b4967e5d067f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061573"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Usare le schede adattive in Microsoft Teams

È possibile creare un flusso che invii [le schede adattive](https://adaptivecards.io) a un canale Microsoft Teams. Con le schede adattive, è possibile usare la formattazione RTF per rendere i post più chiari, interattivi e accattivanti. Le schede adattive possono contenere i componenti, ad esempio immagini, grafici, testo in formato RTF e altro ancora.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Creare un flusso che invii le schede adattive a un team

Seguire questi passaggi per creare un flusso che inserisce una scheda adattiva al canale generale del team di strategia e pianificazione. Il flusso viene creato usa il **registrare il proprio scheda adattiva come al bot di flusso di un canale (anteprima)** azione per inviare il contenuto della scheda adattiva al canale del team ogni settimana.

1. Eseguire l'accesso a Microsoft Teams.
1. Selezionare il **Teams** icona nel riquadro di spostamento a sinistra e quindi selezionare la **strategia e pianificazione** team.

    ![Selezionare i team](media/create-adaptive-cards-teams/select-teams-team.png)

1. Selezionare il **Flow** scheda nella parte superiore della schermata.
1. Selezionare il **+** icona (Crea da zero).
1. Cercare **ricorrenza**, quindi selezionare la **ricorrenza** trigger.

    ![Scheda di ricorrenza](media/create-adaptive-cards-teams/select-recurrence.png)

1. Impostare la pianificazione come indicato di seguito per ripetere ogni settimana, un'ora e fuso orario di propria scelta:
    
    ![Scheda di ricorrenza](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Selezionare **Nuovo passaggio**.
1. Cercare **adattivo**, selezionare **Microsoft Teams**e quindi selezionare il **registrare il proprio scheda adattiva come al bot di flusso di un canale (anteprima)** azione.

   ![Scheda adattiva](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Fornire una **Team**, **canale**, e **messaggio** nel **registrare il proprio scheda adattiva come al bot di flusso di un canale (anteprima)** carta per indicare il team e il canale a cui la scheda adattiva **messaggio** verrà pubblicato.

   ![Scheda adattiva](media/create-adaptive-cards-teams/adaptive-card-message.png)

   È possibile usare il contenuto JSON di esempio per la **messaggio**:

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

Si noti che, trascorso il tempo di ricorrenza, il flusso invia il contenuto della scheda adattiva al canale di team definito.

![Eseguire il flusso](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Altre informazioni

- Introduzione [esempi di scheda adattiva](https://adaptivecards.io/samples/).
- Creare [contenuto scheda adattiva](https://adaptivecards.io) il modo più semplice.



