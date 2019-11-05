---
title: Riepilogo delle richieste del soggetto dei dati GDPR per gli account Microsoft (MSA) | Microsoft Docs
description: Informazioni su come rispondere alle richieste del soggetto dei dati alle GPDR per Microsoft Flow.
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
ms.openlocfilehash: bff3e050db40c60622496202a092f94cc1d36fca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548171"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Rispondere alle richieste dei soggetti interessati GDPR (DSRs)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Questo articolo descrive la Regolamento generale sulla protezione dei dati (GDPR) dell'Unione europea e illustra le procedure da eseguire per supportare la conformità GDPR per gli utenti Microsoft Flow che eseguono l'autenticazione con gli account Microsoft (MSA).

## <a name="prerequisites"></a>Prerequisiti

Per eseguire la procedura descritta in questo articolo, è necessario un account del servizio gestito con [licenza gratuita Microsoft Flow](https://flow.microsoft.com/pricing/) .

>[!TIP]
> Le informazioni di conformità di GDPR sono disponibili anche per gli utenti che eseguono l'autenticazione con [account Azure Active Directory](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Rispondi a DSRs per i dati del cliente Microsoft Flow

Una richiesta formale del soggetto dati a un controller per eseguire un'azione sui dati personali è detta richiesta di diritti dei soggetti interessati (DSR). GDPR definisce i dati personali come **tutti i dati che si riferiscono a un utente naturale identificato o identificabile**. Il GDPR fornisce ai dipendenti (noti come soggetti dati) diritti per gestire i dati personali raccolti da un datore di lavoro, da un'agenzia o da un'organizzazione (noto come controller dati o controller). Questi diritti includono:

* Ottenere copie dei dati personali.
* Richiesta di correzioni ai dati personali.
* Limitazione dell'elaborazione dei dati personali.
* Eliminazione dei dati personali.
* Ricezione di dati personali in formato elettronico in modo da poterli spostare in un altro controller.

Microsoft offre prodotti, servizi e strumenti per aiutare i controller a trovare e agire sui dati personali quando rispondono alle richieste di DSRs di dati che si trovano nel cloud.

Ecco una panoramica dei processi descritti in questa guida:

1. **Discover**: usare gli strumenti di ricerca e individuazione per trovare facilmente i dati dei clienti che potrebbero essere l'oggetto di una richiesta DSR. Se si stabilisce che i documenti raccolti soddisfano le linee guida del controller per l'esecuzione di azioni, è possibile eseguire una o più delle azioni DSR descritte nei passaggi seguenti. Per altre informazioni, vedere la [documentazione di individuazione di Microsoft Flow DSR per gli account Microsoft](gdpr-dsr-discovery-msa.md). In alternativa, è possibile determinare che la richiesta non soddisfa le linee guida del controller per rispondere alle richieste dei soggetti interessati.

1. **Accesso**: recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, effettuarne una copia in modo che possa essere disponibile per l'oggetto dati.

1. **Rettifica**: apportare modifiche o implementare altre azioni richieste sui dati personali, ove applicabile.

1. **Limitazione**: limitare l'elaborazione dei dati personali, rimuovendo le licenze per vari servizi online o spegnendo laddove possibile i servizi desiderati. È anche possibile rimuovere i dati dal cloud Microsoft e conservarli in locale o in un'altra posizione.

1. **Elimina**: rimuovere in modo permanente i dati personali che risiedono nel cloud di Microsoft. Altre informazioni sull' [eliminazione dei dati personali per gli account Microsoft](gdpr-dsr-delete-msa.md). Altre informazioni sulla [chiusura di un account Microsoft](gdpr-dsr-accountclose-msa.md).

1. **Export**: fornire una copia elettronica (in un formato leggibile dal computer) dei dati personali. [Altre informazioni sull'esportazione dei dati personali per gli account Microsoft](gdpr-dsr-export-msa.md).
