---
title: Richieste di individuazione del soggetto dei dati Microsoft Flow GDPR per gli account Microsoft (MSA) | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di individuazione del soggetto dei dati alle GPDR per gli account Microsoft.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 06e88aa215089145f86f9027a6ad75b73c7cf627
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548109"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Rispondere alle richieste di individuazione del soggetto dei dati GDPR 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Il primo passaggio per rispondere a una richiesta del DSR è trovare i dati personali che sono oggetto della richiesta.
Ecco un riepilogo delle risorse Microsoft Flow che contengono dati personali per un utente che esegue l'autenticazione con il proprio account Microsoft (MSA).

|Risorse|Scopo|
|-----|-----|
|cronologia di esecuzione|Fornisce la cronologia dell'esecuzione di ogni flusso negli ultimi 28 giorni. Questi dati includono l'ora di inizio, l'ora di fine, lo stato e tutte le informazioni di input/output per ogni esecuzione del flusso. Altre informazioni sulla [cronologia di esecuzione del flusso](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Feed attività| Fornisce un riepilogo delle attività di ogni flusso, tra cui lo stato di esecuzione, gli errori e le notifiche.|
|Flussi|Logica del flusso di lavoro per un [flusso](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Connessioni|Usato dai connettori e consente la connettività a API, sistemi, database e altro ancora. Altre informazioni sulle [connessioni](add-manage-connections.md).|

