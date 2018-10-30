---
title: Usare le interazioni di CDS per le app per le procedure guidate (deprecato) | MicrosoftDocs
description: Le interazioni sono i processi sincroni o interattivi che raccolgono ed elaborano le informazioni usando script dettagliati per indirizzare gli utenti in un processo
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8b2e87bdb9aed63e9f180d446349779cd37c25c
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689664"
---
# <a name="use-cds-for-apps-dialogs-for-guided-processes-deprecated"></a>Usare le interazioni di CDS per le app per le procedure guidate (deprecato)

[Le interazioni sono deprecate](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Sostituire le interazioni con processi aziendali o app canvas. Altre informazioni: [Sostituire le interazioni con processi aziendali o app canvas](replace-dialogs.md) 

Le interazioni sono i processi sincroni o interattivi di Common Data Service (CDS) per le app che raccolgono ed elaborano le informazioni usando script dettagliati per indirizzare gli utenti in un processo. Ad esempio, è possibile creare interazioni da usare come guida per i rappresentanti del servizio clienti per la risoluzione e la riassegnazione dei casi. Analogamente, è possibile creare interazioni per standardizzare i processi di vendita, ad esempio per la qualifica opportunità e il punteggio lead. Per altre informazioni, vedere [Use dialogs for guided processes](/dynamics365/customer-engagement/developer/use-dialogs-guided-processes) (Usare le interazioni per le procedure guidate) in Dynamics 365 Customer Engagement Developer Guide (Guida per sviluppatori di Dynamics 365 Customer Engagement).

## <a name="differences-between-workflows-and-dialogs"></a>Differenze tra flussi di lavoro e interazioni

La tabella seguente offre informazioni sulle differenze tra i flussi di lavoro e le interazioni di CDS per le app.  


| Flussi di lavoro     |    Interazioni      |
|---------------|--------------|
|                                                                                                  Possono essere avviati da un utente o possono essere automatizzati.                                                                                                   |                                                                                          Devono essere avviati da un utente.                                                                                          |
|                                  Sono processi asincroni o in tempo reale e non richiedono l'input dell'utente per completare l'esecuzione. I processi asincroni vengono eseguiti in background mentre i processi in tempo reale vengono eseguiti immediatamente.                                   | Sono processi in tempo reale che richiedono l'input dell'utente per completare l'esecuzione. Quando vengono eseguiti questi processi, viene visualizzata un'interfaccia simile a una procedura guidata che consente di effettuare le selezioni appropriate per eseguire i processi. |
|                                                    Per la memorizzazione dei dettagli di un flusso di lavoro asincrono in esecuzione viene usata l'entità `AsyncOperation`, mentre per un flusso di lavoro in tempo reale viene usata `Process`.                                                     |                                                       Per la memorizzazione delle informazioni generate da un'interazione in esecuzione viene usata l'entità `ProcessSession`.                                                       |
|                  I trigger sono supportati per i flussi di lavoro. Per un elenco dei trigger supportati, vedere [Supported Types, Triggers, and Entities for Processes](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes) (Tipi, trigger ed entità supportati per i processi).                   |                                                                                   I trigger non sono supportati per le interazioni.                                                                                    |
  
### <a name="see-also"></a>Vedere anche
[Sostituire le interazioni con processi aziendali o app canvas](replace-dialogs.md)