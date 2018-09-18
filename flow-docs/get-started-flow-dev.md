---
title: Creare connettori personalizzati e incorporare flussi| Microsoft Docs
description: Creare un connettore personalizzato, condividerlo, incorporare un flusso e molto altro.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: barathb
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 21f35216231193f40c1a723dda62bb3a2ad1be59
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689641"
---
# <a name="start-to-build-with-microsoft-flow"></a>Iniziare a creare con Microsoft Flow

Di seguito sono descritti alcuni dei modi in cui è possibile estendere la propria applicazione con Microsoft Flow:

* Creare e connettersi a un connettore personalizzato.
* Condividere il connettore personalizzato con tutti gli utenti di Microsoft Flow.
* Incorporare l'esperienza di flusso all'interno di un'app.
* Mettere in evidenza tutti i connettori personalizzati per consentire agli utenti di interagire con Microsoft Flow nel modo migliore.

## <a name="prerequisites"></a>Prerequisiti

* Un account [Microsoft Flow](https://flow.microsoft.com).

## <a name="create-a-custom-connector"></a>Creare un connettore personalizzato

Se è disponibile un servizio Web a cui si vuole connettersi da Microsoft Flow, è necessario innanzitutto creare un connettore personalizzato. Con la registrazione di un connettore personalizzato, si indicano a Microsoft Flow le caratteristiche del servizio Web, inclusa l'autenticazione che richiede, i trigger e azioni che supporta e i parametri e gli output per ognuna di tali azioni.

Seguire questa esercitazione per apprendere come [registrare e usare i connettori personalizzati](https://powerapps.microsoft.com/tutorials/register-custom-api/). Dopo aver registrato il connettore personalizzato, è possibile condividerlo all'interno dell'organizzazione per il test.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Condividere un connettore personalizzato con tutti gli utenti di Microsoft Flow

Dopo aver eseguito il test completo del connettore personalizzato, iniziare il [processo di revisione](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) per ottenere l'approvazione di Microsoft per la condivisione con tutti gli altri utenti di Microsoft Flow.

Per il processo di revisione sono necessari gli elementi seguenti:

* Un file OpenAPI che rappresenta l'API ed eventuali informazioni di autenticazione.
* Un'icona per il connettore.
* Una descrizione del connettore.
* Circa 10 suggerimenti su come il connettore possa avvantaggiare altri utenti attraverso i modelli.

Dopo aver inviato queste informazioni, Microsoft inizia a valutare la funzionalità dell'API in Microsoft Flow e Microsoft PowerApps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Incorporare l'esperienza di flusso nel sito Web o nell'app

È possibile [incorporare](developer/embed-flow-dev.md) Microsoft Flow all'interno dell'app per abilitare un'integrazione profonda nel contesto tra l'app e tutti gli altri servizi supportati da Microsoft Flow. Ad esempio, è possibile:

* Esplorare tutti i modelli correlati al servizio e consentire agli utenti di selezionare un modello.
* Gestire i flussi che gli utenti hanno correlato all'app.

## <a name="next-steps"></a>Passaggi successivi

Informazioni su come [incorporare](developer/embed-flow-dev.md) Microsoft Flow nell'app.
