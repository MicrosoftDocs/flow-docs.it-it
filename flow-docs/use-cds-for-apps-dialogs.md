---
title: Usare Common Data Service finestre di dialogo per i processi guidati (deprecato) | MicrosoftDocs
description: I dialoghi sono i processi sincroni o interattivi che raccolgono ed elaborano le informazioni usando script step-by-Step per indirizzare gli utenti attraverso un processo
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
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
ms.openlocfilehash: 05f0b9b72f2f9e2d7f02356ec40eeb520214a0cb
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548751"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Usare Common Data Service finestre di dialogo per i processi guidati (deprecato)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Le [finestre di dialogo sono deprecate](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). È necessario sostituire i dialoghi con i flussi del processo di business o le app Canvas. Altre informazioni: [sostituire i dialoghi con i flussi del processo di business o le app Canvas](replace-dialogs.md) 

I dialoghi sono processi sincroni o interattivi in Common Data Service che raccolgono ed elaborano le informazioni tramite script step-by-Step per indirizzare gli utenti attraverso un processo. È ad esempio possibile creare finestre di dialogo che fungano da guida per i rappresentanti del servizio per la risoluzione dei casi e l'escalation dei case. Analogamente, è possibile creare finestre di dialogo per la standardizzazione dei processi di vendita, come la qualificazione dell'opportunità e l'assegnazione di punteggi.

## <a name="differences-between-workflows-and-dialogs"></a>Differenze tra flussi di lavoro e finestre di dialogo

Nella tabella seguente vengono fornite informazioni sulle differenze tra Common Data Service flussi di lavoro e le finestre di dialogo.  


| flussi     |    Finestre      |
|---------------|--------------|
|                                                                                                  Può essere avviato da un utente o può essere automatizzato.                                                                                                   |                                                                                          Deve essere avviato da un utente.                                                                                          |
|                                  Sono processi asincroni o in tempo reale e non richiedono l'esecuzione dell'input utente fino al completamento. I processi asincroni vengono eseguiti in background, mentre i processi in tempo reale vengono eseguiti immediatamente.                                   | Sono processi in tempo reale che richiedono l'esecuzione dell'input utente fino al completamento. Quando si eseguono questi processi, viene visualizzata un'interfaccia simile a una procedura guidata, in modo da poter effettuare le selezioni appropriate per eseguire i processi. |
|                                                    L'entità che archivia i dettagli relativi a un flusso di lavoro asincrono in esecuzione viene `AsyncOperation` mentre viene utilizzata una `Process` per un flusso di lavoro in tempo reale.                                                     |                                                       L'entità che archivia le informazioni generate da una finestra di dialogo in esecuzione è l'entità `ProcessSession`.                                                       |
|                  I trigger sono supportati per i flussi di lavoro. Per un elenco dei trigger supportati, vedere [tipi, trigger ed entità supportati per i processi](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   I trigger non sono supportati per le finestre di dialogo.                                                                                    |
  
### <a name="see-also"></a>Vedere anche
[Sostituisci finestre di dialogo con flussi di processi aziendali o app Canvas](replace-dialogs.md)
