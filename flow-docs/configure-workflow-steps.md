---
title: Configurare le fasi e i passaggi del flusso di lavoro in PowerApps | MicrosoftDocs
description: Informazioni su come configurare i passaggi del flusso di lavoro
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4239e939f9522b4b3a22e56dfc69275482b017a7
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547083"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurare fasi e passaggi del flusso di lavoro
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Quando si progettano i flussi di lavoro, è possibile scegliere di includere la logica che si desidera eseguire in fasi e passaggi.  
  
 **Fasi**  
 Le fasi rendono più semplice la lettura della logica del flusso di lavoro e spiegano la logica del flusso di lavoro. Tuttavia, le fasi non influiscono sulla logica o sul comportamento dei flussi di lavoro. Se un processo ha fasi, tutti i passaggi all'interno del processo devono essere contenuti in una fase.  
  
 **Passaggi**  
 I passaggi sono un'unità di logica di business all'interno di un flusso di lavoro. I passaggi possono includere condizioni, azioni, altri passaggi o una combinazione di questi elementi.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Azioni che possono essere eseguite dai processi del flusso di lavoro  

 I processi del flusso di lavoro possono eseguire le azioni elencate nella tabella seguente.  
  
|Azione|Descrizione|  
|------------|-----------------|  
|**Crea record**|Crea un nuovo record per un'entità e assegna i valori scelti per gli attributi.|  
|**Aggiorna record**|È possibile aggiornare il record in cui viene eseguito il flusso di lavoro, uno dei record collegati a tale record in una relazione di N:1 o qualsiasi record creato dai passaggi precedenti.|  
|**Assegna record**|È possibile assegnare il record in cui viene eseguito il flusso di lavoro, uno dei record collegati a tale record con una relazione di N:1 o qualsiasi record creato dai passaggi precedenti.|  
|**Invia messaggio di posta elettronica**|Invia un messaggio di posta elettronica. È possibile scegliere di creare un nuovo messaggio di posta elettronica o usare un modello di posta elettronica configurato per l'entità del record in cui viene eseguito il flusso di lavoro o per qualsiasi entità che disponga di una relazione di N:1 con l'entità o dell'entità per tutti i record creati nei passaggi precedenti.|  
|**Avvia flusso di lavoro figlio**|Avvia un processo del flusso di lavoro che è stato configurato come un flusso di lavoro figlio.|  
|**Modifica stato**|Modifica lo stato del record in cui è in esecuzione il processo, di tutti i record collegati a tale record con una relazione di N:1 o di qualsiasi record creato dai passaggi precedenti.|  
|**Interrompi flusso di lavoro**|Arresta il flusso di lavoro corrente. È possibile impostare uno stato di operazione **riuscita** o **annullata** e specificare un messaggio di stato.<br /><br /> Quando i flussi di lavoro in tempo reale sono configurati per un evento, l'arresto di un flusso di lavoro con stato annullato impedisce il completamento dell'azione dell'evento. Per ulteriori informazioni, vedere [utilizzo dei flussi di lavoro in tempo reale](configure-workflow-steps.md#BKMK_SynchronousWorkflows) .|  
|**Passaggio personalizzato**|Gli sviluppatori possono creare passaggi personalizzati del flusso di lavoro che definiscono le azioni. Per impostazione predefinita, non sono disponibili passaggi personalizzati.|  
  
### <a name="setting-record-values"></a>Impostazione dei valori dei record  

 Quando si crea un record, è possibile impostare i valori per il record. Quando si aggiorna un record, è possibile impostare i valori di Accodamento, incremento, decremento, moltiplicazione o Cancella.  
  
 Quando si seleziona **Imposta proprietà**, viene visualizzata una finestra di dialogo che mostra il modulo predefinito per l'entità.  
  
 Nella parte inferiore della finestra di dialogo è possibile visualizzare un elenco di campi aggiuntivi non presenti nel modulo.  
  
 Per qualsiasi campo, è possibile impostare un valore statico che verrà impostato dal flusso di lavoro.  
  
 Sul lato destro della finestra di dialogo il **form Assistant** consente di impostare o aggiungere valori dinamici dal contesto del record corrente. Sono inclusi i valori dei record correlati a cui è possibile accedere dalle relazioni N:1 (molti-a-uno) per l'entità.  
  
 Le opzioni disponibili nell'Assistente per il **form** dipendono dal campo selezionato nel form. Quando si imposta un valore dinamico, viene visualizzato un segnaposto giallo noto come ' Slug ' che indica dove verranno inclusi i dati dinamici. Se si vuole rimuovere il valore, è sufficiente selezionare il campo slug ed eliminarlo. Per i campi di testo, è possibile usare una combinazione di dati statici e dinamici.  
  
 Con i valori dinamici non si è certi che un campo o un'entità correlata disponga del valore che si desidera impostare. È possibile impostare un certo numero di campi per provare a impostare il valore e ordinarli in ordine usando le frecce verdi. Se il primo campo non contiene dati, il secondo campo verrà provato e così via. Se nessuno dei campi contiene dati, è possibile specificare un valore predefinito da usare.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Impostazione delle condizioni per le azioni del flusso di lavoro  

 Le azioni che verranno applicate spesso dipendono dalle condizioni. I processi del flusso di lavoro forniscono diversi modi per impostare le condizioni e creare la logica di diramazione per ottenere i risultati desiderati. È possibile controllare i valori del record in cui viene eseguito il processo del flusso di lavoro, i record collegati a tale record con una relazione di N:1 o i valori all'interno del processo stesso.  
  
|Tipo di condizione|Descrizione|  
|--------------------|-----------------|  
|**Condizione di controllo**|Istruzione "If-\<condition > then" logica.<br /><br /> È possibile controllare i valori correnti per il record in cui viene eseguito il flusso di lavoro, uno dei record collegati a tale record in una relazione di N:1 o qualsiasi record creato dai passaggi precedenti. In base a questi valori, è possibile definire passaggi aggiuntivi quando la condizione è true.<br /><br /> Nell'istruzione "If-\<condition > then" è possibile usare gli operatori seguenti: **Equals**, non **uguale**a, **contiene dati**, non **contiene dati**, **in** e **non in**. **Nota:**  Gli operatori **in** e **not under** sono operatori gerarchici. Possono essere utilizzati solo nelle entità per cui è definita una relazione gerarchica. Se si sta tentando di usare questi operatori sulle entità per le quali non è definita la relazione gerarchica, verrà visualizzato il messaggio di errore: "si sta usando un operatore gerarchico in un'entità che non dispone di una relazione gerarchica definita. Rendere l'entità gerarchica (contrassegnando una relazione come gerarchica) o usare un operatore diverso ". Per ulteriori informazioni sulle relazioni gerarchiche, vedere [definizione ed esecuzione di query su dati correlati gerarchicamente](/powerapps/maker/common-data-service/define-query-hierarchical-data). Una schermata che segue la tabella è un esempio della definizione del processo del flusso di lavoro che usa l'oggetto **in** e **non sotto** gli operatori gerarchici.|  
|**Ramo condizionale**|Un'istruzione "else-if-then" logica, l'editor usa il testo "in caso contrario, se \<condizione >:"<br /><br /> Selezionare una condizione di controllo definita in precedenza ed è possibile aggiungere un ramo condizionale per definire passaggi aggiuntivi quando la condizione di controllo restituisce false.|  
|**Azione predefinita**|Istruzione "else" logica. l'editor usa il testo "in caso contrario:"<br /><br /> Selezionare una condizione di controllo, un ramo condizionale, una condizione di attesa o un ramo di attesa parallelo definito in precedenza ed è possibile usare un'azione predefinita per definire i passaggi per tutti i case che non corrispondono ai criteri definiti negli elementi condizione o ramo.|  
|**Condizione di attesa**|Consente a un flusso di lavoro in background di sospendersi fino a quando non vengono soddisfatti i criteri definiti dalla condizione. Il flusso di lavoro viene riavviato automaticamente quando i criteri nella condizione di attesa sono stati soddisfatti.<br /><br /> I flussi di lavoro in tempo reale non possono usare condizioni di attesa.|  
|**Ramo di attesa parallela**|Definisce una condizione di attesa alternativa per un flusso di lavoro in background con un set di passaggi aggiuntivi corrispondente che vengono eseguiti solo quando viene soddisfatto il criterio iniziale. È possibile usare i rami di attesa paralleli per creare limiti temporali nella logica del flusso di lavoro. Contribuiscono a impedire che il flusso di lavoro attenda indefinitamente fino a quando non vengono soddisfatti i criteri definiti in una condizione di attesa.|  
|**Passaggio personalizzato**|Gli sviluppatori possono creare passaggi personalizzati del flusso di lavoro che definiscono le condizioni. Per impostazione predefinita, non sono disponibili passaggi personalizzati.|  
  
 Lo screenshot seguente contiene un esempio della definizione del processo del flusso di lavoro con l'oggetto **in** e **non sotto** gli operatori gerarchici. In questo esempio vengono applicati due sconti diversi a due gruppi di account. In **Aggiungi passaggio**è stata selezionata la **condizione di controllo** per specificare la condizione **if-then** contenente gli operatori **Under** o **not under** . La prima condizione **if-then** si applica a tutti gli account che si trovano **nell'** account Alpine Ski House. Questi account ricevono uno sconto del 10% sull'acquisto di servizi e buoni. La seconda condizione **if-then** si applica a tutti gli account che **non** sono inclusi nell'account Alpine Ski House e che ricevono uno sconto del 5%. Quindi, è stato selezionato **Aggiorna record** per definire l'azione da eseguire in base alla condizione.  
  
 ![Processo del flusso di&#47;lavoro con operatore under not Under](media/wfp-under-not-under.PNG "Processo del flusso di lavoro con operatori under/not Under")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Uso dei flussi di lavoro in tempo reale  

 È possibile configurare i flussi di lavoro in tempo reale, ma è consigliabile usarli con cautela. I flussi di lavoro in background sono in genere consigliati perché consentono al sistema di applicarli come risorse sul server sono disponibili. Questo consente di semplificare il lavoro svolto dal server e di mantenere le migliori prestazioni per tutti gli utenti che usano il sistema. Lo svantaggio è che le azioni definite da flussi di lavoro in background non sono immediate. Non è possibile prevedere quando verranno applicati, ma in genere saranno necessari alcuni minuti. Per la maggior parte dell'automazione dei processi aziendali questa operazione è corretta perché gli utenti che usano il sistema non devono essere consapevoli del fatto che il processo è in esecuzione.  
  
 Usare i flussi di lavoro in tempo reale quando un processo di business richiede a un utente di visualizzare immediatamente i risultati del processo o se si vuole annullare un'operazione. Ad esempio, è possibile impostare determinati valori predefiniti per un record la prima volta che viene salvato o si desidera assicurarsi che alcuni record non vengano eliminati.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversione tra flussi di lavoro in tempo reale e in background  

 È possibile modificare un flusso di lavoro in tempo reale in un flusso di lavoro in background scegliendo **Converti in un flusso di lavoro in background** sulla barra degli strumenti.  
  
 È possibile modificare un flusso di lavoro in background in un flusso di lavoro in tempo reale scegliendo **Converti in un flusso di lavoro in tempo reale** sulla barra degli strumenti. Se il flusso di lavoro in background usa una condizione di attesa, diventerà non valido e non sarà possibile attivarlo fino a quando non si rimuove la condizione di attesa.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Avvio dei flussi di lavoro in tempo reale prima o dopo le modifiche dello stato  

 Quando si configurano le **Opzioni per i processi automatici** per i flussi di lavoro in tempo reale, le opzioni di **avvio quando** per l'evento di modifica dello stato consentono di selezionare **after** o **before** quando lo stato cambia. L'opzione predefinita è **successiva**a.  
  
 Quando si seleziona **prima** di dire che si desidera che la logica nel flusso di lavoro venga applicata prima che i dati che cambiano lo stato vengano salvati. In questo modo è possibile controllare i valori prima che altra logica venga applicata dopo l'operazione e impedire l'esecuzione di un'ulteriore logica. È possibile, ad esempio, che si disponga di logica aggiuntiva in un plug-in o in un'azione personalizzata del flusso di lavoro che può avviare azioni in un altro sistema. Arrestando un'ulteriore elaborazione è possibile evitare i casi in cui sono interessati sistemi esterni. L'applicazione di flussi di lavoro in tempo reale prima di questo evento indica anche che è necessario eseguire il rollback di altre azioni del flusso di lavoro o del plug-in che potrebbero avere dati salvati quando l'operazione viene annullata.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Uso dell'azione Interrompi flusso di lavoro con flussi di lavoro in tempo reale  

 Quando si applica un'azione **Interrompi flusso di lavoro** in un flusso di lavoro, è possibile specificare una condizione di stato che può essere **completata** o **annullata**. Quando si imposta lo stato su annullato, l'operazione viene impedita. Un messaggio di errore contenente il testo del messaggio di stato Interrompi azione verrà visualizzato all'utente con l'intestazione **errore processo di business**.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Creazione di una logica di business personalizzata con processi](guide-staff-through-common-tasks-processes.md)   
 [Panoramica dei processi di flusso di lavoro](workflow-processes.md)   
 [Monitorare e gestire i processi del flusso di lavoro](monitor-manage-processes.md)   
 [Procedure consigliate per i processi del flusso di lavoro](best-practices-workflow-processes.md)
