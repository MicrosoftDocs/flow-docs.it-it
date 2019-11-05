---
title: Cenni preliminari sulle aree geografiche per Microsoft Flow | Microsoft Docs
description: Panoramica con domande e risposte sulle aree in Microsoft Flow
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 33c5a1c331d9874f6b794e8fd2ea92b541024ec6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548474"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Domande frequenti sulle aree in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Questo documento contiene un elenco di domande frequenti su Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Ricerca per categorie scoprire dove viene distribuito il flusso?
Il flusso viene distribuito nell' [area](https://azure.microsoft.com/regions/) che ospita l' [ambiente](environments-overview-admin.md). Ad esempio, se l'ambiente viene creato nell'area Europa, il flusso viene distribuito nei data center dell'Europa.

Gli amministratori possono identificare l'area se accedono al centro di [amministrazione](https://admin.flow.microsoft.com)Microsoft Flow. La scheda **ambienti** elenca tutti gli ambienti esistenti e le rispettive aree.

![Visualizza ambienti](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Quali aree sono disponibili?
* Stati Uniti
* Europa
* Asia
* Australia
* India
* Giappone
* Canada
* America del sud
* Regno Unito
* Governo degli Stati Uniti (GCC)
* Francia

## <a name="what-features-are-specific-to-a-given-region"></a>Quali funzionalità sono specifiche per una determinata area?
Gli ambienti possono essere creati in aree diverse e sono associati alla posizione geografica. Quando si crea un flusso in un ambiente, tale flusso viene distribuito nei data center di quella posizione geografica. Questo vale per tutti gli elementi creati in tale ambiente, inclusi il modello di dati comune, i flussi, le connessioni, i gateway, le app e i connettori personalizzati.

Per prestazioni ottimali, creare l'ambiente nell'area più vicina agli utenti. Ad esempio, se gli utenti si trovano in Europa, creare gli ambienti nell'area Europa. Se gli utenti si trovano nella Stati Uniti, creare gli ambienti nell'area Stati Uniti.

## <a name="gateways"></a>Gateway
I gateway sono:

* Non disponibile nell'area India.
* Supportato solo nell'ambiente predefinito, non in ambienti personalizzati.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Microsoft Flow è disponibile nei cloud nazionali?
Sì. [Altre informazioni](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Quali indirizzi IP in uscita vengono usati in ogni area?
Vedere [limiti e configurazione](limits-and-config.md).

