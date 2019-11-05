---
title: Microsoft Flow per sviluppatori aziendali, ISV e partner | Microsoft Docs
description: Introduzione allo sviluppo di soluzioni per Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f26143533e84bc3ea8bc0784fef3c56eeb0551e1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547816"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow per sviluppatori aziendali, ISV e partner
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Gli sviluppatori possono estendere Microsoft Flow, abilitando soluzioni ancora più potenti per organizzazioni e clienti.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow per sviluppatori aziendali

In qualità di sviluppatore aziendale, consentire all'organizzazione di creare soluzioni personalizzate affidabili in Microsoft Flow:

- **Creare connettori personalizzati**: sviluppare connettori personalizzati per connettersi ai dati e ai servizi Web dell'organizzazione tramite Microsoft Flow. [Ulteriori informazioni](https://docs.microsoft.com/connectors/custom-connectors/)

- **Creare funzioni di Azure**: creare funzioni di Azure per estendere le app con logica personalizzata lato server. [Ulteriori informazioni](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Incorporare Microsoft Flow**: incorporare Microsoft Flow direttamente nelle esperienze del sito Web per creare soluzioni integrate, i flussi di lavoro o i processi in cui gli utenti dell'organizzazione lavorano già. [Ulteriori informazioni](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow per ISV e partner Microsoft

Un partner Microsoft o un fornitore di software indipendente (ISV) accelera l'adozione dei clienti estendendo i prodotti per l'integrazione con i dati e i processi aziendali dei clienti, nonché aggiungere e personalizzare i flussi di lavoro per automatizzare i processi aziendali come parte del applicazione. Dopo aver completato i sette passaggi seguenti, l'applicazione sarà in grado di sfruttare un potente motore di flusso di lavoro scalabile su cloud in grado di connettersi a più di 200 servizi diversi.

| Fase | Passo | Quando necessario? |
| --- | --- | --- |
| Sviluppo | 1. creare un connettore personalizzato per i dati | Se si desidera esporre i propri dati ISV a PowerApps o Microsoft Flow |
| Sviluppo | 2. aggiungere il supporto per l'applicazione per autenticare gli utenti con Azure Active Directory (Azure AD) | Se si vuole incorporare l'interfaccia utente o l'elenco Microsoft Flow in Microsoft AppSource | 
| Sviluppo | 3. incorporare l'interfaccia utente di Microsoft Flow nell'applicazione usando l'iframe basato sul Web | Se si vuole includere la creazione o la gestione del flusso nell'applicazione | 
| Sviluppo | 4. creare e pubblicare modelli di flusso | Se si vuole pre-compilare i flussi per i clienti | 
| Sviluppo | 5. aggiungere la logica dell'applicazione per distribuire i flussi a livello di codice | Se si vuole distribuire automaticamente i flussi predefiniti per i clienti | 
| Distribuzione | 6. Concedi ai tuoi clienti le licenze per Microsoft Flow tramite il programma Microsoft Cloud Solution Provider | Se i clienti non hanno licenze di Office 365 o Dynamics 365 |
| Distribuzione | 7. elencare la soluzione in Microsoft AppSource | Consigliato per aumentare la visibilità della soluzione ISV |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. connessione alle API o consentire ai clienti di connettersi alle API

In qualità di ISV, spesso si hanno dati proprietari a cui si vuole che i clienti accedano attraverso i flussi. È possibile esporre l'accesso a tutti i dati tramite un connettore personalizzato. [Ulteriori informazioni](https://docs.microsoft.com/connectors/custom-connectors/)

Una volta creati, esistono due modi per rendere disponibile il connettore ai clienti:
- Il connettore può essere distribuito nel tenant del cliente tramite le API REST o PowerShell.
- Per rendere il connettore personalizzato disponibile pubblicamente per tutti gli utenti, è possibile inviare il connettore per la certificazione. [Ulteriori informazioni](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. autenticazione 

Per chiamare le API REST e incorporare l'interfaccia utente autenticata, l'applicazione deve usare Azure AD Single Sign-On federato per autenticare gli utenti finali e i clienti. Per informazioni su come abilitare l'accesso SSO federato di AAD, [vedere qui](https://identity.microsoft.com/) . Non è supportato l'accesso non autenticato o l'accesso con provider di identità diversi da Azure AD. 

### <a name="3-embedding-ui-components"></a>3. incorporamento dei componenti dell'interfaccia utente

Incorpora Microsoft Flow all'interno dell'app per abilitare l'integrazione profonda nel contesto tra l'app e tutti gli altri servizi supportati da Microsoft Flow. [Ulteriori informazioni](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. creare e pubblicare modelli di flusso

Quando si dispone di un connettore, è consigliabile pubblicare modelli che dimostrino come usare il servizio. Questi modelli vengono usati come esempi che gli utenti possono usare per apprendere e quindi estendere i propri flussi di lavoro univoci. [Ulteriori informazioni](../publish-a-template.md)

### <a name="5-deployment"></a>5. distribuzione

Per consentire agli utenti finali di accedere ai flussi che possono usare automaticamente, distribuire i flussi nel tenant Azure AD dell'utente. Usare un pacchetto di distribuzione distribuito usando le API REST o PowerShell. [Ulteriori informazioni](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. licenze

Se i clienti hanno già Office 365 o Dynamics 365 e queste licenze sono associate alle identità con cui gli utenti accedono Azure AD, non sono previsti ulteriori requisiti di licenza. Tuttavia, se i clienti non usano Office 365 o Dynamics 365, è necessario acquisire i diritti di utilizzo per conto di Microsoft Flow, in modo che siano concessi in licenza per sfruttare tali componenti incorporati nell'applicazione.

Offriamo il programma [Microsoft Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) per acquisire licenze per conto dei clienti. Per Microsoft Flow sono disponibili due [piani tariffari](https://flow.microsoft.com/pricing/) diversi, che è necessario verificare per i dettagli relativi a piani e funzionalità.

### <a name="7-list-on-appsource"></a>7. elenco in AppSource

Dopo aver integrato Microsoft Flow nell'applicazione, è possibile elencarlo in AppSource. Con AppSource è possibile generare nuovi lead per l'azienda creando un'app e pubblicando tale app in AppSource per il test drive da nuovi clienti. [Ulteriori informazioni](dev-appsource-test-drive.md)
