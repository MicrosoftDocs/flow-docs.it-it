---
title: Informazioni su come gestire i gateway dati locali | Microsoft Docs
description: Visualizzare e installare un gateway dati locale in Microsoft Flow
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
ms.date: 02/05/2018
ms.author: deonhe
ms.openlocfilehash: 642cf26110a09404c8bd453f894540963904ebda
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "29057406"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Gestire un gateway dati locale in Microsoft Flow

Installare e gestire un gateway dati locale per integrare in modo sicuro un'ampia gamma di app basate su cloud con i dati e le app locali attraverso Microsoft Flow.

Con un gateway è possibile connettersi ai dati locali attraverso le connessioni seguenti:

* SharePoint
* SQL Server
* Oracle
* Informix
* Filesystem
* DB2

> [!IMPORTANT]
> I gateway di dati di Microsoft SharePoint ora supportano il traffico sia HTTP che HTTPS.


## <a name="prerequisites"></a>Prerequisiti

* Il nome utente e la password usati per [iscriversi](sign-up-sign-in.md) a Microsoft Flow.
* Autorizzazioni amministrative per un gateway.

  Queste autorizzazioni sono disponibili per impostazione predefinita per ogni gateway installato. Inoltre, un amministratore di un altro gateway può concedere queste autorizzazioni per tale gateway.
* Una licenza che supporti i gateway. Per ulteriori informazioni, vedere la sezione "Connectivity" (Connettività) della [pagina dei prezzi](https://flow.microsoft.com/pricing/).

> [!NOTE]
> È possibile creare un gateway e una connessione locale solo nell'[ambiente predefinito](environments-overview-maker.md).



## <a name="view-your-gateways"></a>Visualizzare i gateway

Nell'angolo in alto a destra del [sito Web di Microsoft Flow](https://flow.microsoft.com) selezionare l'icona a forma di ingranaggio e quindi selezionare **Gateway**.

![Gateway in gestione][1]

> [!NOTE]
> Se si è l'autore di un gateway in PowerApps o si è autorizzati ad accedervi, tale gateway viene visualizzato nell'elenco **Gateway personali** in Microsoft Flow.



## <a name="install-a-gateway"></a>Installare un gateway

1. Scaricare l'[installazione guidata del gateway](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).

1. Eseguire questa procedura guidata e specificare le stesse credenziali usate per accedere a Microsoft Flow.

    Dopo aver registrato e configurato correttamente il gateway, questo viene visualizzato nell'elenco **Gateway** in Microsoft Flow.

Per altre informazioni, vedere [Informazioni sui gateway](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
