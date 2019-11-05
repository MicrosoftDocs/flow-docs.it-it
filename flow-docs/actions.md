---
title: Usare le azioni | MicrosoftDocs
description: Con le azioni è possibile eseguire operazioni, ad esempio creare, aggiornare, eliminare, assegnare o eseguire un'azione. Internamente, un'azione crea un messaggio personalizzato
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: eb4fa4040611241dd2bd81706736738ad6774d38
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544600"
---
# <a name="use-actions"></a>Usare le azioni
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Le azioni aprono una gamma di possibilità per comporre la logica di business. Con le azioni è possibile eseguire operazioni, ad esempio creare, aggiornare, eliminare, assegnare o eseguire un'azione. Internamente, un'azione crea un messaggio personalizzato. Gli sviluppatori fanno riferimento a queste azioni come "messaggi". Ognuno di questi messaggi è basato sulle azioni eseguite su un record di entità. Se l'obiettivo di un processo è creare un record, aggiornarlo e quindi assegnarlo, sono disponibili tre passaggi distinti. Ogni passaggio è definito dalle funzionalità dell'entità, non necessariamente dal processo di business.  
  
Le azioni consentono di definire un singolo verbo o messaggio che corrisponde a un'operazione che è necessario eseguire per l'azienda. Questi nuovi messaggi sono basati su un processo o un comportamento anziché su ciò che può essere eseguito con un'entità. Questi messaggi possono corrispondere a verbi come l'escalation, la conversione, la pianificazione, la route o l'approvazione, a prescindere dalla necessità. L'aggiunta di questi verbi consente di fornire un vocabolario più completo per definire in modo fluente i processi aziendali. È possibile applicare questo vocabolario più completo da client o integrazioni anziché dover scrivere l'azione all'interno dei client. Questo consente anche di semplificare la gestione e la registrazione dell'esito positivo o negativo dell'intera azione come una singola unità.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Messaggi configurabili  
 Una volta che un'azione è stata definita e attivata, uno sviluppatore può utilizzare tale messaggio come uno qualsiasi degli altri messaggi forniti dalla piattaforma. Tuttavia, una differenza significativa è che ora un utente che non è uno sviluppatore può applicare modifiche alle operazioni da eseguire quando viene usato il messaggio. È possibile configurare l'azione per modificare i passaggi durante la modifica dei processi aziendali. Non è necessario modificare il codice personalizzato che usa il messaggio finché gli argomenti del processo non cambiano.  
  
 I processi e i plug-in del flusso di lavoro continuano a offrire funzionalità simili per la definizione dell'automazione. I processi del flusso di lavoro offrono comunque la possibilità per un non sviluppatore di applicare le modifiche. Ma la differenza consiste nel modo in cui i processi di business vengono composti e in che modo uno sviluppatore può scrivere il proprio codice. Un'azione è un messaggio che opera sullo stesso livello dei messaggi forniti dalla piattaforma. Gli sviluppatori possono registrare i plug-in per le azioni.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Messaggi globali 
 
 A differenza di Common Data Service flussi di lavoro o [plug-](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in)in, un'azione non deve essere associata a un'entità specifica. È possibile definire azioni "globali" che possono essere chiamate autonomamente.

## <a name="next-steps"></a>Passaggi successivi

[Creare un'azione personalizzata](create-actions.md)  
  

