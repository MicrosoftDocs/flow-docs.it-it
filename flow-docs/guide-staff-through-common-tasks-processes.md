---
title: Creare una logica di business personalizzata tramite processi con PowerApps | MicrosoftDocs
description: Informazioni sui diversi tipi di logica di business che è possibile usare nell'app
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
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
ms.openlocfilehash: b3072cc5897b8a2ef5a2a92ec3a07a0e31b57898
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545337"
---
# <a name="create-custom-business-logic-through-processes"></a>Creazione di una logica di business personalizzata tramite processi
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

La definizione e l'applicazione di processi aziendali coerenti sono uno dei motivi principali per cui gli utenti usano app basate su modello. I processi coerenti contribuiscono a garantire che gli utenti che usano il sistema possano concentrarsi sul proprio lavoro e non su come ricordare di eseguire una serie di passaggi manuali. I processi possono essere semplici o complessi e possono cambiare nel tempo.  
  
PowerApps include diversi tipi di processi, ognuno dei quali è progettato per uno scopo diverso:  
  
-   Flussi del processo di business  
  
-   Flussi di attività per dispositivi mobili  
  
-   flussi  
  
-   Azioni  
  
 Analogamente ai processi, è anche possibile creare regole di business e consigli. Per altre informazioni, vedere [creare regole di business e consigli per applicare la logica in un modulo](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  L'uso dei processi può influire sui requisiti di licenza per PowerApps e flussi. Per ulteriori informazioni, vedere [requisiti di licenza](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses)per le entità. 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Quando utilizzare i flussi del processo di business  
 Utilizzare un flusso del processo di business quando si desidera che il personale si sposti nelle stesse fasi e segua gli stessi passaggi per interagire con un cliente. Utilizzare, ad esempio, un flusso del processo di business se si desidera che tutti gli utenti gestiscano le richieste del servizio clienti allo stesso modo o per richiedere al personale di ottenere l'approvazione di una fattura prima di inviare un ordine.  
  
 L'ambiente include diversi flussi di processi aziendali pronti all'uso per le attività comuni di vendita, servizio e marketing che è possibile usare con modifiche minime o non necessarie. In alternativa, è possibile crearne di personalizzati. Per ulteriori informazioni sui flussi dei processi di business, vedere l'argomento seguente:  
  
-   [Creare un flusso del processo di business](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Quando usare i flussi di lavoro  
 Usare i flussi di lavoro per automatizzare i processi aziendali dietro le quinte. I flussi di lavoro in genere vengono avviati dagli eventi di sistema in modo che l'utente non debba tenere presente che sono in esecuzione. I flussi di lavoro che operano in background sono "asincroni". I flussi di lavoro possono essere configurati anche per gli utenti per avviarli manualmente. Quando si vuole automatizzare le attività comuni, ad esempio l'invio automatico di un messaggio di posta elettronica di conferma a un cliente quando un ordine viene fornito. I flussi di lavoro che operano in tempo reale sono "sincroni". Per altre informazioni sui flussi di lavoro, vedere [processi del flusso di lavoro](workflow-processes.md)  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Quando usare le azioni  
 Usare le azioni quando si vuole automatizzare una serie di comandi nel sistema. Azioni espandere il vocabolario disponibile per gli sviluppatori per esprimere i processi aziendali. Con i verbi di base come create, Update, DELETE e Assign forniti dal sistema, un'azione usa i verbi di base per creare verbi più espressivi come approvare, inoltrare, indirizzare o pianificare. Se la definizione di un processo di business viene modificata, un utente che non è uno sviluppatore può modificare l'azione in modo che il codice non debba essere modificato.  Per ulteriori informazioni sulle azioni, vedere [azioni](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Quando usare Microsoft Flow  
 Usare Microsoft Flow quando è necessario creare flussi di lavoro automatizzati che eseguono azioni tra l'ambiente e l'app o il servizio preferito, ad esempio Dynamics 365, Twitter, Dropbox, Google Services, Office 365 e SharePoint. È possibile attivare un flusso in base a un'azione specifica o richiamare dall'interno dell'app. Altre informazioni: [usare Microsoft Flow per automatizzare i processi tra i servizi](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Dove si scelgono i processi di creazione?  
 Sono disponibili due percorsi per spostarsi tra i processi:  
  
- Aprire [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e passare a **componenti > processi.** Questo percorso fornisce un comodo accesso quando si eseguono altre operazioni di personalizzazione negli strumenti di personalizzazione.  

- **[Impostazioni](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > processi.** Questo percorso consente di usare le visualizzazioni definite per l'entità process, incluse le visualizzazioni personalizzate.  
  
 È inoltre possibile modificare i singoli flussi del processo di business utilizzando il pulsante **Modifica processo** nella barra dei comandi per il form in cui è attivo il flusso del processo di business.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Chi può creare processi?  
 Solo gli utenti con ruolo di sicurezza amministratore di sistema, System verbi o CEO-Business Manager possono creare processi applicabili all'intero ambiente. Le persone con altri ruoli possono creare processi con un livello di accesso limitato. Ad esempio, gli utenti con il livello di accesso utente possono creare flussi di lavoro per uso personale con i record di loro proprietà.  
  
 La tabella seguente mostra il livello di accesso dei processi in base ai ruoli di sicurezza predefiniti.  
  
|||  
|-|-|  
|**Ruolo di sicurezza**|**Livello di accesso**|  
|CEO-Business Manager|Organizzazione|  
|Amministratore di sistema|Organizzazione|  
|Verbi di sistema|Organizzazione|  
|Vicepresidente del marketing|Padre: business unit figlio|  
|Vicepresidente delle vendite|Padre: business unit figlio|  
|Service Manager|Business Unit|  
|Responsabile marketing|Business Unit|  
|Responsabile vendite|Business Unit|  
|Gestione pianificazione|Business Unit|  
|Rappresentante del servizio clienti|Utente|  
|Marketing professionale|Utente|  
|Venditore|Utente|  
|Scheduler|Utente|  
  
> [!NOTE]
>  Sebbene gli utenti possano creare il flusso del processo di business, il flusso di lavoro in tempo reale o i processi di azione, è necessario che i **flussi del processo di business Activate** o attivino i privilegi dei **processi in tempo reale** per attivarli.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Ulteriori informazioni sui flussi di lavoro e sulle azioni  
 I processi possono controllare le condizioni, applicare la logica di diramazione ed eseguire azioni. Queste azioni vengono eseguite in una serie di passaggi. Nella tabella seguente vengono descritti i passaggi disponibili nei processi di flusso di lavoro e di azione. Per altri dettagli, vedere gli argomenti per ogni tipo di processo.  
  
|Passo|Tipo di processo|Descrizione|  
|----------|------------------|-----------------|  
|**Fase**|Flusso di lavoro, azione|Le fasi rendono più semplice la lettura della logica del flusso di lavoro e spiegano la logica del flusso di lavoro. Tuttavia, le fasi non influiscono sulla logica o sul comportamento dei flussi di lavoro. Se un processo ha fasi, tutti i passaggi del processo devono essere contenuti in una fase.|  
|**Condizione di controllo**|Flusso di lavoro, azione|Istruzione "If-\<condition > then" logica.<br /><br /> È possibile controllare i valori per il record in cui viene eseguito il flusso di lavoro, uno dei record collegati a tale record in una relazione di N:1 o qualsiasi record creato dai passaggi precedenti. In base a questi valori, è possibile definire passaggi aggiuntivi quando la condizione viene `true`.|  
|**Ramo condizionale**|Flusso di lavoro, azione|Un'istruzione "else-if-then" logica, l'editor usa il testo "in caso contrario, se \<condizione >:"<br /><br /> Selezionare una condizione di controllo definita in precedenza ed è possibile aggiungere un ramo condizionale per definire ulteriori passaggi quando la condizione di controllo restituisce `false`.|  
|**Azione predefinita**|Flusso di lavoro, azione|Istruzione "else" logica. l'editor usa il testo "in caso contrario:"<br /><br /> Selezionare una condizione di controllo, un ramo condizionale, una condizione di attesa o un ramo di attesa parallelo definito in precedenza ed è possibile usare un'azione predefinita per definire i passaggi per tutti i casi che non corrispondono ai criteri definiti negli elementi condizione o ramo.|  
|**Condizione di attesa**|Solo flusso di lavoro in background|Consente a un flusso di lavoro in background di sospendersi fino a quando non vengono soddisfatti i criteri definiti dalla condizione. Il flusso di lavoro viene riavviato automaticamente quando i criteri nella condizione di attesa sono stati soddisfatti.|  
|**Ramo di attesa parallela**|Solo flusso di lavoro in background|Definisce una condizione di attesa alternativa per un flusso di lavoro in background con un set di passaggi aggiuntivi corrispondente che vengono eseguiti solo quando viene soddisfatto il criterio iniziale. È possibile usare i rami di attesa paralleli per creare limiti temporali nella logica del flusso di lavoro. Contribuiscono a impedire che il flusso di lavoro attenda indefinitamente fino a quando non vengono soddisfatti i criteri definiti in una condizione di attesa.|  
|**Assegna valore**|Azione|Imposta un valore su una variabile o un parametro di output nel processo.|  
|**Crea record**|Flusso di lavoro, azione|Crea un nuovo record per un'entità e assegna i valori agli attributi.|  
|**Aggiorna record**|Flusso di lavoro, azione|È possibile aggiornare il record in cui viene eseguito il flusso di lavoro, uno dei record collegati a tale record in una relazione di N:1 o qualsiasi record creato dai passaggi precedenti.|  
|**Assegna record**|Flusso di lavoro, azione|È possibile assegnare il record in cui viene eseguito il flusso di lavoro, uno dei record collegati a tale record con una relazione di N:1 o qualsiasi record creato dai passaggi precedenti.|  
|**Invia messaggio di posta elettronica**|Flusso di lavoro, azione|Invia un messaggio di posta elettronica. È possibile scegliere di creare un nuovo messaggio di posta elettronica o usare un modello di posta elettronica configurato per l'entità del record in cui viene eseguito il flusso di lavoro o per qualsiasi entità che disponga di una relazione di N:1 con l'entità o dell'entità per tutti i record creati nei passaggi precedenti.|  
|**Avvia flusso di lavoro figlio**|Flusso di lavoro, azione|Avvia un processo del flusso di lavoro che è stato configurato come un flusso di lavoro figlio.|  
|**Modifica stato**|Flusso di lavoro, azione|Modifica lo stato del record in cui è in esecuzione il processo, di tutti i record collegati a tale record con una relazione di N:1 o di qualsiasi record creato dai passaggi precedenti.|  
|**Interrompi flusso di lavoro**|Flusso di lavoro, azione|Arresta il flusso di lavoro o l'azione corrente. È possibile impostare uno stato di operazione **riuscita** o **annullata** e specificare un messaggio di stato.|  
|**Passaggio personalizzato**|Flusso di lavoro, azione|Fornisce le estensioni agli elementi logici disponibili per impostazione predefinita. I passaggi possono includere condizioni, azioni, altri passaggi o una combinazione di questi elementi. Gli sviluppatori possono creare passaggi personalizzati del flusso di lavoro. Per impostazione predefinita, non sono disponibili passaggi personalizzati.|

  

