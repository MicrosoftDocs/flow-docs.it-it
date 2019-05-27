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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b8b14f720736a60b04cbd9ae23dec5c0524ff03c
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65054065"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Gestire un gateway dati locale in Microsoft Flow

Installare e gestire un gateway dati locale per integrare in modo sicuro un'ampia gamma di app basate su cloud con i dati e le app locali attraverso Microsoft Flow.

Con un gateway è possibile connettersi ai dati locali attraverso le connessioni seguenti:

* Apache Impala
* Connettori personalizzati creati dall'utente
* DB2
* File system
* HTTP con Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (anteprima)

> [!IMPORTANT]
> I gateway di dati di Microsoft SharePoint ora supportano il traffico sia HTTP che HTTPS.

## <a name="prerequisites"></a>Prerequisiti

* Il nome utente e la password usati per [iscriversi](sign-up-sign-in.md) a Microsoft Flow.
* Autorizzazioni amministrative per un gateway.

  Queste autorizzazioni sono disponibili per impostazione predefinita per ogni gateway installato. Inoltre, un amministratore di un altro gateway può concedere queste autorizzazioni per tale gateway.
* Una licenza che supporti i gateway. Per ulteriori informazioni, vedere la sezione "Connectivity" (Connettività) della [pagina dei prezzi](https://flow.microsoft.com/pricing/).

> [!NOTE]
> È possibile creare un gateway e una connessione locale solo nell'[ambiente predefinito](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Installare un gateway

1. Scaricare l'[installazione guidata del gateway](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).

1. Eseguire questa procedura guidata e specificare le stesse credenziali usate per accedere a Microsoft Flow.

    Dopo aver registrato e configurato correttamente il gateway, questo viene visualizzato nell'elenco **Gateway** in Microsoft Flow.

## <a name="view-your-gateways"></a>Visualizzare i gateway

Nell'angolo in alto a destra del [sito Web di Microsoft Flow](https://flow.microsoft.com) selezionare l'icona a forma di ingranaggio e quindi selezionare **Gateway**.

![Gateway in gestione][1]

> [!NOTE]
> Se si è l'autore di un gateway in PowerApps o si è autorizzati ad accedervi, tale gateway viene visualizzato nell'elenco **Gateway personali** in Microsoft Flow.


## <a name="cluster-your-gateways"></a>I gateway del cluster

È possibile creare *cluster a disponibilità elevata di installazioni del gateway dati locale* per evitare singoli punti di errore nell'accesso alle risorse dati locali. 

Per impostazione predefinita, Microsoft Flow Usa il gateway primario nel cluster. Se il gateway primario non è disponibile, il servizio passa al gateway successivo del cluster, e così via.

Dopo aver configurato un cluster di gateway, è possibile consentire il traffico deve essere distribuito tra tutti i gateway nel cluster. 

Seguire questi passaggi per distribuire il traffico tra i gateway:

1. Selezionare **dati** sulla barra di spostamento a sinistra.
1. Selezionare **gateway**.
1. Selezionare uno dei gateway.
1. Selezionare **distribuire le richieste tra tutti i gateway attivi in questo cluster**.
1. Selezionare **applica** per salvare le modifiche.


Per altre informazioni, vedere [Informazioni sui gateway](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
