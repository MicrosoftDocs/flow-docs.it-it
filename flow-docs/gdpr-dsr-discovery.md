---
title: Individuazione richieste oggetto dati Microsoft Flow GDPR | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di individuazione del soggetto dei dati alle GPDR.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 197d9ebfc38fc4f5b52bf674aef61d419530f439
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548118"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Risposta alle richieste di individuazione del soggetto dei dati GDPR per Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Il primo passaggio per rispondere a un DSR è trovare i dati personali che sono oggetto della richiesta. Questo primo passaggio consente di determinare se un DSR soddisfa i requisiti dell'organizzazione per rispettare o rifiutare una richiesta del DSR. Dopo aver individuato e esaminato i dati personali in questione, ad esempio, è possibile determinare che la richiesta non soddisfa i requisiti dell'organizzazione perché questa operazione può influire negativamente sui diritti e sulle libertà di altri utenti.

Di seguito è riportato un riepilogo dei tipi di risorse di Microsoft Flow che contengono dati personali per un utente specifico.

|**Risorse contenenti dati personali**|**Scopo**|
|-----|-----|
|Log generati dal sistema|Telemetria che acquisisce gli eventi di sistema e la cronologia.|
|cronologia di esecuzione|Cronologia di ogni esecuzione del flusso negli ultimi 28 giorni. Questi dati includono l'ora di inizio, l'ora di fine, lo stato e tutte le informazioni di input/output per il flusso. [Ulteriori informazioni](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Feed attività| Fornisce un riepilogo delle attività di flusso, tra cui lo stato di esecuzione, gli errori e le notifiche.|
|Processi utente|Non visibile all'utente, i processi di sistema eseguiti per conto di un utente per consentire l'esecuzione dei flussi.|
|Flussi|Logica del flusso di lavoro esistente per un flusso. [Ulteriori informazioni](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Autorizzazioni per il flusso|I flussi possono essere condivisi e riassegnati ad altri utenti. Sono disponibili elenchi di autorizzazioni per tutti i flussi. [Ulteriori informazioni](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Dettagli utente|Dettagli, che non vengono visualizzati dall'utente, che supportano l'esecuzione del flusso.|
|Connessioni|Usato dai connettori e consente la connettività a API, sistemi, database e così via. [Ulteriori informazioni](https://docs.microsoft.com/flow/add-manage-connections)|
|Autorizzazioni per la connessione|Autorizzazioni per una connessione specifica. [Ulteriori informazioni](https://docs.microsoft.com/flow/add-manage-connections)|
|Connettori personalizzati|Connettori personalizzati creati e pubblicati da un utente che consente la connettività a sistemi personalizzati o di terze parti. [Ulteriori informazioni](https://docs.microsoft.com/connectors/custom-connectors/)|
|Autorizzazioni connettore personalizzato|Elenchi di autorizzazioni per i connettori personalizzati. [Ulteriori informazioni](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|I gateway sono servizi dati locali che possono essere installati da un utente per trasferire i dati in modo rapido e sicuro tra Microsoft Flow e un'origine dati che non si trova nel cloud. [Ulteriori informazioni](https://docs.microsoft.com/flow/gateway-manage)|
|Autorizzazioni del gateway|I gateway possono essere condivisi con gli utenti all'interno di un'organizzazione. [Ulteriori informazioni](https://go.microsoft.com/fwlink/?linkid=872249)|
