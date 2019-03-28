---
title: Riepilogo delle richieste di soggetto dei dati GDPR | Microsoft Docs
description: Informazioni su come rispondere alle richieste di soggetto dei dati GPDR per Microsoft Flow.
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
ms.date: 4/24/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 1eaa98b674e78f46988d253e2be76a5d92283a76
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2019
ms.locfileid: "58353126"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Risposta alle richieste di soggetto dei dati GDPR per Microsoft Flow

Le informazioni in questo articolo consentono di preparare amministratori e organizzazioni per il Regolamento generale sulla protezione dei dati (GDPR) dell'Unione europea. Questo articolo non solo descrive le iniziative di Microsoft per prepararsi per il regolamento GDPR, ma condivide anche esempi delle procedure adottabili sin da subito per supportare la conformità a GDPR quando si usano PowerApps, Microsoft Flow e Common Data Service.

## <a name="prerequisites"></a>Prerequisiti

Gli utenti e gli amministratori possono eseguire le azioni descritte in questo articolo.

### <a name="users"></a>Utenti

Un utente deve avere un account Azure Active Directory attivo con un [licenza Microsoft Flow](https://preview.flow.microsoft.com/pricing/). Gli utenti che non soddisfano questo requisito devono chiedere a un amministratore di eseguire queste azioni.

### <a name="administrators"></a>Amministratori

È possibile eseguire le operazioni che richiedono privilegi di amministratore, descritte in questo articolo, se si esegue l'accesso all'[interfaccia di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/) o a [PowerShell per amministratori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) con un account che dispone di entrambe queste autorizzazioni:

- Una licenza a pagamento o di valutazione per PowerApps Piano 2.

    [Una licenza di valutazione](http://web.powerapps.com/trial) scade dopo 30 giorni.

- [Amministratore globale di Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) oppure [Amministratore globale di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Tenant non gestiti
Se l'utente appartiene a un [tenant non gestito](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), ovvero se il tenant Azure AD non ha un amministratore globale, l'utente può comunque seguire la procedura descritta in questo articolo per esportare e rimuovere i dati personali. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Risposta alle richieste DSR per i dati dei clienti di Microsoft Flow

Il regolamento GDPR concede diritti agli individui (noti come soggetti dei dati in GDPR) per gestire i dati personali raccolti da un datore di lavoro o un altro tipo di agenzia o organizzazione (noto come titolare del trattamento dei dati o semplicemente titolare). Nell'ambito del regolamento GDPR i dati personali hanno una definizione molto ampia, ovvero sono tutti i dati riferiti a una persona fisica identificata o identificabile. In base al regolamento GDPR, ai soggetti dei dati vengono assegnati diritti specifici per i dati personali, tra i quali ottenere copie dei dati personali, richiedere correzioni di tali dati, limitarne l'elaborazione, eliminarli o riceverli in formato elettronico in modo che possano essere trasferiti a un altro titolare. Una richiesta formale da un soggetto dei dati a un titolare di agire sui dati personali viene definita richiesta DSR (Data Subject Rights, diritti del soggetto dei dati).

Questo articolo illustra come usare i prodotti, i servizi e gli strumenti di amministrazione di Microsoft per consentire ai titoli di individuare i dati personali e agire su di essi in risposta alle richieste DSR. In particolare, questo articolo include indicazioni per trovare, accedere e agire sui dati personali che si risiedono nel cloud di Microsoft. Ecco una rapida panoramica dei processi descritti in questa guida:

1. Individuazione: usare strumenti di ricerca e individuazione per trovare più facilmente i dati dei clienti che potrebbero essere oggetto di una richiesta DSR. Dopo aver raccolto i documenti potenzialmente interessati, è possibile eseguire una o più delle azioni DSR descritte nei passaggi seguenti per rispondere alla richiesta. Si potrebbe anche determinare che la richiesta non soddisfa le linee guida della propria organizzazione per rispondere a richieste DSR. [Documentazione sulle procedure di individuazione per le richieste DSR in Microsoft Flow](gdpr-dsr-discovery.md)

1. Accesso: recuperare i dati personali che risiedono nel cloud di Microsoft e, se richiesto, crearne una copia che può essere resa disponibile al soggetto dei dati.

1. Rettifica: apportare modifiche o implementare altre azioni richieste sui dati personali, se applicabile.

    Se un soggetto dei dati richiede la rettifica dei dati personali che si trovano all'interno dell'organizzazione, l'amministratore e l'organizzazione devono determinare se è appropriato soddisfare la richiesta.  La rettifica dei dati può includere l'esecuzione di azioni, come la modifica, la revisione o la rimozione dei dati personali.

    È possibile usare Azure Active Directory per gestire le identità degli utenti di Microsoft Flow. I clienti aziendali possono gestire le richieste di rettifica DSR, incluse funzionalità di modifica limitate, in base alla natura di un determinato servizio Microsoft.  In quanto responsabile del trattamento dei dati, Microsoft non offre la possibilità di correggere i log generati dal sistema, in quanto questi log riflettono attività concrete e costituiscono un record cronologico degli eventi all'interno di servizi Microsoft.  [Altre informazioni sulle richieste DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Limitazione: limitare l'elaborazione dei dati personali, rimuovendo le licenze per vari servizi online o disattivando i servizi desiderati, se possibile. È anche possibile rimuovere i dati dal cloud di Microsoft e conservarli in locale o in un'altra posizione.

    I soggetti dei dati possono richiedere la limitazione dell'elaborazione dei dati personali.  Microsoft offre API (Application Programming Interface) e interfacce utente a questo scopo.  Queste interfacce consentono all'amministratore tenant del cliente aziendale di gestire queste richieste DSR tramite una combinazione di esportazione dei dati ed eliminazione dei dati. Un cliente potrebbe (1) esportare una copia in formato elettronico dei dati personali dell'utente, tra cui account, log generati dal sistema e log associati, e in seguito (2) eliminare l'account e i dati associati che risiedono all'interno di sistemi Microsoft.

1. Eliminazione: rimuovere in modo permanente i dati personali che risiedono nel cloud di Microsoft. [Altre informazioni sull'eliminazione dei dati personali](gdpr-dsr-delete.md).

1. Esportazione: consegnare una copia elettronica (in un formato leggibile al computer) dei dati personali al soggetto dei dati. In ogni sezione di questo articolo vengono descritte le procedure tecniche che un'organizzazione titolare del trattamento dei dati può adottare per rispondere a una richiesta DSR per dati personali nel cloud di Microsoft. [Altre informazioni sull'esportazione dei dati personali](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Log generati dal sistema

Fare riferimento a questa [guida](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) per altre informazioni sui log generati dal sistema per Microsoft Flow.
