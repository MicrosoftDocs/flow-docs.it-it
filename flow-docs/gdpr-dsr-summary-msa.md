---
title: Riepilogo delle richieste di soggetto dei dati GDPR per account del servizio gestito Microsoft (MSA) | Microsoft Docs
description: Informazioni su come rispondere alle richieste di soggetto dei dati GPDR per Microsoft Flow.
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
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 3742ac7afed24b0a1523a6038978589d293ba00b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460302"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Rispondere alle richieste di diritti del soggetto dei dati (DSR) GPDR

Questo articolo descrive il Regolamento generale sulla protezione dei dati (GDPR, General Data Protection Regulation) dell'Unione Europea e include la procedura per supportare la conformità GDPR per gli utenti di Microsoft Flow che eseguono l'autenticazione con account del servizio gestito Microsoft (MSA).

## <a name="prerequisites"></a>Prerequisiti

Per eseguire la procedura di questo articolo è necessario avere un account del servizio gestito Microsoft (MSA) con una [licenza Microsoft Flow gratuita](https://flow.microsoft.com/pricing/).

>[!TIP]
> Le informazioni per la conformità GDPR sono disponibili anche per gli utenti che eseguono l'autenticazione con [account Azure Active Directory](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Rispondere alle richieste DSR per i dati dei clienti di Microsoft Flow

Una richiesta formale di agire sui dati personali trasmessa da un soggetto dei dati a un titolare viene definita richiesta DSR (Data Subject Rights, diritti del soggetto dei dati). Il regolamento GDPR definisce i dati personali come **tutti i dati riferiti a una persona fisica identificata o identificabile**. Il regolamento GDPR concede agli individui (detti soggetti dei dati in GDPR) i diritti per gestire i dati personali raccolti da un datore di lavoro, un'agenzia o un'organizzazione (denominata titolare del trattamento dei dati o semplicemente titolare). Questi diritti includono:

* Ottenimento di copie dei dati personali.
* Richiesta di correzione dei dati personali.
* Limitazione dell'elaborazione dei dati personali.
* Eliminazione dei dati personali.
* Ricezione dei dati personali in formato elettronico, in modo da poterli trasferire a un altro titolare.

Microsoft offre prodotti, servizi e strumenti di amministrazione che consentono ai titolari di trovare e modificare i dati personali nel cloud in risposta alle richieste DSR.

Ecco una panoramica dei processi descritti in questa guida:

1. **Individuare**: Usare gli strumenti di ricerca per trovare facilmente i dati dei clienti che potrebbero essere oggetto di una richiesta DSR. Se si determina che i documenti raccolti soddisfano le linee guida del titolare per intraprendere un'azione, è possibile eseguire una o più delle azioni DSR descritte nei passaggi seguenti. Altre informazioni sono disponibili nella [documentazione sulle procedure di individuazione per le richieste DSR in Microsoft Flow](gdpr-dsr-discovery-msa.md). Si potrebbe anche determinare che la richiesta non soddisfa le linee guida del titolare per la risposta a richieste DSR.

1. **Accesso**: Recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, crearne una copia in modo che possa essere disponibile al soggetto dei dati.

1. **Rettifica**: apportare modifiche o implementare altre azioni richieste sui dati personali, se applicabile.

1. **Limitare**: limitare l'elaborazione dei dati personali, rimuovendo le licenze per vari servizi online o disattivando i servizi desiderati, se possibile. È anche possibile rimuovere i dati dal cloud di Microsoft e conservarli in locale o in un'altra posizione.

1. **Elimina**: rimuovere in modo permanente i dati personali che risiedono nel cloud di Microsoft. Altre informazioni sull'[eliminazione dei dati personali per gli account Microsoft](gdpr-dsr-delete-msa.md). Altre informazioni sulla [chiusura di un account Microsoft](gdpr-dsr-accountclose-msa.md).

1. **Esportare**: Fornire una copia elettronica (in un formato leggibile al computer) dei dati personali. [Altre informazioni sull'esportazione dei dati personali per gli account Microsoft](gdpr-dsr-export-msa.md).
