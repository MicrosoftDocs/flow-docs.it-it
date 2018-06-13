---
title: Richieste di individuazione del soggetto dei dati GDPR in Microsoft Flow per account del servizio gestito Microsoft (MSA) | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di individuazione del soggetto dei dati GPDR per gli account Microsoft.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
ms.author: keweare
ms.openlocfilehash: d31e91420f2235b201d3ae974b1950ae5fbc35c9
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563114"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Rispondere alle richieste di individuazione del soggetto dei dati GPDR 

Il primo passaggio per rispondere a una richiesta di soggetto dei dati (DSR, Data Subject Request) consiste nel trovare i dati personali oggetto della richiesta.
Di seguito è riportato un riepilogo delle risorse di Microsoft Flow che contengono dati personali per un utente che esegue l'autenticazione con l'account del servizio gestito Microsoft (MSA).

|Risorsa|Scopo|
|-----|-----|
|Cronologia di esecuzione|Offre la cronologia di ogni esecuzione del flusso per gli ultimi 28 giorni. Questi dati includono l'ora di inizio, l'ora di fine, lo stato e tutte le informazioni di input/output per ogni esecuzione del flusso. Altre informazioni sulla [cronologia di esecuzione del flusso](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Feed attività| Offre un riepilogo delle attività di ogni flusso, inclusi lo stato dell'esecuzione, gli errori e le notifiche.|
|Flussi|Logica del flusso di lavoro per un [flusso](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Connessioni|Usate dai connettori, consentono la connettività alle API, ai sistemi, ai database e così via. Altre informazioni sulle [connessioni](add-manage-connections.md).|

