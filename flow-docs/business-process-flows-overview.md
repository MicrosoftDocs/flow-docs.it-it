---
title: Cenni preliminari sui flussi del processo di business | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 230c35947c4e499c5e26fc37bb87828ec787a469
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545510"
---
# <a name="business-process-flows-overview"></a>Panoramica sui flussi del processo di business
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

È possibile garantire che gli utenti immettano i dati in modo coerente e seguano la stessa procedura ogni volta che lavorano con un cliente creando un flusso del processo di business. È possibile, ad esempio, creare un flusso del processo di business in modo che tutti gli utenti gestiscano le richieste del servizio clienti allo stesso modo o per richiedere che gli utenti ottengano l'approvazione di una fattura prima di inviare un ordine. I flussi del processo di business utilizzano la stessa tecnologia sottostante di altri processi, ma le funzionalità che forniscono sono molto diverse dalle altre funzionalità che utilizzano i processi. Per informazioni su come creare o modificare un flusso del processo di business, vedere [creare un flusso del processo di business](create-business-process-flow.md).  
  
 [Guarda un breve video (4:49) sui flussi del processo di business.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Perché usare i flussi del processo di business?  
I flussi del processo di business forniscono una guida che consente agli utenti di svolgere il proprio lavoro. Forniscono un'esperienza utente semplificata che conduce le persone attraverso i processi definiti dall'organizzazione per le interazioni che devono essere avanzate a una conclusione di qualche tipo. Questa esperienza utente può essere personalizzata in modo che gli utenti con ruoli di sicurezza diversi possano avere un'esperienza ottimale per il lavoro svolto.  
  
 Usare i flussi del processo di business per definire una serie di passaggi che gli utenti devono seguire per portarli a un risultato desiderato. Questi passaggi forniscono un indicatore visivo che indica agli utenti dove si trovano nel processo di business. I flussi del processo di business riducono la necessità di training perché i nuovi utenti non devono concentrarsi sull'entità da usare. Possono consentire al processo di guidarli. È possibile configurare i flussi del processo di business per supportare le metodologie di vendita comuni che consentono ai gruppi di vendite di ottenere risultati migliori. Per i gruppi di servizi, i flussi del processo di business possono aiutare i nuovi dipendenti ad accelerare la velocità ed evitare errori che potrebbero comportare l'insoddisfazione dei clienti.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>Che cosa possono fare i flussi del processo aziendale?  
 Con i flussi del processo di business, si definisce un set di *fasi* e *passaggi* che vengono quindi visualizzati in un controllo nella parte superiore del form.  
  
 ![Processo di business con fasi](media/business-process-stages.png "Processo di business con fasi")  
  
 Ogni fase contiene un gruppo di passaggi. Ogni passaggio rappresenta un campo in cui è possibile immettere i dati. Le persone avanzano alla fase successiva usando il pulsante **fase successiva** . È possibile eseguire un passaggio necessario in modo che gli utenti debbano immettere i dati per il campo corrispondente prima di poter procedere alla fase successiva. Questo metodo è comunemente denominato "Stage-Gate".  
  
 I flussi del processo di business sono relativamente semplici rispetto ad altri tipi di processi, in quanto non forniscono logica di business condizionale o automazione oltre a offrire un'esperienza semplificata per l'immissione di dati e il controllo delle fasi. Tuttavia, quando si combinano con altri processi e personalizzazioni, questi possono svolgere un ruolo importante nel salvare i tempi, ridurre i costi di formazione e aumentare l'adozione dell'utente.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Flussi del processo di business integrati con altre personalizzazioni  
 Quando l'utente o l'utente immette dati mediante flussi del processo di business, le modifiche ai dati vengono applicate anche ai campi del modulo in modo che sia possibile applicare immediatamente qualsiasi automazione fornita dalle regole business o dagli script del modulo. È possibile aggiungere i passaggi che impostano i valori per i campi che non sono presenti nel form e questi campi verranno aggiunti al modello a oggetti di `Xrm.Page` usato per gli script del modulo. Tutti i flussi di lavoro avviati dalle modifiche ai campi inclusi in un flusso del processo di business verranno applicati quando vengono salvati i dati nel form. Se l'automazione viene applicata da un flusso di lavoro in tempo reale, le modifiche saranno immediatamente visibili all'utente quando i dati nel modulo vengono aggiornati dopo il salvataggio del record.  
  
 Sebbene il controllo di flusso del processo di business nel form non fornisca alcuna programmabilità diretta sul lato client, le modifiche applicate dalle regole di business o dagli script del modulo vengono applicate automaticamente ai controlli di flusso del processo di business. Se si nasconde un campo in un form, il campo sarà anche nascosto nel controllo di flusso del processo di business. Se si imposta un valore utilizzando regole business o script del modulo, tale valore verrà impostato all'interno del flusso del processo di business.  
  
### <a name="concurrent-process-flows"></a>Flussi di processi simultanei  
 I flussi di processi aziendali simultanei consentono ai personalizzatori di configurare più processi aziendali e di associarli allo stesso record iniziale. Gli utenti possono passare tra più processi di business in esecuzione contemporaneamente e riprendere il lavoro in fase di esecuzione nel processo in cui si trovavano.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Flussi del processo di business di sistema  
 Sono inclusi i seguenti flussi del processo di business. Per comprendere il funzionamento del flusso del processo di business, esaminare i flussi dei processi di business del sistema seguenti:  
  
-   Lead to Opportunity Sales process  
  
-   Processo vendite opportunità  
  
-   Da telefono a caso processo  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Più entità nei flussi del processo di business  
 È possibile utilizzare un flusso del processo di business per una singola entità o per più entità. Ad esempio, è possibile che si disponga di un processo che inizia con un'opportunità, quindi continua con una virgoletta, un ordine e quindi una fattura, prima di restituire infine per chiudere l'opportunità.  
  
 È possibile progettare flussi del processo di business che uniscono i record per un massimo di cinque entità diverse in un unico processo, in modo che le persone che usano l'app possano concentrarsi sul flusso del processo anziché sull'entità in cui lavorano. Possono spostarsi più facilmente tra i record di entità correlati.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Sono disponibili più flussi del processo di business per entità  
 Non tutti gli utenti di un'organizzazione possono seguire lo stesso processo e condizioni diverse possono richiedere l'applicazione di un processo diverso. È possibile disporre di un massimo di 10 flussi di processi aziendali attivi per entità per fornire processi appropriati per situazioni diverse.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Controllare il flusso del processo di business che verrà applicato  
 È possibile associare i flussi del processo di business ai ruoli di sicurezza in modo che solo gli utenti con tali ruoli di sicurezza possano visualizzarli o usarli. È inoltre possibile impostare l'ordine dei flussi del processo di business in modo da poter controllare quale flusso del processo di business verrà impostato per impostazione predefinita. Questa operazione funziona nello stesso modo in cui vengono definiti più moduli per un'entità.  
  
 Quando un utente crea un nuovo record di entità, l'elenco della definizione di processo di business attivo disponibile viene filtrato in base al ruolo di sicurezza dell'utente. La prima definizione di processo di business attivata disponibile per il ruolo di sicurezza dell'utente in base all'elenco di ordini di elaborazione è quella applicata per impostazione predefinita. Se è disponibile più di una definizione di processo di business attivo, gli utenti possono caricarne un'altra dalla finestra di dialogo Cambia processo. Ogni volta che vengono scambiati processi, quello attualmente sottoposto a rendering passa allo sfondo e viene sostituito da quello selezionato, ma mantiene lo stato e può essere cambiato. A ogni record possono essere associate più istanze di processo, ciascuna per una definizione di flusso del processo di business diversa, fino a un totale di 10. Al caricamento del form viene eseguito il rendering di un solo flusso del processo di business. Quando un utente applica un processo diverso, il processo può essere caricato per impostazione predefinita solo per tale utente specifico.  
  
 Per assicurarsi che un processo di business venga caricato per impostazione predefinita per tutti gli utenti (comportamento equivalente a "blocco" del processo), è possibile aggiungere uno script API client personalizzato (risorsa Web) al caricamento del modulo che carica in modo specifico un'istanza del processo di business esistente basata sull'azienda ID definizione del processo. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Considerazioni sui flussi del processo di business  
 È possibile definire i flussi del processo di business solo per le entità che le supportano. È anche necessario tenere presente i limiti per il numero di processi, fasi e passaggi che è possibile aggiungere.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Flussi del processo di business che chiamano un flusso di lavoro  
 È possibile chiamare i flussi di lavoro su richiesta dall'interno di un flusso del processo di business. È possibile configurare questa impostazione dalla nuova finestra di progettazione del flusso del processo di business trascinando un componente del flusso di lavoro in una fase di elaborazione o nella sezione flussi di lavoro globali. Per ulteriori informazioni sull'utilizzo dei flussi di lavoro nei flussi del processo di business, vedere il Blog relativo all' [automazione del flusso dei processi di business in Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Quando si include un flusso di lavoro che si vuole attivare alla chiusura della fase di una fase nel flusso del processo di business e tale fase è l'ultima fase del flusso, la finestra di progettazione dà l'impressione che il flusso di lavoro venga attivato al termine della fase. Tuttavia, il flusso di lavoro non verrà attivato perché non viene eseguita una transizione della fase. Non verrà visualizzato alcun avviso o errore che impedisce di includere il flusso di lavoro nella fase. Quando un utente interagisce con il flusso del processo di business, il completamento o l'abbandono del processo non comporta una transizione di fase e pertanto il flusso di lavoro non viene attivato. Si considerino gli esempi seguenti:  
  
-   Si crea un flusso del processo di business con due fasi, S1 si connette a S2, con un flusso di lavoro nella fase S2 e imposta il trigger per la **fase di uscita**.  
  
-   Si crea un flusso del processo di business con tre fasi, S1 si connette a S2, quindi i rami S2 a S3. Si include un flusso di lavoro in S2 e si imposta il trigger per la **fase di chiusura**.  
  
 Il flusso di lavoro non viene attivato in entrambi i casi. Per ovviare a questo problema, è possibile aggiungere un flusso di lavoro globale e aggiungere il flusso di lavoro che si desidera attivare, in modo che il flusso di lavoro venga attivato per il processo di business anziché una fase del processo. È possibile impostare il trigger per un flusso di lavoro globale su elaborazione abbandonata o processo completato per fare in modo che il flusso di lavoro venga attivato quando un utente abbandona o completa il processo di business.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entità che possono usare i flussi del processo di business  
 Tutte le entità personalizzate possono usare i flussi del processo di business. Le entità standard seguenti possono inoltre utilizzare i flussi del processo di business:  
  
-   Account  
-   Appuntamento  
-   Campagna  
-   Attività campagna  
-   Risposta alla campagna  
-   Concorrente  
-   Contattare  
-   Posta elettronica  
-   Diritti  
-   Fax  
-   Caso  
-   Fattura  
-   Lead  
-   Lettera  
-   Elenco marketing  
-   Opportunità  
-   Telefonata  
-   Prodotto  
-   Elemento elenco prezzi  
-   Citazione  
-   Appuntamento ricorrente  
-   Letteratura sulle vendite  
-   Attività social  
-   Ordine  
-   Utente  
-   Attività  
-   Team  
  
 Per abilitare un'entità personalizzata per i flussi del processo di business, selezionare la casella di controllo **flussi del processo di business (campi che verranno creati)** nella definizione dell'entità. Si noti che non è possibile annullare questa azione.  
  
> [!NOTE]
>  Se si passa alla fase di flusso del processo di business che contiene l'entità `Social Activity` e si sceglie il pulsante **fase successiva** , verrà visualizzata l'opzione **Crea** . Quando si sceglie **Crea**, viene caricato il modulo di **attività social** . Tuttavia, poiché `Social Activity` non è valido per `Create` dall'interfaccia utente dell'app, non sarà possibile salvare il modulo e verrà visualizzato il messaggio di errore "errore imprevisto".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Numero massimo di processi, fasi e passaggi  
 Per garantire prestazioni accettabili e l'usabilità dell'interfaccia utente, è necessario tenere presenti alcune limitazioni quando si prevede di utilizzare i flussi del processo di business:  
  
-   Non possono essere presenti più di 10 processi di flusso del processo di business attivati per entità.  
  
-   Ogni processo non può contenere più di 30 fasi.  
  
-   I processi a più entità non possono contenere più di cinque entità.
  
## <a name="business-process-flow-entity-customization-support"></a>Supporto per la personalizzazione dell'entità flusso del processo di business 

Introdotta nell'aggiornamento di Dynamics 365 (online), versione 9,0, le entità del flusso del processo di business possono essere visualizzate nel sistema in modo che i dati dei record di entità possano essere resi disponibili in griglie, visualizzazioni, grafici e dashboard. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Usare i record di entità del flusso del processo di business con griglie, visualizzazioni, grafici e dashboard

Con i flussi dei processi di business disponibili come entità, è ora possibile usare reperti, viste, grafici e Dashboard avanzati originati da dati del flusso del processo di business per un'entità specifica, ad esempio un lead o un'opportunità. Gli amministratori di sistema e i personalizzatori possono creare griglie, visualizzazioni, grafici e dashboard del flusso di processi di business personalizzati simili a quelli creati con qualsiasi altra entità.

I flussi del processo di business, ad esempio **lead to Opportunity Sales process**, vengono visualizzati come entità personalizzabile in Esplora soluzioni.

![Esplora soluzioni con l'entità di processo lead-to-Opportunity](media/bpf-lead-solution-explorer.png)

Per accedere a una visualizzazione del flusso del processo di business predefinita, aprire Esplora soluzioni, espandere **entità** > espandere il processo desiderato, ad esempio **lead to Opportunity Sales process**, selezionare **views**, quindi selezionare la visualizzazione desiderata.

Sono disponibili diverse visualizzazioni predefinite che è possibile visualizzare come grafico, ad esempio la visualizzazione del **processo vendite di opportunità attive** . 

![Visualizzazione processo delle vendite di opportunità attive](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagire con l'entità del flusso del processo di business da un flusso di lavoro
È anche possibile interagire con le entità del flusso del processo di business da un flusso di lavoro. È ad esempio possibile creare un flusso di lavoro per il record dell'entità flusso del processo di business per modificare la fase attiva quando viene aggiornato un campo nel record dell'entità opportunity. Per ulteriori informazioni su come eseguire questa operazione, vedere [automatizzare le fasi del flusso del processo di business mediante i flussi di lavoro](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>Limitazioni dell'utilizzo delle entità del flusso del processo di business

- Attualmente, non è possibile creare moduli personalizzati per le entità in base a un flusso del processo di business.
- Se una soluzione include un'entità del flusso del processo di business, è necessario aggiungere manualmente l'entità del flusso del processo di business alla soluzione prima di esportarla. In caso contrario, l'entità del flusso del processo di business non verrà inclusa nel pacchetto della soluzione. Altre informazioni: [aggiungere componenti della soluzione](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Passaggi successivi  
 [Guarda un breve video (4:49) sui flussi di processi aziendali](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Creare un flusso del processo di business](create-business-process-flow.md)   
 [Migliorare i flussi di processi aziendali con la diramazione](enhance-business-process-flows-branching.md) <br/>
 [White paper: abilitazione del processo con Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
