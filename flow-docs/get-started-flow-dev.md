---
title: Iniziare a creare | Microsoft Docs
description: Creare un connettore personalizzato, condividerlo, incorporare un flusso e molto altro.
services: 
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: barathb
ms.openlocfilehash: d22193ac40b6eb8f90abf2ae5ced91b39c2faad9
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="start-to-build-with-microsoft-flow"></a>Iniziare a creare con Microsoft Flow
Estendere l'applicazione con Microsoft Flow nei seguenti modi, tra gli altri:

* creare e connettersi a un connettore personalizzato
* condividere tale API con tutti gli utenti di Microsoft Flow
* incorporare l'esperienza di flusso dall'interno di un'app
* sfruttare tutte le API degli sviluppatori in modo che gli utenti possano interagire con Microsoft Flow nel miglior modo possibile

## <a name="prerequisites"></a>Prerequisiti
* Un account in [flow.microsoft.com](https://flow.microsoft.com)

## <a name="create-a-custom-connector"></a>Creare un connettore personalizzato
Quando si vuole automatizzare un servizio Web con Microsoft Flow, è prima di tutto necessario creare un connettore personalizzato. Con la registrazione di un connettore personalizzato, si indicano a Microsoft Flow le caratteristiche della propria API Web, inclusa l'autenticazione che richiede, i trigger e azioni che supporta e i parametri e gli output per ognuna di tali azioni.

Seguire [questa esercitazione](https://powerapps.microsoft.com/tutorials/register-custom-api/) per registrare un connettore personalizzato. Dopo la registrazione, è possibile condividerla all'interno dell'organizzazione in modo che altri utenti possano aiutare a testarla.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Condividere un connettore personalizzato con tutti gli utenti di Microsoft Flow
Dopo avere testato completamente il connettore personalizzato, avviare il processo di revisione come stabilito in [questo post di blog](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/):

* Un file OpenAPI che rappresenta l'API ed eventuali informazioni di autenticazione
* Un'icona per il connettore
* Una descrizione dell'API
* Circa 10 suggerimenti su come le API possono avvantaggiare altri utenti attraverso i modelli

Dopo aver inviato queste informazioni, Microsoft inizierà a valutare la funzione dell'API in Microsoft Flow e Microsoft PowerApps.

## <a name="embed-the-flow-experience-in-your-website-or-app"></a>Incorporare l'esperienza di flusso in un'app o nel sito Web
Infine, è possibile incorporare Microsoft Flow all'interno dell'app per abilitare integrazione profonda nel contesto tra l'app e tutti gli altri servizi supportati da Microsoft Flow. Ad esempio, è possibile:

* Esplorare tutti i modelli correlati al servizio e consentire agli utenti di selezionare un modello
* Gestire i flussi che gli utenti hanno correlato all'app

Seguire [questa esercitazione](embed-flow-dev.md) per altre informazioni su come incorporare Microsoft Flow all'interno di un'app.

