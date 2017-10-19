---
title: Informazioni su come gestire i gateway dati locali | Microsoft Docs
description: Visualizzare e installare un gateway dati locale in Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
ms.openlocfilehash: 41f5d40ca2ad5fcce3a7967beef7104dd532b1d8
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
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
> I gateway di dati di Microsoft SharePoint supportano il traffico HTTP, ma non il traffico HTTPS.
> 
> 

## <a name="prerequisites"></a>Prerequisiti
* Il nome utente e la password usati per [iscriversi](sign-up-sign-in.md) a Microsoft Flow.
* Autorizzazioni amministrative per un gateway.
  
  Per ogni gateway installato sono fornite queste autorizzazioni per impostazione predefinita e un amministratore di un altro gateway può concederle per tale gateway.
* Una licenza che supporti i gateway. Per ulteriori informazioni, vedere la sezione "Connectivity" (Connettività) della [pagina dei prezzi](https://flow.microsoft.com/pricing/).
* È possibile creare un gateway e una connessione locale solo nell'[ambiente predefinito](environments-overview-maker.md).

## <a name="view-your-gateways"></a>Visualizzare i gateway
Nell'angolo in alto a destra del [sito Web di Microsoft Flow](https://flow.microsoft.com) scegliere o toccare l'icona dell'ingranaggio, quindi scegliere o toccare **Gateway**.

![Gateway in gestione][1]

**Nota**: se è stato creato o si è ricevuto l'accesso a un gateway in PowerApps, tale gateway viene visualizzato nell'elenco **Gateway personali** in Microsoft Flow.

## <a name="install-a-gateway"></a>Installare un gateway
1. Scaricare l'[installazione guidata del gateway](http://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).
   
    È anche possibile scaricare questa procedura guidata selezionando o toccando l'icona dell'ingranaggio nell'angolo in alto a destra del [sito Web di Microsoft Flow](https://flow.microsoft.com), facendo clic su o toccando **Gateway**, quindi selezionando **Crea gateway**.
   
    ![Installazione del gateway][2]
2. Eseguire questa procedura guidata, specificando le stesse credenziali usate per accedere a Microsoft Flow.
   
    Dopo aver registrato e configurato correttamente il gateway, questo viene visualizzato nell'elenco **Gateway personali** in Microsoft Flow.

Per altre informazioni, vedere [Informazioni sui gateway](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
[2]: ./media/manage-gateway/list-gateways.png
