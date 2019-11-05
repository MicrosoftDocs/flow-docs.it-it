---
title: Gateway dati locale | Microsoft Docs
description: Questo articolo è una panoramica del gateway dati locale per Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8349361b7ee543c19635dc5899726d69adaa917a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544653"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Che cos'è un gateway dati locale?
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Il gateway dati locale funge da Bridge per offrire un trasferimento dei dati rapido e sicuro tra i dati locali (dati non presenti nel cloud) e diversi servizi cloud Microsoft. Questi servizi cloud includono Power BI, PowerApps, Microsoft Flow, Azure Analysis Services e app per la logica di Azure. Usando un gateway, le organizzazioni possono proteggere i database e altre origini dati nelle rispettive reti locali, ma usano in modo sicuro i dati locali nei servizi cloud.

## <a name="how-the-gateway-works"></a>Funzionamento del gateway

![Panoramica sul gateway](media/gateway-reference/on-premises-data-gateway.png)

Per altre informazioni sul funzionamento del gateway, vedere [architettura del gateway dati locale](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Tipi di gateway

Esistono due tipi di gateway diversi, ognuno per uno scenario diverso:

- **Il gateway dati locale** consente a più utenti di connettersi a più origini dati locali. È possibile usare un gateway dati locale con tutti i servizi supportati, con un'unica installazione del gateway. Questo gateway è particolarmente adatto per scenari complessi con più persone che accedono a più origini dati.

- **Il gateway dati locale (modalità personale)** consente a un utente di connettersi alle origini e non può essere condiviso con altri. Un gateway dati locale (modalità personale) può essere usato solo con Power BI. Questo gateway è particolarmente adatto agli scenari in cui si è l'unico utente che crea report e non è necessario condividere le origini dati con altri utenti.

## <a name="use-a-gateway"></a>Usare un gateway

Ci sono quattro passaggi principali per l'uso di un gateway.

1. [Scaricare e installare il gateway](/data-integration/gateway/service-gateway-install) in un computer locale.
2. [Configurare](/data-integration/gateway/service-gateway-app) il gateway in base al firewall e ad altri requisiti di rete.
3. [Aggiungere gli amministratori del gateway](/data-integration/gateway/service-gateway-manage) che possono anche gestire e amministrare altri requisiti di rete.
4. [Risolvere i problemi](/data-integration/gateway/service-gateway-tshoot) del gateway in caso di errori.

## <a name="next-steps"></a>Passaggi successivi

- [Installare il gateway dati locale](/data-integration/gateway/service-gateway-install)
