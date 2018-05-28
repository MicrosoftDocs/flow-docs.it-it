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
ms.date: 01/31/2018
ms.author: stepsic
ms.openlocfilehash: 9b2447ce0a7c9bc353e47ee1edb4bea55f2c49f4
ms.sourcegitcommit: f9be24c533003146d75e5a7fa6e40356d4ce47d7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2018
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
| Numero tentativi |4 |

## <a name="run-duration-and-retention"></a>Durata e conservazione esecuzione
Questi sono i limiti per una singola esecuzione del flusso.

| Nome | Limite | Note |
| --- | --- | --- |
| Durata dell'esecuzione |30 giorni |Include i flussi di lavoro con passaggi in sospeso, ad esempio le approvazioni. Il timeout di eventuali passaggi in sospeso è previsto dopo 30 giorni. Dopo il timeout, le approvazioni vengono rimosse dal Centro approvazioni. Se un utente tenta di approvare una richiesta dopo il timeout, riceverà un messaggio di errore. |
| Conservazione archiviazione |30 giorni |A partire dall'ora di inizio esecuzione. |
| Intervallo di ricorrenza min |1 minuto | |
| Intervallo di ricorrenza max |500 giorni | |
| Tempo massimo di conservazione cronologia di esecuzione |28 giorni, in base alle regole GDPR. | |

## <a name="looping-and-debatching-limits"></a>Limiti di ciclo e debatch
Questi sono i limiti per una singola esecuzione del flusso.

| Nome | Limite | Note |
| --- | --- | --- |
| Elementi ForEach |5.000 |È possibile usare l'azione di filtro per filtrare matrici di dimensioni superiori secondo le esigenze. |
| Iterazioni Until |5.000 | |
| Elementi SplitOn |5.000 | |
| Parallelismo ForEach |1 | |

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

### <a name="logic-app-service"></a>Servizio app per la logica
Le chiamate effettuate da un flusso di passano direttamente attraverso il servizio App per la logica di Azure. Alcuni esempi di queste chiamate includono HTTP o HTTP + OpenAPI. Le chiamate proverranno dai seguenti indirizzi IP:

| Area | IP in uscita |
| --- | --- |
| Asia |168.63.200.173, 13.75.89.159, 23.97.68.172, 13.75.94.173, 40.83.127.19, 52.175.33.254, 52.163.93.214, 52.187.65.81, 52.187.65.155, 13.76.133.155, 52.163.228.93, 52.163.230.166 |
| Australia |13.75.153.66, 104.210.89.222, 104.210.89.244, 13.75.149.4, 104.210.91.55, 104.210.90.241, 13.73.115.153, 40.115.78.70, 40.115.78.237, 13.73.114.207, 13.77.3.139, 13.70.159.205 |
| Canada |52.233.29.92, 52.228.39.241, 52.228.39.244, 52.232.128.155, 52.229.120.45, 52.229.126.25 |
| Europa |13.79.173.49, 52.169.218.253, 52.169.220.174, 40.113.12.95, 52.178.165.215, 52.178.166.21, 13.95.155.53, 52.174.54.218, 52.174.49.6, 40.68.222.65, 40.68.209.23, 13.95.147.65 |
| India |52.172.157.194, 52.172.184.192, 52.172.191.194, 52.172.154.168, 52.172.186.159, 52.172.185.79, 52.172.9.47, 52.172.49.43, 52.172.51.140, 52.172.50.24, 52.172.55.231, 52.172.52.0 |
| Giappone |13.71.146.140, 13.78.84.187, 13.78.62.130, 13.71.158.3, 13.73.4.207, 13.71.158.120, 40.74.140.173, 40.74.81.13, 40.74.85.215, 40.74.140.4, 104.214.137.243, 138.91.26.45 |
| Stati Uniti |137.135.106.54, 40.117.99.79, 40.117.100.228, 13.92.98.111, 40.121.91.41, 40.114.82.191, 52.160.90.237, 138.91.188.137, 13.91.252.184, 52.160.92.112, 40.118.244.241, 40.118.241.243 |

### <a name="services"></a>Servizi
Le chiamate effettuate da un'API connessa attraverso (ad esempio l'API SQL o l'API SharePoint) proverranno dall'indirizzo IP specificato di seguito:

| Area | IP in uscita |
| --- | --- |
| Asia |52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124 |
| Australia |13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35 |
| Canada |52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| Europa |52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| India |52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| Giappone |104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| Stati Uniti |104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Stati Uniti (accesso anticipato) |52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

Ad esempio, se è necessario autorizzare gli indirizzi IP per il database SQL di Azure, è necessario usare questi indirizzi.

La tabella seguente elenca i servizio a cui si connette Microsoft Flow. Assicurarsi che nessuno di questi servizi risulti bloccato nella rete corrente.

Domini | Protocolli | Utilizzo
--------|  ---------| -----
management.azure.com|https|Accesso ad Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Accesso ad Active Directory Authentication Library (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Accesso all'API Graph di Azure AD per recuperare informazioni sull'utente, ad esempio la foto del profilo.
*.azure-apim.net|https|Accesso al runtime per i connettori.
*.flow.microsoft.com|https|Accesso al sito di Microsoft Flow.
*.powerapps.com|https|Accesso al sito PowerApps.
psux.azureedge.net|https|Accesso alla rete CDN di Microsoft Flow.
nps.onyx.azure.net|https|Accesso a Punteggio di promozione della rete (NPS, Net Promoter Score).

