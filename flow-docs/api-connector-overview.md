---
title: Panoramica sul connettore API | Microsoft Docs
description: Gli ISV e i proprietari dei servizi SaaS possono creare connettori e richiederne la certificazione a Microsoft.
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 62f8f8d0af72292a61324d75bd46f53d559b46a3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="api-connector-overview-microsoft-flow"></a>Panoramica sul connettore delle API (Microsoft Flow)
Un **connettore API** è un wrapper basato su OpenAPI (Swagger) intorno a un'API REST che consente al servizio sottostante di comunicare con [Microsoft Flow](https://flow.microsoft.com), [PowerApps](https://powerapps.microsoft.com) e le [App per la logica](https://docs.microsoft.com/azure/logic-apps/). Un connettore permette agli utenti di connettere i propri account e sfruttare un set di **trigger** e **azioni** predefiniti per compilare le app e i flussi di lavoro.

I **fornitori di software indipendenti (ISV)** o i **proprietari del servizio SaaS** possono creare i connettori per abilitare una vasta gamma di scenari aziendali e di produttività per gli utenti. Un connettore consente di superare un set definito di integrazioni e di aumentare la copertura, l'esposizione al rilevamento e l'utilizzo del servizio.

## <a name="requirements"></a>Requisiti
Per compilare e inviare un connettore, il servizio deve soddisfare i requisiti seguenti:

* Scenario utente aziendale che si adatta perfettamente a Microsoft Flow, PowerApps e App per la logica
* Servizio pubblicamente disponibile con API REST stabili

## <a name="build-your-connector"></a>Creare il connettore
Il primo passaggio per compilare un connettore delle API consiste nel creare un connettore personalizzato completamente funzionale. Un connettore personalizzato funziona esattamente come un connettore delle API, ma la disponibilità è limitata al relativo autore e a utenti specifici nel tenant dell'autore.

Il processo di creazione di un connettore prevede più passaggi:

![Passaggi di creazione del connettore API](./media/api-connectors-overview/authoring-steps.png)

[Altre informazioni](api-connector-dev.md) su come sviluppare un connettore delle API.

## <a name="submit-for-certification"></a>Inviare per la certificazione
Dopo aver creato un connettore, inviarlo per la certificazione. Come parte del processo di certificazione di terze parti, Microsoft esamina il connettore prima della pubblicazione.

Questo processo convalida la funzionalità del connettore in Microsoft Flow e PowerApps e verifica la conformità tecnica e di contenuto.

[Altre informazioni](api-connector-submission.md) sul processo di invio del connettore per la certificazione e pubblicazione.

## <a name="get-support"></a>Ottenere supporto
Per il supporto di onboarding e sviluppo, scrivere a [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com). Questo account è monitorato e gestito attivamente. Le query e gli eventi imprevisti riscontrati e comunicati dagli sviluppatori verranno inoltrati rapidamente al team appropriato.

