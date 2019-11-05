---
title: Configurare azioni per i flussi di lavoro in PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
author: Mattp123
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d0b680c5c38b31b915482c435e7bc2ba83586dae
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547590"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Configurare azioni personalizzate da un flusso di lavoro
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

È possibile abilitare un'azione personalizzata da un flusso di lavoro senza scrivere codice. Altre informazioni: [richiamare azioni personalizzate da un flusso di lavoro](invoke-custom-actions-workflow-dialog.md).  
  
 È anche possibile creare un'azione in modo che uno sviluppatore possa usarla nel codice o potrebbe essere necessario modificare un'azione definita in precedenza. Analogamente ai processi del flusso di lavoro, tenere presente quanto segue:  
  
-   Specificare l'azione da eseguire.  
  
-   In quali condizioni deve essere eseguita l'azione?  
  
 
A differenza dei processi del flusso di lavoro, non è necessario impostare le opzioni seguenti:  
  
- **Inizia quando**: le azioni iniziano quando il codice chiama il messaggio generato.  
  
- **Ambito**: le azioni vengono sempre eseguite nel contesto dell'utente chiamante.  
  
- **Esegui in background**: le azioni sono sempre flussi di lavoro in tempo reale.  
  
Le azioni hanno anche elementi che non vengono elaborati dai processi del flusso di lavoro: argomenti di input e output Altre informazioni: [definizione degli argomenti del processo](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Creare un'azione  
  
> [!IMPORTANT]
>  Se si sta creando un'azione da includere come parte di una soluzione che verrà distribuita, crearla nel contesto della soluzione. Passare a **[impostazioni](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **soluzioni** e individuare la soluzione non gestita di cui questa azione sarà parte. Quindi, nella barra dei menu, selezionare **nuovo** > **processo**. In questo modo si garantisce che il prefisso di personalizzazione associato al nome dell'azione sia coerente con gli altri componenti della soluzione. Dopo aver creato l'azione, non è possibile modificare il prefisso.  
  
 Analogamente ai processi del flusso di lavoro, le azioni hanno le proprietà seguenti nella finestra di dialogo **Crea processo** .  
  
 **Nome processo**  
 Dopo aver immesso un nome per il processo, verrà creato un nome univoco rimuovendo gli spazi o i caratteri speciali dal nome del processo.  
  
 **Categoria**  
 Questa proprietà stabilisce che si tratta di un processo di azione. Non è possibile modificare questa operazione dopo aver salvato il processo.  
  
 **Entità**  
 Con i processi di azioni è possibile selezionare un'entità per fornire il contesto del flusso di lavoro come altri tipi di processi, ma è anche possibile scegliere **nessuno (globale)** . Usare questa se l'azione non richiede il contesto di un'entità specifica. Non è possibile modificare questa operazione dopo aver salvato il processo.  
  
 **Tipo**  
 Utilizzare questa proprietà per scegliere se compilare una nuova azione da zero o per iniziare da un modello esistente.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Modificare un'azione  
 È necessario disattivare i processi prima di poterli modificare.  
  
 È possibile modificare un'azione creata come parte di una soluzione non gestita o inclusa in una soluzione installata nell'organizzazione. Se la soluzione è una soluzione gestita, potrebbe non essere possibile modificarla. L'autore della soluzione è in grado di modificare le proprietà gestite in modo da non modificare l'azione installata con una soluzione gestita.  
  
 Quando un'azione viene salvata, viene generato un nome univoco in base al nome del processo. Questo nome univoco ha il prefisso di personalizzazione aggiunto dal server di pubblicazione della soluzione. Si tratta del nome del messaggio che lo sviluppatore utilizzerà nel codice.  
  
 Quando si modifica un'azione sono disponibili le opzioni seguenti:  
  
 **Nome processo**  
 Dopo la creazione del processo e il nome univoco generato dal nome del processo, è possibile modificare il nome del processo. Potrebbe essere necessario applicare una convenzione di denominazione per semplificare l'individuazione di processi specifici.  
  
 **Nome univoco**  
 Quando un'azione viene salvata, viene generato un nome univoco in base al nome del processo. Questo nome univoco ha il prefisso di personalizzazione dell'autore della soluzione aggiunto. Si tratta del nome del messaggio che lo sviluppatore utilizzerà nel codice. Non modificare questo nome univoco se il processo è stato attivato e il codice prevede di chiamare l'azione usando questo nome.  
  
> [!IMPORTANT]
>  Dopo che l'azione è stata attivata e il codice è stato scritto in modo da usare un nome univoco, il nome univoco non deve essere modificato senza modificare anche il codice che vi fa riferimento.  
  
 **Abilita rollback**  
 In genere, i processi che supportano le transazioni "annullano" o eseguono il rollback dell'intera operazione se una parte di essi non riesce. Esistono alcune eccezioni. Alcune azioni che gli sviluppatori potrebbero eseguire nel codice avviato dall'azione potrebbero non supportare le transazioni. Ad esempio, se il codice esegue azioni in altri sistemi che esulano dall'ambito della transazione. Non è possibile eseguire il rollback dell'azione eseguita in un'app. Alcuni messaggi della piattaforma non supportano le transazioni. Tuttavia, tutto ciò che è possibile fare solo con l'interfaccia utente dell'azione supporterà le transazioni. Tutte le azioni che fanno parte di un flusso di lavoro in tempo reale vengono considerate nella transazione, ma con le azioni è possibile rifiutare esplicitamente questa opzione.  
  
 È necessario consultare lo sviluppatore che utilizzerà questo messaggio per determinare se deve essere o meno nella transazione. In genere, un'azione dovrebbe essere nella transazione se le azioni eseguite dal processo di business non sono sensate, a meno che tutte siano completate correttamente. L'esempio classico è il trasferimento di fondi tra due conti bancari. Se si prelevano fondi da un account, è necessario depositarli nell'altro. In caso di esito negativo, entrambi devono avere esito negativo.  
  
> [!NOTE]
>  Non è possibile abilitare il rollback se un'azione personalizzata viene richiamata direttamente dall'interno di un flusso di lavoro. È possibile abilitare il rollback se un'azione viene attivata da un messaggio di servizi Web PowerApps.  
  
 **Attiva come**  
 Come tutti i processi, è possibile attivare il processo come modello e usarlo come punto di partenza avanzato per i processi che seguono un modello simile.  
  
 **Definire gli argomenti del processo**  
 In quest'area verranno specificati i dati che l'azione prevede di avviare e i dati che verranno passati dall'azione. Altre informazioni: [definizione degli argomenti del processo](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Aggiungere fasi, condizioni e azioni**  
 Analogamente ad altri processi, è possibile specificare quali azioni eseguire e quando eseguirle. Altre informazioni: [aggiungere fasi, condizioni e azioni](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Definire gli argomenti del processo  
 Quando uno sviluppatore usa un messaggio, può iniziare con alcuni dati che possono passare al messaggio. Ad esempio, per creare un nuovo record del case, potrebbe essere presente il valore del titolo del case che viene passato come argomento di input.  
  
 Al termine del messaggio, lo sviluppatore potrebbe dover passare alcuni dati che sono stati modificati o generati dal messaggio a un'altra operazione nel codice. Questi dati sono l'argomento di output.  
  
 Gli argomenti di input e di output devono avere un nome, un tipo e alcune informazioni sul fatto che l'argomento sia sempre obbligatorio. È anche possibile fornire una descrizione.  
  
 Il nome del messaggio e le informazioni su tutti gli argomenti del processo rappresentano la "firma" per il messaggio. Dopo che un'azione è stata attivata e viene utilizzata nel codice, la firma non deve essere modificata. Se questa firma viene modificata, il codice che utilizza il messaggio avrà esito negativo. L'unica eccezione a questa operazione potrebbe essere la modifica di uno dei parametri in modo che non sia sempre obbligatorio.  
  
 È possibile modificare l'ordine degli argomenti ordinando gli argomenti o spostarli verso l'alto o verso il basso perché gli argomenti sono identificati in base al nome, non in base all'ordine. Inoltre, la modifica della descrizione non interrompe il codice utilizzando il messaggio.  
  
#### <a name="action-process-argument-types"></a>Tipi di argomenti del processo di azione  
 Nella tabella seguente vengono descritti i tipi di argomenti del processo di azione.  
  
|Tipo|Descrizione|  
|----------|-----------------|  
|Boolean|Valore `true` o `false`.|  
|DateTime|Valore che archivia le informazioni di data e ora.|  
|Decimale|Valore numerico con precisione decimale. Usato quando la precisione è estremamente importante.|  
|Entità|Record per l'entità specificata. Quando si seleziona entità, l'elenco a discesa è abilitato e consente di selezionare il tipo di entità.|  
|EntityCollection|Raccolta di record di entità.|  
|EntityReference|Oggetto che contiene il nome, l'ID e il tipo di un record di entità che lo identifica in modo univoco. Quando si seleziona EntityReference, l'elenco a discesa è abilitato e consente di selezionare il tipo di entità.|  
|Float|Valore numerico con precisione decimale. Utilizzato quando i dati provengono da una misura che non è assolutamente precisa.|  
|intero|Numero intero.|  
|denaro|Valore che archivia i dati relativi a una quantità di denaro.|  
|Picklist|Valore che rappresenta un'opzione per un attributo di opzioni.|  
|stringa|Valore di testo.|  
  
> [!NOTE]
> Non è possibile impostare i valori dell'argomento **EntityCollection** nell'interfaccia utente per le condizioni o le azioni. Questi vengono forniti per l'uso da parte degli sviluppatori nel codice personalizzato. Altre informazioni: [creare azioni personalizzate](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Aggiungere fasi e passaggi  
 Le azioni sono un tipo di processo molto simile ai flussi di lavoro in tempo reale. Tutti i passaggi che possono essere usati nei flussi di lavoro in tempo reale possono essere usati in azioni. Per informazioni sui passaggi che possono essere usati sia per i flussi di lavoro in tempo reale che per le azioni, vedere [fasi e passaggi del flusso di lavoro](configure-workflow-steps.md).  
  
 Oltre ai passaggi che possono essere usati per i flussi di lavoro in tempo reale, le azioni hanno anche il passaggio **assegna valore** .  Nelle azioni possono essere utilizzate solo per impostare gli argomenti di output. È possibile utilizzare Assistente form per impostare gli argomenti di output su valori specifici o, più probabilmente, sui valori del record in cui viene eseguita l'azione, i record correlati a tale record con una relazione molti-a-uno, i record creati in un passaggio precedente o i valori che fanno parte del processo stesso.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Azioni](actions.md)  

 [Richiamare azioni personalizzate da un flusso di lavoro](invoke-custom-actions-workflow-dialog.md)   
 [Monitoraggio delle azioni e dei flussi di lavoro in tempo reale](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
