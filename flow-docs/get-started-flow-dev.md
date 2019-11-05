---
title: Creare connettori personalizzati e incorporare flussi | Microsoft Docs
description: Creare un connettore personalizzato, condividerlo, incorporare un flusso ed eseguire molte altre operazioni.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 80b1d17944d780a1800c91458ee674f5f2afe188
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548254"
---
# <a name="start-to-build-with-microsoft-flow"></a>Inizia a compilare con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Di seguito sono illustrati alcuni dei modi in cui è possibile estendere l'applicazione con Microsoft Flow:

* Creare e connettersi a un connettore personalizzato.
* Condividere il connettore personalizzato con tutti gli utenti Microsoft Flow.
* Incorporare l'esperienza di flusso all'interno di un'app.
* Evidenziare tutti i connettori personalizzati in modo che gli utenti possano interagire con Microsoft Flow nel modo migliore.

## <a name="prerequisites"></a>Prerequisiti

* Un account [Microsoft Flow](https://flow.microsoft.com) .

## <a name="create-a-custom-connector"></a>Creare un connettore personalizzato

Se si dispone di un servizio Web a cui si desidera connettersi da Microsoft Flow, sarà prima di tutto necessario creare un connettore personalizzato. Quando si registra un connettore personalizzato, si insegna Microsoft Flow sulle caratteristiche del servizio Web, inclusa l'autenticazione che richiede, i trigger e le azioni che supporta e i parametri e gli output per ognuna di tali azioni.

Seguire questa esercitazione per informazioni su come [registrare e usare connettori personalizzati](https://powerapps.microsoft.com/tutorials/register-custom-api/). Dopo aver registrato il connettore personalizzato, è possibile condividerlo all'interno dell'organizzazione per il test.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Condividere un connettore personalizzato con tutti gli utenti Microsoft Flow

Dopo aver testato completamente il connettore personalizzato, avviare il [processo di revisione](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) affinché venga approvato da Microsoft per la condivisione con tutti gli altri utenti Microsoft Flow.

Ecco gli elementi necessari per il processo di Revisione:

* Un file OpenAPI che rappresenta l'API ed eventuali informazioni di autenticazione.
* Icona per il connettore.
* Descrizione del connettore.
* Circa 10 idee per il modo in cui il connettore può trarre vantaggio da altri utenti tramite modelli.

Dopo aver inviato queste informazioni, Microsoft inizia a valutare le funzionalità dell'API in Microsoft Flow e Microsoft PowerApps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Incorporare l'esperienza di flusso nel sito Web o nell'app

È possibile [incorporare](developer/embed-flow-dev.md) Microsoft Flow nell'app per abilitare l'integrazione profonda nel contesto tra l'app e tutti gli altri servizi supportati da Microsoft Flow. Ad esempio, è possibile:

* Esplorare tutti i modelli correlati al servizio e consentire agli utenti di selezionare un modello.
* Gestire i flussi che gli utenti hanno correlato all'app.

## <a name="next-steps"></a>Passaggi successivi

Informazioni su come [incorporare](developer/embed-flow-dev.md) Microsoft Flow nell'app.
