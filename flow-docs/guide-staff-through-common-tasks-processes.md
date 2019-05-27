---
title: Creare una logica di business personalizzata tramite i processi con PowerApps | MicrosoftDocs
description: Informazioni sui diversi tipi di logica di business che è possibile usare nell'app
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5e123fa2abc8955d90fad2c9b09da76e449bf4b1
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460324"
---
# <a name="create-custom-business-logic-through-processes"></a>Creare una logica di business personalizzata tramite i processi

La definizione e l'applicazione di processi aziendali coerenti sono una delle ragioni principali per cui vengono usate le app basate su modello. Processi coerenti consentono di assicurarsi che gli utenti che usano il sistema possano concentrarsi sul proprio lavoro e non sull'esecuzione di un set di passaggi manuali. I processi possono essere semplici o complessi e possono cambiare nel tempo.  
  
PowerApps include diversi tipi di processi, ognuno progettato per uno scopo diverso:  
  
-   Processi aziendali  
  
-   Flussi di attività per dispositivi mobili  
  
-   Flussi di lavoro  
  
-   Azioni  
  
 Analogamente ai processi, è anche possibile creare regole di business ed elementi consigliati. Per altre informazioni, vedere [Creare elementi consigliati e regole di business per applicare la logica in un modulo](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  L'uso dei processi può modificare i requisiti di licenza per PowerApps e i flussi. Per altre informazioni, vedere [Requisiti di licenza per entità](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Quando usare i processi aziendali  
 Usare un processo aziendale quando si vuole che il personale attraversi le stesse fasi e segua gli stessi passaggi per interagire con un cliente. Ad esempio, usare un processo aziendale se si vuole che tutto il personale gestisca le richieste di servizio dei clienti nello stesso modo oppure per richiedere al personale di ottenere l'approvazione per una fattura prima di inviare un ordine.  
  
 L'ambiente include diversi processi aziendali pronti all'uso per attività di vendita, assistenza e marketing comuni che è possibile usare apportando piccole modifiche o nessuna modifica. In alternativa, è possibile creare un nuovo processo aziendale. Vedere l'argomento seguente per altre informazioni sui processi aziendali:  
  
-   [Creare un processo aziendale](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Quando usare i flussi di lavoro  
 Usare i flussi di lavoro per automatizzare i processi aziendali. Poiché i flussi di lavoro vengono in genere avviati da eventi di sistema, l'utente non deve essere necessariamente a conoscenza della loro esecuzione. I flussi di lavoro che operano in background sono "asincroni". È anche possibile configurare i flussi di lavoro in modo che vengano avviati manualmente dagli utenti quando si vuole automatizzare attività comuni, ad esempio l'invio automatico di un messaggio di posta elettronica di conferma a un cliente quando viene inviato un ordine. I flussi di lavoro che operano in tempo reale sono "sincroni". Per altre informazioni sui flussi di lavoro, vedere [Processi del flusso di lavoro](workflow-processes.md).  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Quando usare le azioni  
 Usare le azioni quando si vuole automatizzare una serie di comandi nel sistema. Le azioni espandono il vocabolario disponibile per gli sviluppatori per esprimere i processi aziendali. Un'azione usa i verbi principali come Crea, Aggiorna, Elimina e Assegna forniti dal sistema per creare verbi più espressivi come Approva, Riassegna, Indirizza o Pianifica. Se viene modificata la definizione di un processo aziendale, un utente che non è uno sviluppatore può modificare l'azione in modo che non sia necessario modificare il codice.  Per altre informazioni sulle azioni, vedere [Azioni](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Quando usare Microsoft Flow  
 Usare Microsoft Flow quando è necessario creare flussi di lavoro automatizzati che eseguano azioni tra l'ambiente e l'app o il servizio preferito, ad esempio Dynamics 365, Twitter, Dropbox, servizi di Google, Office 365 e SharePoint. È possibile attivare un flusso in base a un'azione specifica oppure richiamarlo dall'interno dell'app. Altre informazioni: [Usare Microsoft Flow per automatizzare i processi tra i servizi](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Dove è possibile creare i processi?  
 Esistono due percorsi per passare ai processi:  
  
- Aprire [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e passare a **Componenti > Processi.** Questo percorso offre un accesso utile quando si stanno eseguendo altre personalizzazioni negli strumenti di personalizzazione.  

- **[Impostazioni](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Processi.** Questo percorso consente di usare le visualizzazioni definite per l'entità Processo, incluse eventuali visualizzazioni personalizzate.  
  
 I singoli processi aziendali possono essere modificati anche usando il pulsante **Modifica processo** nella barra dei comandi del modulo in cui è attivo il processo aziendale.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Chi può creare i processi?  
 Solo gli utenti con il ruolo di sicurezza Amministratore di sistema, Addetto personalizzazione sistema o Responsabile aziendale possono creare processi che si applicano all'intero ambiente. Gli utenti con altri ruoli possono creare processi con livello di accesso limitato. Ad esempio, gli utenti con il livello di accesso Utente possono creare flussi di lavoro per un uso personale con record di cui sono proprietari.  
  
 La tabella seguente mostra il livello di accesso dei processi in base ai ruoli di sicurezza predefiniti.  
  
|||  
|-|-|  
|**Ruolo di sicurezza**|**Livello di accesso**|  
|Responsabile aziendale|Organizzazione|  
|Amministratore di sistema|Organizzazione|  
|Addetto personalizzazione sistema|Organizzazione|  
|Vicepresidente Marketing|Business Unit padre-figlio|  
|Vicepresidente Vendite|Business Unit padre-figlio|  
|Gestione servizi|Business Unit|  
|Responsabile Marketing|Business Unit|  
|Direttore commerciale|Business Unit|  
|Responsabile pianificazione|Business Unit|  
|Rappresentante del servizio clienti|Utente|  
|Esperto Marketing|Utente|  
|Venditore|Utente|  
|Addetto pianificazione|Utente|  
  
> [!NOTE]
>  Sebbene possano creare processi aziendali, flussi di lavoro in tempo reale o processi di azione, gli utenti devono avere i privilegi **Attiva processi aziendali** o **Attiva processi in tempo reale** per poterli attivare.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Altre informazioni sui flussi di lavoro e le azioni  
 I processi possono controllare le condizioni, applicare la logica di salto condizionato ed eseguire azioni. Queste azioni vengono eseguite in una serie di passaggi. La tabella seguente descrive i passaggi disponibili nei processi del flusso di lavoro e delle azioni. Per informazioni dettagliate vedere gli argomenti relativi a ogni tipo di processo.  
  
|Passaggio|Tipo di processo|Descrizione|  
|----------|------------------|-----------------|  
|**Fase**|Flusso di lavoro, Azione|Le fasi descrivono la logica del flusso di lavoro e ne semplificano la lettura. Tuttavia, le fasi non influenzano la logica o il comportamento dei flussi di lavoro. Se un processo include fasi, tutti i passaggi del processo devono essere contenuti in una fase.|  
|**Condizione controllo**|Flusso di lavoro, Azione|Un'istruzione logica "if-\<condizione> then".<br /><br /> È possibile controllare i valori del record su cui viene eseguito il flusso di lavoro, tutti i record collegati al record in una relazione N:1 o tutti i record creati dai passaggi precedenti. In base a questi valori è possibile definire passaggi aggiuntivi quando la condizione è `true`.|  
|**Ramo condizionale**|Flusso di lavoro, Azione|Un'istruzione logica "else-if-then", l'editor usa il testo “Otherwise, if \<condizione> then:”<br /><br /> Selezionare una condizione di controllo definita in precedenza e sarà possibile aggiungere un ramo condizionale per definire ulteriori passaggi quando la condizione di controllo restituisce `false`.|  
|**Azione predefinita**|Flusso di lavoro, Azione|Un'istruzione logica "else". L'editor usa il testo “Otherwise:”<br /><br /> Selezionare una condizione di controllo, un ramo condizionale, una condizione di attesa o un ramo di attesa parallela definito in precedenza e sarà possibile usare un'azione predefinita per definire i passaggi per tutti i casi che non soddisfano i criteri definiti negli elementi condizione e ramo.|  
|**Condizione di attesa**|Solo flusso di lavoro in background|Abilita un flusso di lavoro in background che viene sospeso fino a quando non vengono soddisfatti i criteri definiti dalla condizione. Il flusso di lavoro viene riavviato automaticamente quando vengono soddisfatti i criteri della condizione di attesa.|  
|**Ramo di attesa parallela**|Solo flusso di lavoro in background|Definisce una condizione di attesa alternativa per un flusso di lavoro in background con un set di passaggi aggiuntivi che vengono eseguiti solo quando viene soddisfatto il criterio iniziale. È possibile usare i rami di attesa parallela per creare limiti di tempo nella logica del flusso di lavoro. Essi impediscono che il flusso di lavoro rimanga in attesa in modo indefinito fino a quando non vengono soddisfatti i criteri definiti in una condizione di attesa.|  
|**Assegna valore**|Azione|Imposta un valore su una variabile o un parametro di output nel processo.|  
|**Crea record**|Flusso di lavoro, Azione|Crea un nuovo record per un'entità e assegna i valori agli attributi.|  
|**Aggiorna record**|Flusso di lavoro, Azione|È possibile aggiornare il record su cui viene eseguito il flusso di lavoro, tutti i record collegati al record in una relazione N:1 o tutti i record creati dai passaggi precedenti.|  
|**Assegna record**|Flusso di lavoro, Azione|È possibile assegnare il record su cui viene eseguito il flusso di lavoro, tutti i record collegati al record con una relazione N:1 o tutti i record creati dai passaggi precedenti.|  
|**Invia messaggio**|Flusso di lavoro, Azione|Invia un messaggio di posta elettronica. È possibile scegliere di creare un nuovo messaggio di posta elettronica o usare un modello di messaggio di posta elettronica configurato per l'entità del record su cui viene eseguito il flusso di lavoro o qualsiasi entità con una relazione N:1 con l'entità o l'entità per qualsiasi record creato dai passaggi precedenti.|  
|**Avvia flusso di lavoro figlio**|Flusso di lavoro, Azione|Avvia un processo del flusso di lavoro che è stato configurato come flusso di lavoro figlio.|  
|**Cambia stato**|Flusso di lavoro, Azione|Modifica lo stato del record su cui viene eseguito il processo, tutti i record collegati al record in una relazione N:1 o tutti i record creati dai passaggi precedenti.|  
|**Interrompi flusso di lavoro**|Flusso di lavoro, Azione|Interrompe il flusso di lavoro o l'azione corrente. È possibile impostare lo stato **Riuscito** o **Annullato** e specificare un messaggio di stato.|  
|**Passaggio personalizzato**|Flusso di lavoro, Azione|Offre le estensioni agli elementi logici disponibili per impostazione predefinita. I passaggi possono includere condizioni, azioni, altri passaggi o una combinazione di questi elementi. Gli sviluppatori possono creare passaggi del flusso di lavoro personalizzati. Per impostazione predefinita, non sono disponibili passaggi personalizzati.|

Per altre informazioni per gli sviluppatori, vedere l'argomento della guida per sviluppatori [Automate your business processes in Customer Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/developer/automate-business-processes-customer-engagement
) (Automatizzare i processi aziendali in Customer Engagement).
  

