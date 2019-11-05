---
title: Limiti e configurazione | Microsoft Docs
description: Limiti e configurazione
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c6a9b3c344ac25afe90c607b4a665aeaab49321f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547371"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limiti e configurazione in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Questo argomento contiene informazioni sui limiti correnti e i dettagli di configurazione per i flussi.

## <a name="request-limits"></a>Limiti delle richieste
Questi sono i limiti per una singola richiesta in uscita.

### <a name="timeout"></a>timeout

| Nome | Limite |
| --- | --- |
| Timeout della richiesta per le chiamate sincrone |120 secondi |
| Timeout della richiesta per le chiamate asincrone|Configurabile. Il valore massimo è 30 giorni. |

### <a name="message-size"></a>Dimensioni messaggio

| Nome | Limite | Note |
| --- | --- | --- |
| Dimensioni messaggio |100 MB |Non tutte le API supportano 100 MB completi. |
| Limite di valutazione delle espressioni |131.072 caratteri |`@concat()`, `@base64()``string` non può superare questo limite. |

### <a name="retry-policy"></a>Criteri di ripetizione

| Nome | Limite |
| --- | --- |
| Tentativi |90 | Il valore predefinito è 4. Per modificare le impostazioni predefinite dell'azione USA | 
| Ritardo massimo tentativi |1 giorno | |
| Ritardo minimo tentativi |5 secondi | |

## <a name="run-duration-and-retention"></a>Durata e conservazione dell'esecuzione
Questi sono i limiti per una singola esecuzione del flusso.

| Nome | Limite | Note |
| --- | --- | --- |
| Durata esecuzione |30 giorni |Include i flussi di lavoro con passaggi in sospeso come le approvazioni. Dopo 30 giorni, qualsiasi timeout dei passaggi in sospeso. Le approvazioni scadute vengono rimosse dal Centro approvazioni. Se un utente tenta di approvare una richiesta scaduta, riceverà un messaggio di errore. |
| Conservazione dell'archiviazione |30 giorni |Si tratta dell'ora di inizio dell'esecuzione. |
| Intervallo di ricorrenza minima |1 minuto | |
| Intervallo di ricorrenza max |500 giorni | |
| Conservazione della cronologia di esecuzione massima |28 giorni, per regole GDPR. | |
|Numero minimo di rimandi intervallo-licenza gratuita e piano 1|5 secondi||
|Minimum posticipate Interval-piano 2 License|1 secondo||

## <a name="looping-and-debatching-limits"></a>Limiti di ciclo e debatching
Questi sono i limiti per una singola esecuzione del flusso.

| Nome | Limite | Note |
| --- | --- | --- |
| Applica a ogni elemento-licenza gratuita|5\.000 |È possibile usare l'azione di filtro per filtrare matrici di dimensioni maggiori in base alle esigenze. |
| Applica a ogni elemento-piano 1 e licenza piano 2|100.000 |È possibile usare l'azione di filtro per filtrare matrici di dimensioni maggiori in base alle esigenze. |
| Fino a iterazioni |5\.000 | |
| Elementi SplitOn-licenza gratuita |5\.000 ||
| Elementi di SplitOn: licenza piano 1 e piano 2 |100.000 ||
| Applica a ogni parallelismo |50 |Per impostazione predefinita, i cicli vengono eseguiti in sequenza (essenzialmente, il parallelismo è 1). È possibile configurare fino a 50 in parallelo. |
| Esecuzioni di azioni per 5 minuti: gratuito, Office365, licenze del piano 1 e piani di valutazione | 2\.000 | Inoltre, è possibile distribuire un carico di lavoro in più di un flusso in base alle esigenze. |
|Esecuzioni di azioni per 5 minuti-piano a pagamento 2 licenze|100.000|Inoltre, è possibile distribuire un carico di lavoro in più di un flusso in base alle esigenze.|
|Esecuzioni di azioni per 5 minuti-piano a pagamento 2 licenze|150.000|Inoltre, è possibile distribuire un carico di lavoro in più di un flusso in base alle esigenze.|
| Azioni per le chiamate in uscita simultanee: licenza gratuita e piano 1 | ~ 500 | Ridurre il numero di richieste simultanee o ridurre la durata in base alle esigenze. |
| Esecuzioni di azioni per 24 ore: licenze gratuite, Office365, piano 1 e piani di valutazione | ~ 2.500 | Ridurre il numero di richieste simultanee o ridurre la durata in base alle esigenze. | 

## <a name="throughput-limits"></a>Limiti di velocità effettiva

|Nome|Limite|Note|
|---|---|---|
|Endpoint di runtime: numero di chiamate di lettura consentite per 5 minuti: licenza gratuita e piano 1|6\.000||
|Endpoint di runtime: numero di chiamate di lettura consentite per 5 minuti-licenza piano 2|60.000||
|Endpoint di runtime: richiama le chiamate per 5 minuti-gratuito e piano 1 licenza|4\.500||
|Endpoint di runtime: numero di chiamate Invoke ogni 5 minuti-licenza piano 2|45.000||
|Quantità di velocità effettiva consentita per 5 minuti-gratuita e licenza piano 1|600 MB||
|Quantità di velocità effettiva consentita per 5 minuti-licenza piano 2|6 GB||
|La quantità di flussi di contenuto è consentita per la produzione (input/output di azioni) per ora-gratuita, piano 1 e licenza del piano 2|200 GB||


## <a name="definition-limits"></a>Limiti delle definizioni
Questi sono i limiti per un singolo flusso.

| Nome | Limite | Note |
| --- | --- | --- |
| Azioni per flusso di lavoro |250 |È possibile aggiungere flussi di lavoro annidati per estendere questo oggetto in base alle esigenze. |
| Profondità di annidamento delle azioni consentite |8 |È possibile aggiungere flussi di lavoro annidati per estendere questo oggetto in base alle esigenze. |
| Numero massimo di caratteri per espressione |8\.192 | |
| `action`/limite del nome `trigger` |80 | |
| limite di lunghezza `description` |256 | |

## <a name="sharepoint-limits"></a>Limiti di SharePoint
Esistono alcune [limitazioni](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) per l'utilizzo di Microsoft SharePoint con Microsoft Flow e PowerApps.

## <a name="ip-address-configuration"></a>Configurazione degli indirizzi IP
L'indirizzo IP da cui vengono inviate Microsoft Flow richieste dipende dall' [area](regions-overview.md) in cui si trova l' [ambiente](environments-overview-admin.md) che contiene il flusso. Attualmente non vengono pubblicati FQDN disponibili per gli scenari di flusso.

>[!IMPORTANT]
> Alcune chiamate a un flusso possono provenire da indirizzi IP elencati nella documentazione relativa alle app per la [logica](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) . Alcuni esempi di queste chiamate includono HTTP o HTTP + OpenAPI.

### <a name="logic-apps"></a>App per la logica
Le chiamate effettuate da un flusso passano direttamente attraverso il servizio app per la logica di Azure. Alcuni esempi di queste chiamate includono HTTP o HTTP + OpenAPI. Fare riferimento [alla documentazione relativa alle app per la logica](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) per cui vengono usati gli indirizzi IP da tale servizio.

### <a name="connectors"></a>Connettori
Le chiamate effettuate da un connettore in un flusso (ad esempio, l'API SQL o l'API di SharePoint) proverranno dagli indirizzi IP elencati di seguito:

| Area | IP in uscita |
| --- | --- |
| Asia Pacifico | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Australia  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Canada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Europa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| India  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Giappone | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| America del sud | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Regno Unito | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Stati Uniti | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Anteprima (Stati Uniti)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Ad esempio, se è necessario autorizzare gli indirizzi IP per il database SQL di Azure, è necessario usare questi indirizzi.

### <a name="required-services"></a>Servizi necessari
Nella tabella seguente sono elencati i servizi a cui Microsoft Flow si connette. Assicurarsi che nessuno di questi servizi sia bloccato nella rete.

Domini | Protocolli | USA
--------|  ---------| -----
management.azure.com|https|Accesso al Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Accesso a Active Directory Authentication Library (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Accesso a Azure AD API Graph: per ottenere informazioni sull'utente, ad esempio una foto del profilo.
*. azure-apim.net|https|Accesso al runtime per i connettori.
*. flow.microsoft.com|https|Accesso al sito di Microsoft Flow.
*. powerapps.com|https|Accesso al sito di PowerApps.
*. azureedge.net|https|Accesso alla rete CDN Microsoft Flow.
nps.onyx.azure.net|https|Accesso al server dei criteri di rete (Punteggio Net Promoter).
