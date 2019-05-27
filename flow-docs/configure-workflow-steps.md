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
ms.openlocfilehash: 9ebdb1eddaea1f2fd7918c968879f5da37c287fe
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456155"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurare le fasi e i passaggi del flusso di lavoro

Quando si progettano i flussi di lavoro si ha la possibilità di inserire la logica che si vuole eseguire in fasi e passaggi.  
  
 **Fasi**  
 Le fasi descrivono la logica del flusso di lavoro e ne semplificano la lettura. Tuttavia, le fasi non influenzano la logica o il comportamento dei flussi di lavoro. Se un processo include fasi, tutti i passaggi all'interno del processo devono essere contenuti in una fase.  
  
 **Passaggi**  
 I passaggi sono un'unità della logica di business all'interno di un flusso di lavoro. I passaggi possono includere condizioni, azioni, altri passaggi o una combinazione di questi elementi.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Azioni che possono essere eseguite dai processi del flusso di lavoro  

 I processi del flusso di lavoro possono eseguire le azioni elencate nella tabella seguente.  
  
|Azione|Descrizione|  
|------------|-----------------|  
|**Crea record**|Crea un nuovo record per un'entità e assegna i valori selezionati agli attributi.|  
|**Aggiorna record**|È possibile aggiornare il record su cui viene eseguito il flusso di lavoro, tutti i record collegati al record in una relazione N:1 o tutti i record creati dai passaggi precedenti.|  
|**Assegna record**|È possibile assegnare il record su cui viene eseguito il flusso di lavoro, tutti i record collegati al record con una relazione N:1 o tutti i record creati dai passaggi precedenti.|  
|**Invia messaggio**|Invia un messaggio di posta elettronica. È possibile scegliere di creare un nuovo messaggio di posta elettronica o usare un modello di messaggio di posta elettronica configurato per l'entità del record su cui viene eseguito il flusso di lavoro o qualsiasi entità con una relazione N:1 con l'entità o l'entità per qualsiasi record creato dai passaggi precedenti.|  
|**Avvia flusso di lavoro figlio**|Avvia un processo del flusso di lavoro che è stato configurato come flusso di lavoro figlio.|  
|**Cambia stato**|Modifica lo stato del record su cui viene eseguito il processo, tutti i record collegati al record in una relazione N:1 o tutti i record creati dai passaggi precedenti.|  
|**Interrompi flusso di lavoro**|Interrompe il flusso di lavoro corrente. È possibile impostare lo stato **Riuscito** o **Annullato** e specificare un messaggio di stato.<br /><br /> Quando i flussi di lavoro in tempo reale vengono configurati per un evento, l'interruzione di un flusso di lavoro con stato Annullato impedisce il completamento dell'azione dell'evento. Per altre informazioni, vedere [Uso dei flussi di lavoro in tempo reale](configure-workflow-steps.md#BKMK_SynchronousWorkflows).|  
|**Passaggio personalizzato**|Gli sviluppatori possono creare passaggi del flusso di lavoro personalizzati che definiscono le azioni. Per impostazione predefinita, non sono disponibili passaggi personalizzati.|  
  
### <a name="setting-record-values"></a>Impostazione dei valori del record  

 Quando si crea un record è possibile impostare i valori per il record. Quando si aggiorna un record è possibile impostare, aggiungere, aumentare, ridurre, moltiplicare o cancellare i valori.  
  
 Quando si seleziona **Imposta proprietà** viene aperta una finestra di dialogo che visualizza il modulo predefinito per l'entità.  
  
 Nella parte inferiore della finestra di dialogo è possibile visualizzare un elenco di campi aggiuntivi non presenti nel modulo.  
  
 Per qualsiasi campo, è possibile impostare un valore statico che verrà impostato dal flusso di lavoro.  
  
 Nella parte destra della finestra di dialogo la funzionalità **Informazioni e selezione rapida** offre la possibilità di impostare o aggiungere valori dinamici dal contesto del record corrente. I valori includono i valori di record correlati che sono accessibili dalle relazioni N:1 (molti-a-uno) per l'entità.  
  
 Le opzioni disponibili in **Informazioni e selezione rapida** variano a seconda del campo selezionato nel modulo. Quando si imposta un valore dinamico, viene visualizzato un segnaposto giallo chiamato 'campo dati dinamico' che mostra la posizione in cui verranno inseriti i dati dinamici. Se si vuole rimuovere il valore, selezionare il campo dati dinamico ed eliminarlo. Per i campi di testo, è possibile usare una combinazione di dati statici e dinamici.  
  
 Con i valori dinamici non è possibile avere la certezza che un campo o l'entità correlata includa il valore che si vuole impostare. È possibile impostare un numero di campi da provare, impostare il valore e ordinarli usando le frecce verdi. Se il primo campo non include dati, verrà provato il secondo campo e così via. Se nessuno dei campi include dati, è possibile specificare un valore predefinito da usare.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Impostazione delle condizioni per le azioni del flusso di lavoro  

 Le azioni che verranno applicate dipendono spesso dalle condizioni. I processi del flusso di lavoro offrono diversi modi per impostare le condizioni e creare la logica di salto condizionata per ottenere i risultati desiderati. È possibile controllare i valori del record in cui viene eseguito il processo del flusso di lavoro, tutti i record collegati al record con una relazione N:1 o i valori all'interno del processo stesso  
  
|Tipo di condizione|Descrizione|  
|--------------------|-----------------|  
|**Condizione controllo**|Un'istruzione logica "if-\<condizione> then".<br /><br /> È possibile controllare i valori correnti del record su cui viene eseguito il flusso di lavoro, tutti i record collegati al record in una relazione N:1 o tutti i record creati dai passaggi precedenti. In base a questi valori è possibile definire passaggi aggiuntivi quando la condizione ha valore true.<br /><br /> Nell'istruzione if-\<condition> then" è possibile usare gli operatori seguenti: **Uguale a**, **Diverso da**, **Contiene dati**, **Non contiene dati**, **Inferiore a** e **Non inferiore a**. **Nota**:  **Inferiore a** e **Non inferiore a** sono operatori gerarchici. Possono essere usati solo nelle entità con una relazione gerarchica definita. Se si tenta di usare questi operatori nelle entità per cui non è stata definita una relazione gerarchica, viene visualizzato il messaggio di errore: "Stai usando un operatore gerarchico su un'entità che non ha alcuna relazione gerarchica definita. Rendi gerarchica l'entità (contrassegnando una relazione come gerarchica) o utilizza un altro operatore". Per altre informazioni sulle relazioni gerarchiche, vedere [Define and query hierarchically related data](/powerapps/maker/common-data-service/define-query-hierarchical-data) (Definire ed eseguire query nei dati correlati in modo gerarchico). Lo screenshot che segue la tabella è un esempio di definizione del processo del flusso di lavoro che usa gli operatori gerarchici **Inferiore a** e **Non inferiore a**.|  
|**Ramo condizionale**|Un'istruzione logica "else-if-then", l'editor usa il testo “Otherwise, if \<condizione> then:”<br /><br /> Selezionare una condizione di controllo definita in precedenza e sarà possibile aggiungere un ramo condizionale per definire ulteriori passaggi quando la condizione di controllo restituisce false.|  
|**Azione predefinita**|Un'istruzione logica "else". L'editor usa il testo “Otherwise:”<br /><br /> Selezionare una condizione di controllo, un ramo condizionale, una condizione di attesa o un ramo di attesa parallela definito in precedenza e sarà possibile usare un'azione predefinita per definire i passaggi per tutti i casi che non soddisfano i criteri definiti negli elementi condizione e ramo.|  
|**Condizione di attesa**|Abilita un flusso di lavoro in background che viene sospeso fino a quando non vengono soddisfatti i criteri definiti dalla condizione. Il flusso di lavoro viene riavviato automaticamente quando vengono soddisfatti i criteri della condizione di attesa.<br /><br /> I flussi di lavoro in tempo reale non possono usare le condizioni di attesa.|  
|**Ramo di attesa parallela**|Definisce una condizione di attesa alternativa per un flusso di lavoro in background con un set di passaggi aggiuntivi che vengono eseguiti solo quando viene soddisfatto il criterio iniziale. È possibile usare i rami di attesa parallela per creare limiti di tempo nella logica del flusso di lavoro. Essi impediscono che il flusso di lavoro rimanga in attesa in modo indefinito fino a quando non vengono soddisfatti i criteri definiti in una condizione di attesa.|  
|**Passaggio personalizzato**|Gli sviluppatori possono creare passaggi del flusso di lavoro personalizzati che definiscono le condizioni. Per impostazione predefinita, non sono disponibili passaggi personalizzati.|  
  
 Lo screenshot seguente contiene un esempio di definizione del processo del flusso di lavoro con gli operatori **Inferiore a** e **Non inferiore a**. Nell'esempio vengono applicati due sconti diversi a due gruppi di account. In **Aggiungi passaggio** è stata selezionata la **Condizione controllo** per specificare la condizione **if-then** contenente gli operatori **Inferiore a** o **Non inferiore a**. La prima condizione **if-then** si applica a tutti gli account che sono **Inferiore a** rispetto all'account Alpine Ski House. Questi account ricevono uno sconto del 10% sulle merci e i servizi acquistati. La seconda condizione **if-then** si applica a tutti gli account che sono **Non inferiore a** rispetto all'account Alpine Ski House che ricevono uno sconto del 5%. È stata quindi selezionata l'opzione **Aggiorna record** per definire l'azione da eseguire in base alla condizione.  
  
 ![Processo del flusso di lavoro con operatori Inferiore a&#47;Non inferiore a](media/wfp-under-not-under.PNG "Processo del flusso di lavoro con operatori Inferiore a/Non inferiore a")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Uso dei flussi di lavoro in tempo reale  

 È possibile configurare flussi di lavoro in tempo reale, ma è necessario usarli con attenzione. I flussi di lavoro in background sono solitamente consigliati poiché consentono al sistema di applicarli non appena sono disponibili le risorse del server. Ciò consente di equilibrare il lavoro del server e garantire prestazioni ottimali per gli utenti che usano il sistema. Lo svantaggio è rappresentato dal fatto che le azioni definite dai flussi di lavoro in background non sono immediate. Non è possibile prevedere quando verranno applicate, ma in genere richiedono alcuni minuti. Ciò non rappresenta un problema per la maggior parte dei processi aziendali automatizzati poiché gli utenti che usano il sistema non devono essere a conoscenza dell'esecuzione del processo.  
  
 Usare i flussi di lavoro in tempo reale quando per un processo aziendale è necessario che alcuni utenti visualizzino immediatamente i risultati oppure se si vuole avere la possibilità di annullare un'operazione. Ad esempio, è possibile impostare alcuni valori predefiniti per un record la prima volta che viene salvato oppure assicurarsi che alcuni record non vengano eliminati.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversione tra flussi di lavoro in tempo reale e flussi di lavoro in background  

 È possibile convertire un flusso di lavoro in tempo reale in flusso di lavoro in background scegliendo **Converti in un flusso di lavoro in background** sulla barra degli strumenti.  
  
 È possibile convertire un flusso di lavoro in background in flusso di lavoro in tempo reale scegliendo **Converti in un flusso di lavoro in tempo reale** sulla barra degli strumenti. Se il flusso di lavoro in background usa una condizione di attesa, il flusso non sarà valido e non sarà possibile attivarlo fino a quando non viene rimossa la condizione di attesa.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Avvio dei flussi di lavoro in tempo reale precedente o successivo alle modifiche dello stato  

 Quando si configurano le **Opzioni per processi automatici** per i flussi di lavoro in tempo reale, le opzioni **Avvia in caso di** per l'evento di modifica dello stato consentono di selezionare **Dopo** o **Prima** relativamente al momento in cui viene modificato lo stato. L'opzione predefinita è **Dopo**.  
  
 Quando si seleziona **Prima** si indica di voler applicare la logica del flusso di lavoro prima del salvataggio dei dati che modificano lo stato. Ciò consente di controllare i valori prima che venga applica un'altra logica al termine dell'operazione e di impedire l'esecuzione di ulteriore logica. È possibile ad esempio avere una logica aggiuntiva in un plug-in o un'azione del flusso di lavoro personalizzata che potrebbe avviare azioni in un altro sistema. Interrompendo l'ulteriore elaborazione è possibile evitare i casi in cui vengono influenzati i sistemi esterni. L'applicazione di flussi di lavoro in tempo reale prima dell'evento significa anche che quando l'operazione viene annullata non è necessario eseguire il rollback delle altre azioni del flusso di lavoro o del plug-in che potrebbero aver salvato dati.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Uso dell'azione Interrompi flusso di lavoro con flussi di lavoro in tempo reale  

 Quando si applica un'azione **Interrompi flusso di lavoro** in un flusso di lavoro è possibile specificare una condizione di stato che può essere **Riuscito** o **Annullato**. Impostando lo stato Annullato si impedisce l'operazione. Viene visualizzato all'utente un messaggio di errore che contiene il testo del messaggio di stato di azione interrotta con l'intestazione **Errore processo aziendale**.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Creare una logica di business personalizzata tramite i processi](guide-staff-through-common-tasks-processes.md)   
 [Panoramica dei processi del flusso di lavoro](workflow-processes.md)   
 [Monitorare e gestire i processi del flusso di lavoro](monitor-manage-processes.md)   
 [Procedure consigliate per i processi dei flussi di lavoro](best-practices-workflow-processes.md)
