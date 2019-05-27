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
ms.date: 12/04/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 615d13adaee8b5db302065b3c21a488504f39398
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64906404"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limiti e configurazione in Microsoft Flow
Questo argomento contiene le informazioni sui limiti e sui dettagli di configurazione per i flussi.

## <a name="request-limits"></a>Limiti di richiesta
Questi sono i limiti per una singola richiesta in uscita.

### <a name="timeout"></a>Timeout

| Nome | Limite |
| --- | --- |
| Timeout della richiesta per le chiamate sincrone |120 secondi |
| Timeout della richiesta per le chiamate asincrone|Configurabile. Il valore massimo è 30 giorni. |

### <a name="message-size"></a>Dimensione del messaggio

| Nome | Limite | Note |
| --- | --- | --- |
| Dimensione del messaggio |100 MB |Non tutte le API supportano tutti i 100 MB. |
| Limite per la valutazione delle espressioni |131.072 caratteri |`@concat()`, `@base64()`, `string` non possono superare questo limite. |

### <a name="retry-policy"></a>Criteri di ripetizione

| Nome | Limite |
| --- | --- |
| Numero tentativi |90 | Il valore predefinito è 4. Per modificare l'impostazione predefinita usare le impostazioni dell'azione | 
| Intervallo massimo tra tentativi |1 giorno | |
| Intervallo minimo tra tentativi |5 secondi | |

## <a name="run-duration-and-retention"></a>Durata e conservazione esecuzione
Questi sono i limiti per una singola esecuzione del flusso.

| Nome | Limite | Note |
| --- | --- | --- |
| Durata dell'esecuzione |30 giorni |Include i flussi di lavoro con passaggi in sospeso, ad esempio le approvazioni. Il timeout di eventuali passaggi in sospeso è previsto dopo 30 giorni. Dopo il timeout, le approvazioni vengono rimosse dal Centro approvazioni. Se un utente tenta di approvare una richiesta dopo il timeout, riceverà un messaggio di errore. |
| Conservazione archiviazione |30 giorni |A partire dall'ora di inizio esecuzione. |
| Intervallo di ricorrenza min |1 minuto | |
| Intervallo di ricorrenza max |500 giorni | |
| Tempo massimo di conservazione cronologia di esecuzione |28 giorni, in base alle regole GDPR. | |
|Intervallo minimo postone: gratuito e prevede 1 licenza|5 secondi||
|Valore minimo posticipare interval - piano 2|1 secondo||

## <a name="looping-and-debatching-limits"></a>Limiti di ciclo e debatch
Questi sono i limiti per una singola esecuzione del flusso.

| Nome | Limite | Note |
| --- | --- | --- |
| Si applica a ogni elementi - licenza gratuita|5.000 |È possibile usare l'azione di filtro per filtrare matrici di dimensioni superiori secondo le esigenze. |
| Si applica a ogni elementi - piano 1 e piano 2|100.000 |È possibile usare l'azione di filtro per filtrare matrici di dimensioni superiori secondo le esigenze. |
| Iterazioni Until |5.000 | |
| Elementi SplitOn - licenza gratuita |5.000 ||
| Elementi SplitOn - piano 1 e piano 2 |100.000 ||
| Applica a ogni Parallelismo |50 |Per impostazione predefinita, i cicli vengono eseguiti in sequenza (in pratica, il parallelismo è 1). È possibile configurarne fino a 50 in parallelo. |
| Piano 1 licenza e esecuzioni di azioni per 5 minuti - gratuito | 2,000 | Inoltre, è possibile distribuire un carico di lavoro tra più di un flusso in base alle esigenze. |
|Esecuzioni di azioni per 5 minuti - piano 2|100.000|Inoltre, è possibile distribuire un carico di lavoro tra più di un flusso in base alle esigenze.|
| Azioni simultanee le chiamate in uscita - gratuiti e prevede 1 licenza | ~500 | Ridurre il numero di richieste simultanee o ridurre la durata in base alle esigenze. |
| Azioni simultanee le chiamate in uscita - gratuiti e prevede 1 licenza | ~2.500 | Ridurre il numero di richieste simultanee o ridurre la durata in base alle esigenze. | 

## <a name="throughput-limits"></a>Limiti di velocità effettiva

|Nome|Limite|Note|
|---|---|---|
|Endpoint di runtime - numero di licenza-piano 1 e chiamate di lettura consentite per ogni 5 minuti - gratuito|6,000||
|Endpoint di runtime - numero di chiamate consentite per ogni 5 minuti - piano 2|60,000||
|Endpoint di runtime: Invoke-piano 1 licenza e le chiamate per 5 minuti - gratuito|4,500||
|Endpoint di runtime: Numero di chiamate di invoke per 5 minuti - piano 2|45,000||
|Quantità di licenze-piano 1 e velocità effettiva consentita ogni 5 minuti - gratuito|600 MB||
|Quantità di velocità effettiva consentita ogni 5 minuti - piano 2|6 GB||
|Quantità di flussi di contenuto sono consentiti per produrre (input/output di azioni) per ogni ora: gratuito, piano 1 e piano 2|200 GB||


## <a name="definition-limits"></a>Limiti di definizione
Questi sono i limiti per un singolo flusso.

| Nome | Limite | Note |
| --- | --- | --- |
| Azioni per ogni flusso di lavoro |250 |È possibile aggiungere flussi di lavoro annidati per estendere il supporto in base alle esigenze. |
| Profondità di annidamento di azione consentita |5 |È possibile aggiungere flussi di lavoro annidati per estendere il supporto in base alle esigenze. |
| Numero massimo caratteri per ogni espressione |8.192 | |
| Limite nome `action`/`trigger` |80 | |
| Limite lunghezza `description` |256 | |

## <a name="sharepoint-limits"></a>Limiti di SharePoint
Sono previste [limitazioni](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) per l'uso di Microsoft SharePoint con Microsoft Flow e PowerApps.

## <a name="ip-address-configuration"></a>Configurazione dell'indirizzo IP
L'indirizzo IP da cui vengono inviate le richieste di Microsoft Flow dipende dall'[area](regions-overview.md) in cui si trova l'[ambiente](environments-overview-admin.md) che include il flusso. Attualmente non sono disponibili FQDN per gli scenari di flusso.

>[!IMPORTANT]
> Alcune chiamate di un flusso rende possono provenire da IP indirizzi che sono elencati nel [App per la logica](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) documentazione. Alcuni esempi di queste chiamate includono HTTP o HTTP + OpenAPI.

### <a name="logic-apps"></a>App per la logica
Le chiamate effettuate da un flusso di passano direttamente attraverso il servizio App per la logica di Azure. Alcuni esempi di queste chiamate includono HTTP o HTTP + OpenAPI. Fare riferimento alla [documentazione di App per la logica](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) per informazioni sugli indirizzi IP usati da tale servizio.

### <a name="connectors"></a>Connettori
Le chiamate effettuate da un connettore in un flusso (ad esempio, l'API SQL o l'API SharePoint) proverranno dagli indirizzi IP elencati di seguito:

| Area | IP in uscita |
| --- | --- |
| Asia Pacifico | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Australia  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Canada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Europa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| India  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Giappone | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| America del Sud | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Regno Unito | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Stati Uniti | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Anteprima (Stati Uniti)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Ad esempio, se è necessario autorizzare gli indirizzi IP per il database SQL di Azure, è necessario usare questi indirizzi.

### <a name="required-services"></a>Servizi necessari
La tabella seguente elenca i servizio a cui si connette Microsoft Flow. Assicurarsi che nessuno di questi servizi risulti bloccato nella rete corrente.

Domini | Protocolli | Utilizzo
--------|  ---------| -----
management.azure.com|https|Accesso ad Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Accesso ad Active Directory Authentication Library (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Accesso all'API Graph di Azure AD per recuperare informazioni sull'utente, ad esempio la foto del profilo.
*.azure-apim.net|https|Accesso al runtime per i connettori.
*.flow.microsoft.com|https|Accesso al sito di Microsoft Flow.
*.powerapps.com|https|Accesso al sito PowerApps.
*.azureedge.net|https|Accesso alla rete CDN di Microsoft Flow.
nps.onyx.azure.net|https|Accesso a Punteggio di promozione della rete (NPS, Net Promoter Score).
