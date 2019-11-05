---
title: Informazioni su come gestire i gateway dati locali | Microsoft Docs
description: Visualizzare e installare un gateway dati locale in Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3991e739178f86bbea3ae1b68b9d3337c42b4727
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547658"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Gestire un gateway dati locale in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Installare e gestire un gateway dati locale per integrare in modo sicuro un'ampia gamma di app basate su cloud con i dati e le app locali tramite Microsoft Flow.

Con un gateway è possibile connettersi ai dati locali tramite le connessioni seguenti:

* Apache Impala
* Connettori personalizzati creati
* DB2
* File System
* Http con Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (anteprima)

> [!IMPORTANT]
> I gateway di dati di Microsoft SharePoint supportano ora sia il traffico HTTP che HTTPS.

## <a name="prerequisites"></a>Prerequisiti

* Nome utente e password usati per [iscriversi](sign-up-sign-in.md) a Microsoft Flow.
* Autorizzazioni amministrative per un gateway.

  Queste autorizzazioni sono disponibili per impostazione predefinita per ogni gateway installato. Inoltre, un amministratore di un altro gateway può concedere queste autorizzazioni per il gateway.
* Una licenza che supporta i gateway. Per ulteriori informazioni, vedere la sezione "connettività" della [pagina dei prezzi](https://flow.microsoft.com/pricing/).

> [!NOTE]
> È possibile creare un gateway e una connessione locale solo nell' [ambiente predefinito](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Installare un gateway

Per installare un gateway, seguire la procedura descritta in [installare un gateway dati locale](/data-integration/gateway/service-gateway-install). Installare il gateway in modalità standard perché il _gateway dati locale (modalità personale)_ è disponibile solo per Power bi.

## <a name="view-your-gateways"></a>Visualizzare i gateway

Nell'angolo in alto a destra del [sito web Microsoft Flow](https://flow.microsoft.com)selezionare l'icona a forma di ingranaggio e quindi selezionare **gateway**.

![Gateway gestito][1]

> [!NOTE]
> Se è stato creato o è stato concesso l'accesso a un gateway in PowerApps, tale gateway viene visualizzato nell'elenco **gateway personali** in Microsoft Flow.

## <a name="cluster-your-gateways"></a>Raggruppare i gateway

È possibile creare [cluster a disponibilità elevata di installazioni di gateway dati locali](/data-integration/gateway/service-gateway-high-availability-clusters) per evitare singoli punti di errore durante l'accesso alle risorse dati locali.

Per impostazione predefinita, Microsoft Flow usa il gateway primario nel cluster. Se il gateway primario non è disponibile, il servizio passa al gateway successivo nel cluster e così via.

Dopo aver configurato un cluster di gateway, è possibile consentire la distribuzione del traffico tra tutti i gateway del cluster.

Per distribuire il traffico tra i gateway, seguire questa procedura:

1. Selezionare **dati** sulla barra di spostamento sul lato sinistro.
1. Selezionare **gateway**.
1. Selezionare uno dei gateway.
1. Selezionare **Distribuisci le richieste tra tutti i gateway attivi in questo cluster**.
1. Selezionare **applica** per salvare le modifiche.

Per altre informazioni, vedere informazioni sui [gateway](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
