---
title: Panoramica sulle aree geografiche per Microsoft Flow | Microsoft Docs
description: Panoramica sulle aree geografiche in Microsoft Flow attraverso domande e risposte
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
ms.openlocfilehash: ec9b72e570c562c091aefd370f73d6862ff56f18
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "23442081"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Domande frequenti sulle aree in Microsoft Flow
Questo documento fornisce un elenco delle domande frequenti su Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Come sapere dove viene distribuito il flusso
Il flusso viene distribuito nell'[area](https://azure.microsoft.com/regions/) geografica che ospita l'[ambiente](environments-overview-admin.md). Ad esempio, se l'ambiente viene creato in Europa, il flusso viene distribuito nei data center di quell'area geografica.

Gli amministratori possono identificare l'area geografica se accedono all'[interfaccia di amministrazione](https://admin.flow.microsoft.com) di Microsoft Flow. La scheda **Ambienti** elenca tutti gli ambienti esistenti e le relative aree geografiche.

![visualizzare gli ambienti](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Quali sono le aree geografiche disponibili?
* Stati Uniti
* Europa
* Asia
* Australia
* India
* Giappone
* Canada

## <a name="what-features-are-specific-to-a-given-region"></a>Quali funzionalità sono specifiche per una determinata area geografica?
Gli ambienti possono essere creati in aree geografiche diverse a cui sono vincolati. Quando si crea un flusso in un ambiente, tale flusso viene distribuito nei data center di quella posizione geografica. Questo vale per qualsiasi elemento creato in quell'ambiente, inclusi i comuni modelli di dati, flussi, connessioni, gateway, app e connettori personalizzati.

Per ottenere prestazioni ottimali, creare l'ambiente nell'area geografica più vicina agli utenti. Ad esempio, se gli utenti si trovano in Europa, creare l'ambiente nell'area geografica Europa. Se gli utenti si trovano negli Stati Uniti, creare gli ambienti nell'area geografica degli Stati Uniti.

## <a name="gateways"></a>Gateway
I gateway sono:

* Non sono disponibili in India.
* Supportato soltanto nell'ambiente predefinito, non in ambienti personalizzati.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Microsoft Flow è disponibile nei cloud nazionali?
No, Microsoft Flow non è disponibile nei cloud nazionali. Il supporto per i cloud nazionali è pianificato per il 2018.

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Quali indirizzi IP in uscita vengono usati in ciascuna area?
Vedere [Limiti e configurazione](limits-and-config.md)

