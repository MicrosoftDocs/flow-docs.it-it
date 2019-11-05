---
title: Riepilogo richieste oggetto dati GDPR | Microsoft Docs
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: c4d2686e9da00aaccc46e62570de387678bd1ece
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548214"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Risposta alle richieste del soggetto dei dati GDPR per Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Questo articolo prepara l'utente e l'organizzazione per la Regolamento generale sulla protezione dei dati dell'Unione europea (GDPR). Questo articolo non solo descrive cosa sta facendo Microsoft per prepararsi per la GDPR, ma condivide anche esempi di passaggi che è possibile intraprendere per supportare la conformità GDPR quando si usa PowerApps, Microsoft Flow e Common Data Service.

## <a name="prerequisites"></a>Prerequisiti

Gli utenti e gli amministratori possono eseguire le azioni descritte in questo articolo.

### <a name="users"></a>Utenti

Un utente deve disporre di un account Azure Active Directory attivo con una [licenza di Microsoft Flow](https://preview.flow.microsoft.com/pricing/). Gli utenti che non soddisfano questo requisito devono richiedere a un amministratore di eseguire queste azioni.

### <a name="administrators"></a>Amministratori

È possibile eseguire le operazioni che richiedono privilegi di amministratore, descritte in questo articolo, se si accede all'interfaccia di [amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/) o a [PowerApps admin PowerShell](https://go.microsoft.com/fwlink/?linkid=871804) con un account che dispone di entrambe le autorizzazioni seguenti:

- Una licenza a pagamento o di valutazione per PowerApps piano 2.

    [Una licenza di valutazione](http://web.powerapps.com/trial) scade tra 30 giorni.

- [Amministratore globale di Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) o [Azure Active Directory amministratore globale](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Tenant non gestiti
Se si è membri di un [tenant non gestito](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), vale a dire che il tenant di Azure ad non dispone di un amministratore globale, sarà comunque possibile seguire la procedura descritta in questo articolo per esportare e rimuovere i dati personali. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Risposta a DSRs per i dati del cliente Microsoft Flow

Il GDPR fornisce ai dipendenti (noti in GDPR come soggetti dati) i diritti per gestire i dati personali raccolti da un datore di lavoro o da un altro tipo di agenzia o organizzazione (noto come controller dati o solo controller). I dati personali vengono definiti in modo molto ampio sotto la GDPR come tutti i dati che si riferiscono a un utente naturale identificato o identificabile. Il GDPR fornisce ai soggetti dati diritti specifici sui dati personali; questi diritti includono l'ottenimento di copie di dati personali, la richiesta di correzioni, la limitazione dell'elaborazione, l'eliminazione o la ricezione in formato elettronico, in modo che possa essere spostata in un altro controller. Una richiesta formale da un soggetto interessato a un controller per eseguire un'azione sui dati personali è detta richiesta di diritti dei soggetti interessati (DSR).

Questo articolo illustra come usare i prodotti, i servizi e gli strumenti di amministrazione di Microsoft per aiutare i controller a trovare e agire sui dati personali quando rispondono a DSRs. In particolare, questo articolo include come trovare, accedere e agire sui dati personali che risiedono nel cloud di Microsoft. Ecco una rapida panoramica dei processi descritti in questa guida:

1. Scopri: usare gli strumenti di ricerca e individuazione per trovare più facilmente i dati dei clienti che possono essere soggetti a un DSR. Una volta raccolti i documenti potenzialmente reattivi, è possibile eseguire una o più delle azioni DSR descritte nei passaggi seguenti per rispondere alla richiesta. In alternativa, è possibile determinare che la richiesta non soddisfa le linee guida della propria organizzazione per rispondere a DSRs. [Documentazione di individuazione di Microsoft Flow DSR](gdpr-dsr-discovery.md)

1. Accesso: recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, effettuarne una copia che può essere disponibile per l'oggetto dati.

1. Rettifica: apportare modifiche o implementare altre azioni richieste sui dati personali, ove applicabile.

    Se un soggetto interessato chiede di rettificare i dati personali che risiedono nell'organizzazione, l'utente e l'organizzazione devono determinare se è opportuno rispettare la richiesta.  La rettifica dei dati può includere l'esecuzione di azioni come la modifica, relazioni o la rimozione dei dati personali.

    È possibile usare Azure Active Directory per gestire le identità di Microsoft Flow degli utenti. I clienti aziendali possono gestire le richieste di rettifica del DSR, incluse le funzionalità di modifica limitate, in base alla natura di un determinato servizio Microsoft.  In qualità di Elaboratore di dati, Microsoft non offre la possibilità di correggere i log generati dal sistema, perché questi log riflettono le attività effettive e costituiscono un record cronologico di eventi all'interno dei servizi Microsoft.  [Altre informazioni su DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Limitazione: limitare l'elaborazione dei dati personali, rimuovendo le licenze per vari Servizi online o spegnendo laddove possibile i servizi desiderati. È anche possibile rimuovere i dati dal cloud Microsoft e conservarli in locale o in un'altra posizione.

    Gli oggetti dati possono richiedere di limitare l'elaborazione dei dati personali.  Microsoft fornisce API (Application Programming Interface) e interfacce utente (UI) a questo scopo.  Queste interfacce consentono all'amministratore tenant del cliente aziendale di gestire tali DSRs tramite una combinazione di esportazione dei dati e eliminazione dei dati. Un cliente può (1) esportare una copia elettronica dei dati personali dell'utente, inclusi gli account, i log generati dal sistema e i log associati, seguiti con (2) l'eliminazione dell'account e i dati associati che risiedono all'interno dei sistemi Microsoft.

1. Elimina: rimuovere in modo permanente i dati personali che risiedono nel cloud di Microsoft. [Altre informazioni sull'eliminazione dei dati personali](gdpr-dsr-delete.md).

1. Export: fornire una copia elettronica (in un formato leggibile dal computer) dei dati personali al soggetto interessato. In ogni sezione di questo articolo vengono descritte le procedure tecniche che un'organizzazione del controller dei dati può intraprendere per rispondere a un DSR per i dati personali nel cloud Microsoft. [Altre informazioni sull'esportazione dei dati personali](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Log generati dal sistema

Per ulteriori informazioni sui log generati dal sistema per Microsoft Flow, fare riferimento a questa [Guida](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) .
