---
title: Richieste di individuazione del soggetto dei dati GDPR in Microsoft Flow | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di individuazione del soggetto dei dati GPDR.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 9f950da1b62eac66b35a667f307917f704eb9133
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Risposta alle richieste di individuazione del soggetto dei dati GDPR per Microsoft Flow

Il primo passaggio per rispondere a una richiesta di soggetto dei dati (DSR, Data Subject Request) consiste nell'individuare i dati personali oggetto della richiesta. Il primo passaggio consente di determinare se una richiesta DSR soddisfa i requisiti dell'organizzazione per soddisfare o rifiutare una richiesta DSR. Ad esempio, dopo l'individuazione e la verifica dei dati personali in questione, si potrebbe determinare che la richiesta non soddisfa i requisiti dell'organizzazione perché soddisfare la richiesta potrebbe influire negativamente sui diritti e la libertà di altri individui.

Di seguito è riportato un riepilogo dei tipi di risorse di Microsoft Flow che contengono dati personali per un utente specifico.

|**Risorse contenenti dati personali**|**Scopo**|
|-----|-----|
|Log generati dal sistema|Dati di telemetria che acquisiscono eventi di sistema e cronologia.|
|Cronologia di esecuzione|Cronologia di ogni esecuzione del flusso per gli ultimi 28 giorni. Questi dati includono l'ora di inizio, l'ora di fine, lo stato e tutte le informazioni di input/output per il flusso. [Altre informazioni](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Feed attività| Fornisce un riepilogo delle attività del flusso, inclusi lo stato dell'esecuzione, gli errori e le notifiche.|
|Processi utente|Non visibili per l'utente, processi di sistema eseguiti per conto di un utente per consentire l'esecuzione dei flussi.|
|Flussi|Logica del flusso di lavoro esistente per un flusso. [Altre informazioni](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Autorizzazioni per i flussi|Flussi possono essere condivisi e riassegnati ad altri utenti. Esistono elenchi di autorizzazioni per tutti i flussi. [Altre informazioni](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Dettagli utente|Dettagli, non visibili per gli utenti, che supportano l'esecuzione del flusso.|
|Connessioni|Usate dai connettori, consentono la connettività alle API, ai sistemi, ai database e così via. [Altre informazioni](https://docs.microsoft.com/flow/add-manage-connections)|
|Autorizzazioni per le connessioni|Autorizzazioni per una connessione specifica. [Altre informazioni](https://docs.microsoft.com/flow/add-manage-connections)|
|Connettori personalizzati|Connettori personalizzati creati e pubblicati da un utente, che consentono la connettività a sistemi personalizzati o di terze parti. [Altre informazioni](https://docs.microsoft.com/connectors/custom-connectors/)|
|Autorizzazioni per i connettori personalizzati|Elenchi di autorizzazioni per i connettori personalizzati. [Altre informazioni](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|I gateway sono servizi dati in locale che possono essere installati da un utente per trasferire i dati rapidamente e in modo sicuro tra Microsoft Flow e un'origine dati che non è nel cloud. [Altre informazioni](https://docs.microsoft.com/flow/gateway-manage)|
|Autorizzazioni per i gateway|I gateway possono essere condivisi con gli utenti all'interno di un'organizzazione. [Altre informazioni](https://go.microsoft.com/fwlink/?linkid=872249)|
