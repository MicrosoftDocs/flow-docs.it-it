---
title: Usare le azioni | MicrosoftDocs
description: Le azioni consentono di eseguire le operazioni, ad esempio Crea, Aggiorna, Elimina, Assegna o Esegui azione. Internamente, un'azione crea un messaggio personalizzato.
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: aaa1d90368cbf513b46a939e7ea512a66b2c0a14
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688952"
---
# <a name="use-actions"></a>Usare le azioni

Le azioni offrono diverse possibilità di composizione della logica di business. Le azioni consentono di eseguire le operazioni, ad esempio Crea, Aggiorna, Elimina, Assegna o Esegui azione. Internamente, un'azione crea un messaggio personalizzato. Gli sviluppatori fanno riferimento a queste azioni come "messaggi". Ognuno di questi messaggi si basa su azioni eseguite su un record entità. Se l'obiettivo di un processo consiste nel creare un record, aggiornarlo e infine assegnarlo, l'obiettivo è diviso in tre passaggi. Ogni passaggio è definito dalle funzionalità dell'entità, non necessariamente dal processo aziendale.  
  
Le azioni offrono la possibilità di definire un singolo verbo (o messaggio) che corrisponde a un'operazione che è necessario eseguire per l'azienda. Questi nuovi messaggi sono determinati da un processo o un comportamento anziché dalle operazioni che è possibile eseguire con un'entità. I messaggi possono corrispondere a verbi come Riassegna, Converti, Pianifica, Indirizza o Approva, a seconda delle proprie esigenze. L'aggiunta di questi verbi offre un vocabolario più ricco per definire i processi aziendali. È possibile applicare questo vocabolario dai client o dalle integrazioni anziché scrivere l'azione all'interno dei client. L'operazione risulta ancora più semplice poiché è possibile gestire e registrare l'esito positivo o negativo dell'intera azione come singola unità.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Messaggi configurabili  
 Dopo aver definito e attivato un'azione, lo sviluppatore può usare il messaggio come qualsiasi altro messaggio fornito dalla piattaforma. Una differenza significativa, tuttavia, è rappresentata dal fatto che un utente che non è uno sviluppatore può apportare modifiche alle operazioni eseguite quando viene usato il messaggio. È possibile configurare l'azione per modificare i passaggi man mano che vengono modificati i processi aziendali. Se gli argomenti del processo non vengono modificati, non sarà necessario modificare il codice personalizzato che usa il messaggio.  
  
 I processi dei flussi di lavoro e i plug-in continuano a offrire funzionalità simili per la definizione dell'automazione. I processi del flusso di lavoro offrono comunque la possibilità a un utente non sviluppatore di applicare le modifiche. La differenza risiede nel modo in cui sono composti i processi aziendali e nel modo in cui uno sviluppatore può scriverne il codice. Un'azione è un messaggio che opera allo stesso livello dei messaggi forniti dalla piattaforma. Gli sviluppatori possono registrare i plug-in per le azioni.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Messaggi globali 
 
 A differenza dei flussi di lavoro di CDS per le app o dei [plug-in](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in), un'azione non deve essere associata a un'entità specifica. È possibile definire ”globali” le azioni che possono essere chiamate autonomamente.

## <a name="next-steps"></a>Passaggi successivi

[Creare un'azione personalizzata](create-actions.md)  
  

