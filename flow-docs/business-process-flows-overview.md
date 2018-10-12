---
title: Panoramica dei processi aziendali | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: baefae21e605b0e54e32b09dfaee8f2980d73c13
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690312"
---
# <a name="business-process-flows-overview"></a>Panoramica dei processi aziendali

La creazione di un processo aziendale consente di garantire che i dati immessi siano coerenti e che sia sempre applicata la stessa procedura quando si lavora con un cliente. Ad esempio, si supponga di voler creare un processo aziendale per gestire le richieste di servizio di un cliente nello stesso modo oppure per ottenere l'approvazione di una fattura prima di inviare un ordine. I processi aziendali si basano sulla stessa tecnologia di altri processi, ma offrono funzionalità molto diverse rispetto a quelle usate dai processi. Per informazioni su come creare o modificare un processo aziendale, vedere [Creare un processo aziendale](create-business-process-flow.md).  
  
 [Breve video (4:49) sui processi aziendali.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Perché usare i processi aziendali  
I processi aziendali consentono agli utenti di portare a termine un lavoro. Offrono un'esperienza utente semplificata che rappresenta i processi definiti dall'organizzazione con i quali gli utenti devono interagire per completare qualsiasi tipo di attività. L'esperienza utente può essere adattata ai diversi ruoli di sicurezza affinché gli utenti possano lavorare nel miglior modo possibile.  
  
 È possibile usare i processi aziendali per definire una serie di passaggi da seguire per ottenere il risultato desiderato. Questi passaggi sono un indicatore visivo che comunica agli utenti il punto in cui si trovano nel processo aziendale. I processi aziendali riducono la necessità di formazione degli utenti che non devono familiarizzare con le entità che useranno. Sarà il processo stesso ad accompagnarli. È possibile configurare processi aziendali per supportare metodologie di vendita comuni che consentono a gruppi vendite di raggiungere risultati migliori. Per i gruppi dei servizi, i processi aziendali consentono al personale nuovo di essere più veloce e di evitare eventuali errori che potrebbero non soddisfare i clienti.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>Operazioni possibili con i processi aziendali  
 Con i processi aziendali, si definisce una serie di *fasi* e di *passaggi* che vengono poi visualizzati in un controllo nella parte superiore del modulo.  
  
 ![Processo aziendale con fasi](media/business-process-stages.png "Processo aziendale con fasi")  
  
 Ogni fase contiene un gruppo di passaggi. Ogni passaggio rappresenta un campo in cui è possibile immettere i dati. Si può passare alla fase successiva selezionando il pulsante **Fase successiva**. È possibile creare un passaggio obbligatorio se si vuole che nel campo corrispondente siano immessi i dati prima di poter passare alla fase successiva. Questo passaggio è comunemente detto "controllo di accesso alla fase".  
  
 I processi aziendali appaiano relativamente semplici rispetto ad altri tipi di processi perché non si basano su nessun tipo di logica di business condizionale o di automazione, ma contribuiscono a semplificare le operazioni di immissione e di controllo dei dati nelle fasi. Tuttavia, se usati in combinazione con altri processi e personalizzazioni, possono essere molto importanti perché consentono agli utenti di risparmiare tempo, ridurre i costi di formazione e facilitare l'adozione da parte degli utenti.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Processi aziendali integrati con le altre personalizzazioni  
 Quando i dati vengono immessi usando i processi aziendali, le modifiche ai dati vengono applicate anche ai campi del modulo. In questo modo, l'automazione delle regole di business o degli script del modulo può essere immediatamente applicata. È possibile aggiungere passaggi per impostare valori in campi che non sono presenti nel modulo. Questi campi verranno aggiunti al modello a oggetti `Xrm.Page` usato per gli script del modulo. Tutti i flussi di lavoro avviati dalle modifiche apportate ai campi inclusi in un processo aziendale saranno applicati al salvataggio dei dati nel modulo. Se l'automazione è applicata da un flusso di lavoro in tempo reale, le modifiche saranno immediatamente visibili nel momento in cui i dati nel modulo vengono aggiornati dopo aver salvato il record.  
  
 Anche se il controllo del processo aziendale nel modulo non offre una programmazione lato client diretta, le modifiche applicate dalle regole di business o dagli script del modulo vengono applicate automaticamente ai controlli del processo aziendale. Se un campo è nascosto in un modulo, lo sarà anche nel controllo del processo aziendale. Se si imposta un valore usando regole di business, tale valore sarà impostato nel processo aziendale.  
  
### <a name="concurrent-process-flows"></a>Processi simultanei  
 I processi aziendali simultanei consentono di personalizzare la configurazione di più processi aziendali e di associarli allo stesso record iniziale. Gli utenti possono passare tra più processi aziendali in esecuzione simultaneamente e riprendere il lavoro nella fase del processo in cui sono rimasti.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Processi aziendali di sistema  
 Sono inclusi i processi aziendali seguenti. Per informazioni sul funzionamento dei processi aziendali, rivedere questi processi aziendali di sistema:  
  
-   Processo di vendita lead - opportunità  
  
-   Processo di vendita opportunità  
  
-   Processo telefono - caso  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Più entità nei processi aziendali  
 È possibile usare un processo aziendale per una singola entità oppure contemplare più entità. Ad esempio, un processo potrebbe iniziare con un'opportunità, continuare con un'offerta, un ordine e infine una fattura, prima di tornare alla chiusura dell'opportunità.  
  
 È possibile progettare processi aziendali che raggruppano i record di un massimo di cinque diverse entità in un unico processo, in modo che gli utenti che usano l'app possano concentrarsi sul flusso del processo anziché sulle entità all'interno del processo. È quindi più semplice spostarsi tra i record di entità correlate.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Più processi aziendali disponibili per ogni entità  
 Può succedere che non tutti gli utenti di un'organizzazione debbano seguire lo stesso processo e che alcune condizioni richiedano l'applicazione di un processo diverso. Per garantire processi appropriati a varie condizioni, è possibile attivare fino a 10 processi aziendali per ogni entità.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Controllo del processo aziendale da applicare  
 È possibile associare i processi aziendali ai ruoli di sicurezza in modo che solo gli utenti con tali ruoli di sicurezza possano visualizzare o usare i processi. È anche possibile impostare l'ordine dei processi aziendali per definire quale sarà il processo aziendale predefinito. Funziona esattamente nello stesso modo in cui si definiscono più moduli per un'entità.  
  
 Quando si crea un nuovo record di entità, l'elenco dei processi aziendali attivi disponibili viene filtrato in base al ruolo di sicurezza dell'utente. Per impostazione predefinita, viene applicata la prima definizione del processo aziendale attivo disponibile per il ruolo di sicurezza dell'utente in base all'elenco dell'ordine dei processi. Se sono disponibili più definizioni di un processo aziendale attivo, è possibile caricarne un altro dalla finestra di dialogo "Cambia processo". Ogni volta che si cambia processo, il processo di cui viene attualmente eseguito il rendering passa in background e viene sostituito dal processo selezionato. Mantiene comunque lo stato e può essere nuovamente selezionato. A ogni record è possibile associare più istanze di processo, una per ogni diversa definizione del processo aziendale, per un massimo di 10 totali. Al caricamento del modulo, è possibile eseguire il rendering solo di un processo aziendale. Quando un utente applica un processo diverso, per impostazione predefinita tale processo può essere caricato solo per l'utente specifico.  
  
 Per garantire che un processo aziendale venga caricato per impostazione predefinita per tutti gli utenti, vale a dire sia associato, è possibile aggiungere uno script dell'API Client personalizzato (risorsa Web) al caricamento del modulo in cui si specifica di caricare un'istanza del processo aziendale esistente in base all'ID definizione del processo aziendale. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Considerazioni sui processi aziendali  
 I processi aziendali possono essere definiti solo per le entità che li supportano. È anche necessario sapere che esistono dei limiti relativamente al numero di processi, fasi e passaggi che possono essere aggiunti.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Processi aziendali che chiamano un flusso di lavoro  
 È possibile chiamare flussi di lavoro su richiesta dall'interno di un processo aziendale. È possibile eseguire questa configurazione dalla nuova finestra di progettazione del processo aziendale. Trascinare il componente del flusso di lavoro in una fase del processo o nella sezione dei flussi di lavoro globali. Per altre informazioni sull'uso dei flussi di lavoro nei processi aziendali, vedere [Blog: Business process flow automation in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/) (Blog: Automazione dei processi aziendali in Dynamics 365).  
  
 Quando si include un flusso di lavoro che deve essere avviato nella fase Uscita fase del processo aziendale, e tale fase è l'ultima del processo, nella finestra di progettazione sembra che il flusso di lavoro sarà attivato al completamento della fase. In realtà, il flusso di lavoro non verrà attivato poiché non è stata eseguita una transizione di fase. Non si riceverà né un avviso né un errore che impedisce di includere il flusso di lavoro nella fase. Quando un utente interagisce con il processo aziendale, il completamento o l'abbandono del processo non determina una transizione di fase e pertanto il flusso di lavoro non viene attivato. Si considerino gli esempi seguenti:  
  
-   Si crea un processo aziendale con due fasi, la fase S1 si connette alla fase S2, con un flusso di lavoro nella fase S2, e si imposta il trigger su **Uscita fase**.  
  
-   Si crea un processo aziendale con tre fasi, la fase S1 si connette alla fase S2, quindi la fase S2 crea un ramo per la fase S3. Si include un flusso di lavoro nella fase S2 e si imposta il trigger su **Uscita fase**.  
  
 In nessuno dei casi il flusso di lavoro verrà attivato. Per risolvere questo problema, è possibile aggiungere un flusso di lavoro globale e aggiungere il flusso di lavoro che si vuole attivare. In questo modo il flusso di lavoro viene attivato per il processo aziendale e non per una fase del processo. È possibile impostare il trigger di un flusso di lavoro globale su Processo abbandonato o Processo completato in modo che il flusso di lavoro sia attivato quando un utente abbandona o completa il processo aziendale.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entità che possono usare i processi aziendali  
 Tutte le entità personalizzate possono usare i processi aziendali. Anche le entità standard seguenti possono usare i processi aziendali:  
  
-   Account  
-   Appuntamento  
-   Campagna  
-   Attività campagna  
-   Risposta campagna  
-   Concorrente  
-   Contatto  
-   Indirizzo di posta elettronica  
-   Diritto  
-   Fax  
-   Maiuscole/minuscole  
-   Fattura  
-   Cliente potenziale  
-   Lettera  
-   Elenco marketing  
-   Opportunità  
-   Chiamata telefonica  
-   Prodotto  
-   Voce di listino  
-   Offerta  
-   Appuntamento ricorrente  
-   Documentazione di vendita  
-   Impegno social  
-   Ordine  
-   Utente  
-   Attività  
-   Team  
  
 Per abilitare un'entità personalizzata per i processi aziendali, selezionare la casella di controllo **Processi aziendali (verranno creati i campi)** nella definizione dell'entità. Si noti che questa azione non può essere annullata.  
  
> [!NOTE]
>  Se si passa alla fase del processo aziendale che contiene l'entità `Social Activity` e si seleziona il pulsante **Fase successiva**, verrà visualizzata l'opzione **Crea**. Scegliendo **Crea**, viene caricato il modulo **Impegno social**. Tuttavia, poiché `Social Activity` non è un'entità valida per `Create` dall'interfaccia utente dell'app, non sarà possibile salvare il modulo e verrà visualizzato il messaggio di errore "Errore imprevisto".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Numero massimo di processi, fasi e passaggi  
 Per garantire prestazioni accettabili e poter usare l'interfaccia utente, esistono alcune limitazioni da tenere presente quando si prevede di usare i processi aziendali:  
  
-   Per ogni entità non è possibile attivare più di 10 processi aziendali.  
  
-   Ogni processo non può contenere più di 30 fasi.  
  
-   I processi a più entità non possono contenere più di cinque entità.
  
## <a name="business-process-flow-entity-customization-support"></a>Supporto per la personalizzazione delle entità del processo aziendale 

A partire dall'aggiornamento di Dynamics 365 versione 9.0 (online), le entità del processo aziendale vengono visualizzate nel sistema in modo che i record di dati delle entità siano disponibili in griglie, visualizzazioni, grafici e dashboard. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Usare record di entità del processo aziendale con griglie, visualizzazioni, grafici e dashboard

Essendo i processi aziendali disponibili come entità, ora è possibile usare ricerche avanzate, visualizzazioni, grafici e dashboard originati dai dati dei processi aziendali per una specifica entità, ad esempio un lead o un'opportunità. Gli amministratore di sistema e gli addetti alla personalizzazione possono creare per i processi aziendali griglie, visualizzazioni e dashboard personalizzati, simili a quelli creati con qualsiasi altra entità.

I processi aziendali, ad esempio **Processo di vendita lead - opportunità** vengono visualizzati in Esplora soluzioni come entità personalizzabile.

![Esplora soluzioni con l'entità Processo lead - opportunità](media/bpf-lead-solution-explorer.png)

Per accedere alla visualizzazione del processo aziendale predefinito, aprire Esplora soluzioni, espandere **Entità** >, espandere il processo necessario, ad esempio **Processo di vendita lead - opportunità**, selezionare **Visualizzazioni**, quindi scegliere la visualizzazione che si preferisce.

Sono disponibili diverse visualizzazioni predefinite che possono essere visualizzate come grafico, ad esempio la visualizzazione **Active Opportunity Sales Process** (Processo di vendita opportunità attivo). 

![Visualizzazione del processo di vendita dell'opportunità attivo](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagire con l'entità del processo aziendale da un flusso di lavoro
È possibile interagire con le entità del processo aziendale da un flusso di lavoro. Ad esempio, è possibile creare un flusso di lavoro per il record di entità Processo aziendale se si vuole modificare la fase attiva quando viene aggiornato un campo nel record di entità Opportunità. Per altre informazioni su come eseguire questa operazione, vedere [Automate business process flow stages using workflows](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows) (Automatizzare le fasi del processo aziendale usando i flussi di lavoro).


### <a name="limitations-of-using-business-process-flow-entities"></a>Limitazioni nell'uso delle entità del processo aziendale

- Attualmente non è possibile creare moduli personalizzati per le entità che si basano su un processo aziendale.
- Se una soluzione include un'entità del processo aziendale, tale entità deve essere aggiunta manualmente alla soluzione prima dell'esportazione. In caso contrario, l'entità del processo aziendale non sarà inclusa nel pacchetto della soluzione. Altre informazioni: [Add solution components](/powerapps/maker/model-driven-apps/create-solution#add-solution-components) (Aggiungere componenti di soluzione)

### <a name="next-steps"></a>Passaggi successivi  
 [Breve video (4:49) sui processi aziendali](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Creare un processo aziendale](create-business-process-flow.md)   
 [Migliorare i processi aziendali con la creazione dei rami](enhance-business-process-flows-branching.md) <br/>
 [Whitepaper: Process Enablement with Dynamics 365](http://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf) (White paper: Abilitazione del processo con Dynamics 365)</br>
