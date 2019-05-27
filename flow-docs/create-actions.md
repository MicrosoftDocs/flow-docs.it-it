---
title: Creare un'azione personalizzata | MicrosoftDocs
description: Usare le azioni personalizzate quando si vuole automatizzare una serie di comandi nel sistema. Le azioni espandono il vocabolario disponibile per gli sviluppatori per esprimere i processi aziendali.
ms.custom: ''
ms.date: 08/06/2018
ms.reviewer: matp
ms.service: flow
ms.topic: article
author: msftman
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 92db054d5e9fab7ef6077146260ce46f540697c9
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64455778"
---
# <a name="create-a-custom-action"></a>Creare un'azione personalizzata

Usare le azioni personalizzate quando si vuole automatizzare una serie di comandi nel sistema. Le azioni espandono il vocabolario disponibile per gli sviluppatori per esprimere i processi aziendali. Un'azione usa i verbi principali come Crea, Aggiorna, Elimina e Assegna forniti dal sistema per creare verbi più espressivi come Approva, Riassegna, Indirizza o Pianifica. Se viene modificata la definizione di un processo aziendale, un utente che non è uno sviluppatore può modificare l'azione personalizzata in modo che non sia necessario modificare il codice.  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Creare un'azione  
  
> [!IMPORTANT]
>  Se si crea un'azione da includere come parte di una soluzione da distribuire, creare l'azione nel contesto della soluzione. Passare a **[Impostazioni](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Soluzioni** e individuare la soluzione non gestita cui apparterrà l'azione. Quindi, nella barra dei menu selezionare **Nuovo** > **Processo**. Ciò garantisce che il prefisso di personalizzazione associato al nome dell'azione sia coerente con gli altri componenti della soluzione. Dopo aver creato l'azione, non sarà possibile modificare il prefisso.  
  
 Come per i processi del flusso di lavoro, le azioni hanno le proprietà seguenti nella finestra di dialogo **Crea processo**.  
  
 **Nome processo**  
 Dopo aver immesso un nome per il processo, verrà creato un nome univoco per il processo rimuovendo spazi o caratteri speciali dal nome del processo.  
  
 **Categoria**  
 Questa proprietà definisce il processo come processo di azione. Non è possibile apportare modifiche dopo aver salvato il processo.  
  
 **Entità**  
 Con i processi di azioni, è possibile selezionare un'entità per specificare il contesto per il flusso di lavoro come per gli altri tipi di processi, ma è anche possibile scegliere **Nessuno (globale)**. Usare questa opzione se l'azione non richiede il contesto di un'entità specifica. Non è possibile apportare modifiche dopo aver salvato il processo.  
  
 **Tipo**  
 Usare questa proprietà per scegliere se creare una nuova azione da zero o iniziare da un modello esistente.  
 
A differenza dei processi del flusso di lavoro, non è necessario impostare le opzioni seguenti:  
  
- **Avvia in caso di**: le azioni vengono avviate quando il codice chiama il messaggio generato per le azioni.  
  
- **Ambito**: le azioni vengono sempre eseguite nel contesto dell'utente chiamante.  
  
- **Esecuzione in background**: le azioni sono sempre flussi di lavoro in tempo reale.  
  
Le azioni hanno anche elementi non presenti nei processi del flusso di lavoro: gli argomenti di input e output.

> [!NOTE]
> È possibile abilitare un'azione personalizzata da un flusso di lavoro senza scrivere codice. Altre informazioni: [Richiamare azioni personalizzate da un flusso di lavoro](invoke-custom-actions-workflow-dialog.md).
 
<a name="edit"></a>   
## <a name="edit-an-action"></a>Modificare un'azione  
 Per poter modificare i processi è necessario disattivarli.  
  
 È possibile modificare un'azione creata come parte di una soluzione non gestita o inclusa in una soluzione installata nell'organizzazione. Se la soluzione è una soluzione gestita, potrebbe non essere possibile modificarla. L'autore della soluzione ha la possibilità di modificare le proprietà gestite in modo che l'azione installata con una soluzione gestita non possa essere modificata.  
  
 Quando un'azione viene salvata, viene generato un nome univoco basato sul nome del processo. Questo nome univoco ha il prefisso di personalizzazione aggiunto dall'autore della soluzione. Si tratta del nome del messaggio che verrà usato dallo sviluppatore nel codice.  
  
 Quando si modifica un'azione sono disponibili le opzioni seguenti:  
  
 **Nome processo**  
 Dopo aver creato il processo e dopo che il nome univoco è stato generato dal nome del processo, è possibile modificare il nome del processo. È possibile applicare una convenzione di denominazione per rendere più semplice l'individuazione di processi specifici.  
  
 **Nome univoco**  
 Quando un'azione viene salvata, viene generato un nome univoco basato sul nome del processo. Questo nome univoco ha il prefisso di personalizzazione specificato dall'autore della soluzione. Si tratta del nome del messaggio che verrà usato dallo sviluppatore nel codice. Non modificare il nome univoco se il processo è stato attivato e il codice prevede di chiamare l'azione usando questo nome.  
  
> [!IMPORTANT]
>  Dopo aver attivato l'azione e aver scritto il codice per l'utilizzo di un nome univoco, non modificare il nome univoco senza modificare anche il codice che fa riferimento a esso.  
  
 **Abilita rollback**  
 In generale, i processi che supportano le transazioni annullano o eseguono il rollback dell'intera operazione se una parte di essi ha esito negativo. Esistono alcune eccezioni. Alcune azioni che gli sviluppatori potrebbero eseguire nel codice avviato dall'azione potrebbero non supportare le transazioni. Ad esempio, nel caso in cui il codice esegua azioni in altri sistemi che non rientrano nell'ambito della transazione. L'azione in esecuzione in un'app non potrà eseguire il rollback delle azioni. Alcuni messaggi nella piattaforma non supportano le transazioni. Tuttavia, tutte le operazioni eseguibili con la sola interfaccia utente dell'azione supporteranno le transazioni. Tutte le azioni che fanno parte di un flusso di lavoro in tempo reale vengono considerate nella transazione, ma con azioni che è possibile rifiutare esplicitamente.  
  
 È consigliabile rivolgersi allo sviluppatore che userà questo messaggio per determinare se il messaggio deve essere incluso nella transazione o meno. In genere, un'azione deve essere nella transazione se le azioni eseguite dal processo aziendale devono essere tutte eseguite. L'esempio classico è il trasferimento di fondi tra due conti bancari. Se si prelevano fondi da un conto è necessario depositarli in un altro conto. Se una delle due azioni non viene eseguita, entrambe le azioni devono avere esito negativo.  
  
> [!NOTE]
>  Se un'azione personalizzata viene richiamata direttamente da un flusso di lavoro non è possibile abilitare il rollback. È possibile abilitare il rollback se un'azione viene attivata da un messaggio dei servizi Web di PowerApps.  
  
 **Attiva come**  
 Come avviene per tutti i processi, è possibile attivare il processo come modello e usarlo come un punto iniziale avanzato per i processi che seguono un modello simile.  
  
 **Definire gli argomenti del processo**  
 In questa area verranno specificati tutti i dati previsti per l'avvio dell'azione e i dati che verranno passati all'esterno dell'azione. Altre informazioni: [Definire gli argomenti del processo](#define-process-arguments)  
  
 **Aggiungere fasi e passaggi**  
 Come avviene per gli altri processi, specificare le azioni da eseguire e quando eseguirle. Altre informazioni: [Aggiungere fasi e passaggi](#add-stages-and-steps)

<a name="BKMK_DefineProcessArgs"></a>   
## <a name="define-process-arguments"></a>Definire gli argomenti del processo  
 Uno sviluppatore che usa un messaggio può iniziare con alcuni dati che possono essere passati nel messaggio. Ad esempio, per creare un nuovo record del caso, è possibile passare il valore di titolo del caso come argomento di input.  
  
 Al termine del messaggio, lo sviluppatore potrebbe dover passare alcuni dati modificati o generati dal messaggio a un'altra operazione nel codice. Questi dati rappresentano l'argomento di output.  
  
 Entrambi gli argomenti di input e output devono aver un nome, un tipo e informazioni che indicano se l'argomento è sempre obbligatorio. È anche possibile specificare una descrizione.  
  
 Il nome del messaggio e le informazioni su tutti gli argomenti del processo rappresentano la "firma" del messaggio. Dopo che l'azione è stata attivata e viene usata nel codice, la firma non deve essere modificata. Se la firma viene modificata, tutto il codice che usa il messaggio non verrà eseguito. L'unica eccezione può essere rappresentata da una modifica di uno dei parametri in modo che non risulti sempre obbligatorio.  
  
 È possibile modificare l'ordine degli argomenti riordinandoli o spostandoli verso l'alto o verso il basso poiché gli argomenti sono identificati in base al nome, non in base all'ordine. Inoltre, la modifica della descrizione non interrompe il codice che usa il messaggio.  
  
### <a name="action-process-argument-types"></a>Tipi di argomento dei processi delle azioni  
 La tabella seguente descrive i tipi di argomento dei processi delle azioni.  
  
|Tipo|Descrizione|  
|----------|-----------------|  
|Boolean|Valore `true` o `false`.|  
|DateTime|Valore che memorizza informazioni di data e ora.|  
|Decimal|Valore numerico con precisione decimale. Usato quando la precisione è fondamentale.|  
|Entity|Record per l'entità specificata. Quando si seleziona Entity, viene abilitato l'elenco a discesa che consente di selezionare il tipo di entità.|  
|EntityCollection|Raccolta di record entità.|  
|EntityReference|Oggetto che contiene il nome, l'ID e il tipo e di un record entità che lo identifica in modo univoco. Quando si seleziona EntityReference, viene abilitato l'elenco a discesa che consente di selezionare il tipo di entità.|  
|Float|Valore numerico con precisione decimale. Usato quando i dati provengono da una misura che non è completamente precisa.|  
|Integer|Numero intero.|  
|Money|Valore che memorizza i dati su un importo in denaro.|  
|Picklist|Valore che rappresenta un'opzione per un attributo OptionSet.|  
|String|Valore di testo.|  
  
> [!NOTE]
> I valori dell'argomento **EntityCollection** non possono essere impostati nell'interfaccia utente per condizioni o azioni. I valori sono disponibili per l'uso da parte degli sviluppatori nel codice personalizzato. Altre informazioni: [Create your own actions](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) (Creare azioni personalizzate) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Aggiungere fasi e passaggi  
 Le azioni sono un tipo di processo molto simile ai flussi di lavoro in tempo reale. Tutti i passaggi che possono essere usati nei flussi di lavoro in tempo reale possono essere usati nelle azioni. Per informazioni sui passaggi che possono essere usati per i flussi di lavoro in tempo reale e le azioni, vedere [Fasi e passaggi dei flussi di lavoro](configure-workflow-steps.md).  
  
 In aggiunta ai passaggi che possono essere usati per i flussi di lavoro in tempo reale, le azioni hanno anche il passaggio **Assegna valore**.  Nelle azioni possono essere usati solo per impostare gli argomenti di output. È possibile usare Informazioni e selezione rapida per impostare i parametri di output su valori specifici o, più probabilmente, su valori del record su cui viene eseguita l'azione, record correlati al record con una relazione molti-a-uno, record creati in un passaggio precedente o valori che sono parte del processo stesso.  
  
## <a name="next-steps"></a>Passaggi successivi  
 [Richiamare azioni personalizzate da un flusso di lavoro](invoke-custom-actions-workflow-dialog.md)   

 
 
