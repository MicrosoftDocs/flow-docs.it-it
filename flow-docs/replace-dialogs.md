---
title: Sostituire le interazioni con processi aziendali o app canvas | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 498efb98a4c89ca6c2a01e345f5593beae4dbcca
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64464603"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Sostituire le interazioni con processi aziendali o app canvas

[Le interazioni sono deprecate](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated) e devono essere sostituite da processi aziendali o app canvas. In questo argomento vengono descritte varie funzionalità e situazioni in cui è possibile usare un processo aziendale o un'app canvas incorporati in un modulo attivato da modello per sostituire un'interazione esistente.

## <a name="feature-capability-comparison"></a>Confronto tra funzionalità

La tabella seguente elenca le funzionalità dell'interazione e le funzionalità equivalenti dei processi aziendali e delle app canvas.


|Funzionalità dell'interazione  | Funzionalità presente in processi aziendali?  | Funzionalità presente in app canvas?  |
|---------|---------|---------|
|Pagina     | Sì <br/> (fase del processo aziendale)    | Sì <br/> (schermata dell'app)        |
|Solo prompt   |  No    |  Sì <br/> (etichette)        |
|Prompt e risposta     |  Sì <br/> (solo attributi di entità)    | Sì <br/> (etichette e campi di input)    |
|Argomenti di input     |  Limitati <br/> (fasi del processo aziendale)    | Sì <br/> (parametri della stringa di query)     |
|Variabili   |  No     |  Sì       |
|Variabili di query    |  No     |  Sì     |
|Logica di diramazione condizionale    |  Sì     | Sì <br/>  (spostarsi nelle schermate dell'app)    |
|Riutilizzo <br/> (avviare come interazione figlio)   |  No     | Sì <br/> (spostarsi nelle schermate dell'app, avviare un'altra app in una nuova finestra)     |
|Eseguire i flussi di lavoro su inizio/fine    |   Sì      |  No <br/> (usare un flusso)  |
|Eseguire flussi di lavoro di input    | Sì    | No <br/> (usare un flusso)   |
|Eseguire i flussi di lavoro nella transizione di pagina   |  Sì       | No <br/> (usare un flusso)    |
|Iniziare a usare un URL  |   No      |  Sì     |
|Registrazione delle sessioni    |  Sì       |  No     |
|Supporto SDK   |  Sì     |  Sì     |

### <a name="additional-capabilities-with-business-process-flows"></a>Funzionalità aggiuntive con i processi aziendali
- Analisi dei processi (viste, grafici e tempo trascorso in una fase)
- Controlli personalizzati

### <a name="additional-capabilities-with-canvas-apps"></a>Funzionalità aggiuntive con app canvas
- Analisi dell'app (uso e prestazioni dell'app)
- Composizione di pagine a più entità
- Eseguire i flussi
- Connettori di dati (standard e personalizzati)
- Avviare come app autonoma
- Layout configurabile

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Scelta tra processo aziendale o app canvas
Quando si sceglie la sostituzione dell'interazione, è importante tenere conto dell'esperienza utente che si vuole offrire. Tenere presente anche che quasi tutte le interazioni possono essere modellate usando un'app canvas.

I processi aziendali sono ideali per sostituire le interazioni che modellano i processi che offrono una guida attraverso una sequenza di lavoro comprensiva che richiede la collaborazione tra gruppi di utenti singoli e un contesto di esecuzione delle app Dynamics 365. Ad esempio, la revisione e l'invio delle offerte. 

In alternativa, le app canvas possono essere usate per sostituire le interazioni che modellano le attività prescrittive come ad esempio la ricerca di clienti potenziali o per semplificare l'esperienza utente per altre attività, come l'aggiornamento di un'opportunità. Si noti che scenari di questo tipo possono anche trarre vantaggio dall'avere un'app canvas autonoma. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Sostituzione dell'interazione con uno scenario di processo aziendale
Si supponga di avere un'interazione che nell'arco di alcune pagine richiede all'utente informazioni chiave, genera un'offerta, invia un messaggio di posta elettronica ai revisori che devono accettare o rifiutare l'offerta prima di inviarla mediante posta elettronica al cliente. Questo tipo di processo viene modellato in modo più efficace usando un processo aziendale. 

Per sostituire l'interazione, iniziare identificando le fasi principali del processo. Ciò può includere una fase di *preparazione dei contenuti* per verificare che tutti i prodotti siano elencati e che vengano applicati sconti, una fase di *generazione dell'offerta* per creare l'offerta e verificarne l'accuratezza del formato, una fase di *revisione principale* per inviare l'offerta per la revisione e l'approvazione, una fase di *revisione secondaria* per esaminare l'offerta in determinate circostanze e, infine, una fase di *invio dell'offerta* per inviare l'offerta al cliente.

In seguito, identificare i passaggi principali che gli utenti devono seguire nel processo. Ad esempio, la fase di *preparazione dei contenuti* potrebbe contenere un semplice passaggio vero o falso in modo che l'utente verifichi i prodotti per cui fare l'offerta, un passaggio di controllo obbligatorio per selezionare un listino prezzi e una fase numerica per immettere uno sconto prima di passare alla fase successiva. La fase di *generazione dell'offerta* potrebbe includere un [passaggio di azione](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) per creare un'offerta in base a tutte le informazioni acquisite in precedenza nella fase di *preparazione dei contenuti* e nel record Dynamics 365 correlato. Le fasi di *revisione principale* e la *revisione secondaria* potrebbero avere diversi passaggi vero o falso per guidare la revisione dell'offerta, nonché un passaggio obbligatorio per acquisire lo stato di approvazione e verificare che il processo possa passare solo alla fase successiva una volta ricevuta l'approvazione. In questo passaggio configurare la [sicurezza a livello di campo](/customer-engagement/admin/field-level-security) per assicurarsi che solo i revisori autorizzati possano approvare l'offerta.  È anche possibile aggiungere un flusso di lavoro alle fasi di *revisione principale* e *revisione secondaria*, come ad esempio l'invio di un messaggio di posta elettronica di notifica a tutti i revisori al momento dell'accesso. 

Infine, configurare le fasi del processo aziendale e i passaggi e la logica condizionale per guidare il processo. Per questo esempio, è possibile aggiungere una [diramazione condizionale](enhance-business-process-flows-branching.md) successiva alla fase di *revisione principale* in modo che, se un passaggio indica la necessità di un secondo livello di revisione, la fase successiva del processo sia la *revisione secondaria* o, in caso contrario, sia la fase di *invio dell'offerta*.

Per rendere questo processo aziendale disponibile agli utenti, assicurarsi che gli utenti idonei abbiano i privilegi di accesso al processo aziendale prima di attivarlo.

Per altre informazioni su come creare un processo aziendale, vedere [Esercitazione: Creare un processo aziendale per la standardizzazione dei processi](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Sostituzione dell'interazione con uno scenario di app canvas

Si supponga di avere un'interazione che segue uno script di chiamata che guida i rappresentanti nell'approccio diretto con i clienti potenziali. Questo processo può essere acquisito con facilità usando un'app canvas.

Iniziare con la connessione alle origini dati necessarie per leggere e scrivere dati. In questo esempio viene usata una [connessione a Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) per le informazioni su clienti potenziali, account e contatti.

Iniziare identificando il numero di schermate necessario. Per questo esempio, è possibile decidere di avere cinque schermate. 
-   Schermata 1. Per selezionare un cliente potenziale da un elenco da chiamare.
-   Schermata 2. Per presentazioni, verifica della disponibilità a una conversazione e per pianificare una nuova chiamata in una data successiva. 
-   Schermata 3. Per determinare il BANT (budget, autorità, necessità e sequenza temporale). 
-   Schermata 4. Per acquisire i passaggi successivi e pianificare le chiamate di follow-up. 
-   Schermata 5. Per ringraziare il cliente potenziale per il tempo dedicato alla fine della chiamata.

Successivamente, compilare ogni schermata. Nella prima schermata [compilare una raccolta](/powerapps/maker/canvas-apps/customize-layout-sharepoint) di clienti potenziali da chiamare. Nella seconda schermata usare le etichette per dare un titolo alla schermata e specificare lo script di chiamata, usando oggetti visivi come i pulsanti di opzione per stabilire se per la persona chiamata è un buon momento per parlare. Se lo è, usare la logica condizionale per abilitare un pulsante per passare alla schermata successiva. In caso contrario, visualizzare uno script nella stessa schermata per tentare di pianificare una nuova chiamata con il cliente. Analogamente, definire lo script di chiamata in più schermate.

Infine, [definire la navigazione tra schermate](/powerapps/maker/canvas-apps/functions/function-navigate). In questo esempio oltre a spostarsi tra le schermate in sequenza, si potrebbe voler far passare l'utente dalla seconda schermata all'ultima (la fine dello script in cui si ringrazia il cliente potenziale per il tempo dedicato) se il cliente potenziale non è interessato ad avere una conversazione.

Per rendere questa app disponibile agli utenti, è necessario pubblicarla. Si consideri come tale scenario potrebbe venire trasformato dalla disponibilità di un'app autonoma che specifica script di chiamata e supporta l'inserimento rapido dei dati.

Si supponga di voler incorporare l'esperienza in Dynamics 365 for Sales. A tale scopo, iniziare con la creazione di un iframe in un modulo di Dynamics 365 for Sales. Passare quindi alla sezione **Applicazioni** del menu di PowerApps, selezionare l'app appena pubblicata, copiare il collegamento Web dalla scheda **Dettagli** e incollarlo come URL per l'iframe. 

Andando oltre, si supponga di voler rendere l'app disponibile direttamente nel modulo principale dei clienti potenziali e in contesto con il cliente potenziale, in modo che non richieda all'utente di selezionare un cliente potenziale nella prima schermata. Per passare informazioni rilevanti all'app, è sufficiente modificare l'URL dell'iframe per accodare una stringa di query che contiene queste informazioni, ad esempio gli ID del cliente potenziale o dell'account, usando JavaScript che viene eseguito in un determinato evento, ad esempio il caricamento del modulo. Successivamente, aggiornare l'app per rimuovere la prima schermata (per la selezione del cliente potenziale) e accedere invece ai valori passati all'app tramite la stringa di query usando la [funzione Param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>Domande frequenti sulla sostituzione delle interazioni

È necessario tenere traccia delle dipendenze delle app canvas? 
- Viene tenuta traccia delle dipendenze delle app canvas come per quelle di Dynamics 365 Customer Engagement.

È possibile avviare un'app canvas come una finestra popup da un pulsante nella barra dei comandi?
- Sì. A tale scopo, è sufficiente impostare l'URL di destinazione su quello dell'app canvas, ottenuto dalla sezione **Dettagli** dell'app, come descritto in precedenza.

I flussi di lavoro possono essere chiamati da un'app canvas?
- Questa funzione non è supportata. È consigliabile usare invece un flusso. Altre informazioni: [Introduzione ai flussi di un pulsante con input dell'utente](button-flow-with-user-input-tokens.md)

È possibile convertire automaticamente le interazioni in processi aziendali o app canvas?
- Non è possibile convertire automaticamente le interazioni in processi aziendali o app canvas.


## <a name="see-also"></a>Vedere anche
[Esercitazione: Creare un processo aziendale per la standardizzazione dei processi](create-business-process-flow.md) </br>
[Che cosa sono le app canvas in PowerApps?](/powerapps/maker/canvas-apps/getting-started)


