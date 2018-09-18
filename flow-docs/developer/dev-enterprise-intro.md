---
title: Microsoft Flow per sviluppatori aziendali, ISV e partner | Microsoft Docs
description: Introduzione allo sviluppo di soluzioni per Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: mblythe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f510d387b594bb11306f8bc2530573b775e5f08e
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690400"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow per sviluppatori aziendali, ISV e partner

Gli sviluppatori hanno la possibilità di estendere Microsoft Flow, realizzando così soluzioni ancora più potenti per le organizzazioni e i clienti.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow per sviluppatori aziendali

Gli sviluppatori aziendali permettono all'organizzazione di creare soluzioni personalizzate affidabili in Microsoft Flow:

- **Creare connettori personalizzati**: sviluppare connettori personalizzati per connettersi ai dati e ai servizi Web dell'organizzazione tramite Microsoft Flow. [Altre informazioni](https://docs.microsoft.com/connectors/custom-connectors/)

- **Creare funzioni di Azure**: sviluppare funzioni di Azure per estendere le app con logica personalizzata sul lato server. [Altre informazioni](https://docs.microsoft.com/azure/azure-functions/functions-flow-scenario)

- **Incorporare Microsoft Flow**: incorporare Microsoft Flow direttamente nelle esperienze dei siti Web per creare soluzioni integrate, sulla base dei flussi di lavoro o dei processi già usati dalle persone dell'organizzazione per svolgere il lavoro. [Altre informazioni](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow per ISV e partner Microsoft

Come partner Microsoft o fornitore di software indipendenti (ISV), è possibile promuovere l'adozione dei prodotti da parte dei clienti estendendoli per integrare i dati e i processi aziendali dei clienti, nonché aggiungere e personalizzare flussi di lavoro per automatizzare i processi aziendali come parte dell'applicazione. Dopo aver completato i sette passaggi seguenti, l'applicazione avrà la possibilità di sfruttare un motore per flussi di lavoro di livello cloud affidabile, in grado di connettersi a più di 200 servizi diversi.

| Fase | Passaggio | Scopo |
| --- | --- | --- |
| Sviluppo | 1. Creare un connettore personalizzato per i dati | Per esporre i dati ISV personalizzati in PowerApps o Microsoft Flow |
| Sviluppo | 2. Aggiungere all'applicazione il supporto per l'autenticazione degli utenti con Azure Active Directory (Azure AD) | Per incorporare l'interfaccia utente di Microsoft Flow o pubblicare l'applicazione in Microsoft AppSource | 
| Sviluppo | 3. Incorporare l'interfaccia utente di Microsoft Flow nell'applicazione tramite l'iframe Microsoft basato sul Web | Per includere funzionalità di creazione e gestione dei flussi nell'applicazione | 
| Sviluppo | 4. Creare e pubblicare modelli di flusso | Per precompilare flussi per i clienti | 
| Sviluppo | 5. Aggiungere logica dell'applicazione per la distribuzione di flussi a livello di programmazione | Per distribuire automaticamente i flussi precompilati ai clienti | 
| Distribuzione | 6. Concedere ai clienti licenze per Microsoft Flow tramite il programma Microsoft Cloud Solution Provider | Se i clienti non hanno licenze di Office 365 o di Dynamics 365 |
| Distribuzione | 7. Pubblicare la soluzione in Microsoft AppSource | Scelta consigliata per aumentare la visibilità della soluzione ISV |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. Connessione alle API o abilitazione dei clienti per la connessione alle API

Gli ISV hanno spesso dati proprietari che vogliono rendere accessibili ai clienti tramite i flussi. È possibile esporre l'accesso a tutti i dati tramite un connettore personalizzato. [Altre informazioni](https://docs.microsoft.com/connectors/custom-connectors/)

Dopo aver creato il connettore, è possibile renderlo disponibile ai clienti in due modi:
- Il connettore può essere distribuito nel tenant del cliente tramite le API REST o PowerShell.
- Per rendere disponibile pubblicamente il connettore personalizzato per tutti gli utenti, è possibile inviare il connettore per la certificazione. [Altre informazioni](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. Autenticazione 

Per chiamare le API REST e incorporare l'interfaccia utente autenticata, l'applicazione deve usare l'accesso Single Sign-On federato di Azure AD per autenticare gli utenti finali e i clienti. [Vedere qui](https://identity.microsoft.com/) per informazioni su come abilitare l'accesso Single Sign-On federato in AAD. Non è supportato l'accesso non autenticato o l'accesso con provider di identità diversi da Azure AD. 

### <a name="3-embedding-ui-components"></a>3. Incorporamento di componenti dell'interfaccia utente

Incorporare Microsoft Flow all'interno dell'app per abilitare l'integrazione profonda nel contesto tra l'app e tutti gli altri servizi supportati da Microsoft Flow. [Altre informazioni](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. Creare e pubblicare modelli di flusso

Dopo aver creato un connettore, è consigliabile pubblicare modelli che illustrino come usare il servizio. Questi modelli fungeranno da esempi che gli utenti potranno usare per apprendere e quindi estenderli ai propri flussi di lavoro univoci. [Altre informazioni](../publish-a-template.md)

### <a name="5-deployment"></a>5. Distribuzione

Per consentire agli utenti finali l'accesso a flussi che possono usare automaticamente, distribuire i flussi nel tenant di Azure AD dell'utente. Usare un pacchetto di distribuzione da distribuire con le API REST o PowerShell. [Altre informazioni](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. Licenze

Se i clienti hanno già Office 365 o Dynamics 365 e queste licenze sono associate alle identità usate per l'accesso ad Azure AD, non sono previsti altri requisiti di licenza. Tuttavia, se i clienti non usano Office 365 o Dynamics 365, è necessario acquisire i diritti di utilizzo per loro conto per Microsoft Flow, in modo che dispongano della licenza per usare tali componenti incorporati nell'applicazione.

Microsoft offre il programma [Microsoft Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) per l'acquisizione delle licenze per conto dei clienti. Per Microsoft Flow esistono due diversi [piani tariffari](https://flow.microsoft.com/pricing/), che è consigliabile esaminare per altri dettagli sui piani e le relative funzionalità.

### <a name="7-list-on-appsource"></a>7. Pubblicare in AppSource

Dopo aver integrato Microsoft Flow nell'applicazione, è possibile pubblicarla in AppSource. Con AppSource è possibile generare nuovi lead per l'azienda creando un'app e pubblicandola in AppSource per il test drive da parte dei nuovi clienti. [Altre informazioni](dev-appsource-test-drive.md)
