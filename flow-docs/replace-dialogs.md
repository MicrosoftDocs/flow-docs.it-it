---
title: Sostituire le finestre di dialogo con i flussi del processo di business o le app Canvas | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
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
ms.openlocfilehash: a7e8bac3c33fa5bb8cfb0501b981af65115036ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548807"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Sostituisci finestre di dialogo con flussi di processi aziendali o app Canvas
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Le [finestre di dialogo sono deprecate](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated)e devono essere sostituite dai flussi del processo aziendale o dalle app Canvas. Questo argomento descrive le diverse funzionalità di queste opzioni, nonché le situazioni in cui è possibile usare un flusso del processo aziendale o un'app Canvas incorporata in un form basato su modello per sostituire una finestra di dialogo esistente.

## <a name="feature-capability-comparison"></a>Confronto funzionalità funzionalità

Questa tabella elenca il set di funzionalità della finestra di dialogo e le funzionalità equivalenti nei flussi del processo di business e nelle app Canvas.


|Funzionalità finestra di dialogo  | Funzionalità nei flussi del processo di business  | Funzionalità nelle app Canvas  |
|---------|---------|---------|
|Pagina     | Sì <br/> (fase del processo di business)    | Sì <br/> (schermata app)        |
|Solo prompt   |  No    |  Sì <br/> etichette        |
|Messaggio di richiesta e risposta     |  Sì <br/> (solo attributi di entità)    | Sì <br/> (etichette e campi di input)    |
|Argomenti di input     |  Limitato <br/> (passaggi nella fase del processo di business)    | Sì <br/> (parametri della stringa di query)     |
|Variabili   |  No     |  Sì       |
|Variabili di query    |  No     |  Sì     |
|Logica di diramazione condizionale    |  Sì     | Sì <br/>  (passare a qualsiasi schermata all'interno dell'app)    |
|Riutilizzare <br/> (avvia come finestra di dialogo figlio)   |  No     | Sì <br/> (passare a una schermata all'interno dell'app, avviare un'altra app in una nuova finestra)     |
|Esegui flussi di lavoro all'inizio/fine    |   Sì      |  No <br/> (usare invece un flusso)  |
|Esegui flussi di lavoro nell'input    | Sì    | No <br/> (usare invece un flusso)   |
|Esegui flussi di lavoro nella transizione di pagina   |  Sì       | No <br/> (usare invece un flusso)    |
|Inizia a usare un URL  |   No      |  Sì     |
|Registrazione sessione    |  Sì       |  No     |
|Supporto SDK   |  Sì     |  Sì     |

### <a name="additional-capabilities-with-business-process-flows"></a>Funzionalità aggiuntive con i flussi del processo di business
- Analisi del processo (Visualizzazioni, grafici e tempo trascorso in una fase)
- Controlli personalizzati

### <a name="additional-capabilities-with-canvas-apps"></a>Funzionalità aggiuntive con le app Canvas
- Analisi delle app (utilizzo delle app &)
- Composizione di pagine con più entità
- Flussi di esecuzione
- Connettori dati (standard e personalizzato)
- Avvia come app autonoma
- Layout configurabile

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Scelta tra un flusso del processo di business o un'app Canvas
Quando si sceglie la sostituzione della finestra di dialogo, è importante tenere conto dell'esperienza utente che si desidera distribuire. Tenere inoltre presente che quasi tutte le finestre di dialogo possono essere modellate tramite un'app Canvas.

I flussi del processo di business sono più adatti per sostituire i dialoghi che i processi del modello forniscono materiale sussidiario per un workstream globale che richiede la collaborazione tra gruppi di singoli utenti e il contesto dell'app Dynamics 365. Ad esempio, la revisione delle virgolette e il routing. 

In alternativa, è possibile usare le app Canvas per sostituire i dialoghi che modellano le attività descrittive, ad esempio uno script di chiamata per la prospezione dei lead o per semplificare l'esperienza utente per altre attività, ad esempio l'aggiornamento di un'opportunità. Si noti che questi scenari possono anche trarre vantaggio dalla presenza di un'app Canvas autonoma. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Sostituzione della finestra di dialogo mediante il flusso del processo di business
Si supponga di disporre di una finestra di dialogo che, in una serie di pagine, richiede informazioni chiave dall'utente, genera un preventivo, invia un messaggio di posta elettronica ai revisori per accettare o rifiutare l'offerta, prima di inviare un messaggio di posta elettronica al cliente. Questo tipo di processo è modellato in modo più efficace utilizzando un flusso del processo di business. 

Per sostituire la finestra di dialogo, è necessario innanzitutto identificare le fasi principali del processo. Questi possono includere una fase di *preparazione del contenuto* per verificare che tutti i prodotti siano elencati e che vengano applicati gli sconti, una fase di *generazione delle virgolette* per creare le virgolette ed esaminarle per verificarne l'accuratezza del formato, una fase di *revisione principale* per cui inviare l'offerta Revisione e approvazione, una fase di *revisione secondaria* per esaminare le virgolette in determinate circostanze e infine una fase di *offerta* per inviare le virgolette al cliente.

Successivamente, identificare i passaggi chiave che gli utenti devono seguire nel processo. Ad esempio, la fase di *preparazione del contenuto* potrebbe contenere un semplice passaggio true o false per consentire all'utente di controllare i prodotti in modo da essere racchiusi tra virgolette, un passaggio di ricerca obbligatorio per selezionare un elenco prezzi e un passaggio numerico per immettere uno sconto prima di passare alla fase successiva. La fase di *generazione delle virgolette* potrebbe avere un [passaggio dell'azione](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) per creare un'offerta basata su tutte le informazioni acquisite in precedenza nella fase di *preparazione del contenuto* e nel record Dynamics 365 correlato. Le fasi di revisione *primaria* e di *revisione secondaria* possono avere diversi passaggi true o false per guidare la revisione delle virgolette, insieme a un passaggio necessario per acquisire lo stato di approvazione e assicurarsi che il processo possa essere spostato solo nella fase successiva dopo l'approvazione ricevuto. Configurare la [sicurezza a livello di campo](/customer-engagement/admin/field-level-security) in questo passaggio per assicurarsi che solo i revisori autorizzati possano fornire l'approvazione per l'offerta.  Inoltre, è possibile aggiungere un flusso di lavoro alle fasi di revisione *primaria* e di *revisione secondaria* , in modo che all'immissione venga inviata una notifica tramite posta elettronica a tutti i revisori. 

Infine, configurare le fasi e i passaggi del flusso del processo di business, insieme alla logica condizionale per guidare il flusso del processo. Per questo esempio, è possibile aggiungere un [ramo condizionale](enhance-business-process-flows-branching.md) dopo la fase di *revisione principale* , in modo che, se un passaggio indica la necessità di un secondo livello di revisione, la fase successiva del processo è la fase di *revisione secondaria* , in caso contrario, è il  *Distribuire* una fase di virgoletta.

Per rendere il flusso del processo di business disponibile per gli utenti, assicurarsi che gli utenti corretti dispongano dei privilegi per il flusso del processo di business e quindi lo attivino.

Per ulteriori informazioni su come creare un flusso del processo di business, vedere [esercitazione: creare un flusso del processo di business per standardizzare i processi](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Sostituzione della finestra di dialogo con lo scenario di app Canvas

Si supponga di disporre di una finestra di dialogo che segue uno script di chiamata che guida i rappresentanti delle vendite tramite Lead di chiamata a freddo. Questo processo può essere facilmente acquisito usando un'app Canvas.

Iniziare a connettersi alle origini dati necessarie per la lettura e la scrittura dei dati. In questo esempio viene usata una [connessione a Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) per le informazioni relative a lead, account e contatti.

Per iniziare, identificare il numero di schermate necessarie. Per questo esempio, è possibile decidere di disporre di cinque schermate. 
-   Schermata 1. Per selezionare un lead da un elenco da chiamare.
-   Schermata 2. Per introduzioni, verifica della disponibilità di una conversazione e pianificazione di un callback in un secondo momento. 
-   Schermata 3. Per determinare BANT (budget, autorità, necessità e sequenza temporale). 
-   Schermata 4. Per acquisire i passaggi successivi e pianificare le chiamate di completamento. 
-   Schermata 5. Ringraziamo il lead per il loro tempo alla fine della chiamata.

Compilare quindi ogni schermata. Nella prima schermata, [compilare una raccolta](/powerapps/maker/canvas-apps/customize-layout-sharepoint) di lead che devono essere chiamati. Nel secondo caso, usare le etichette per assegnare un titolo alla schermata e fornire lo script di chiamata, usando i controlli come i pulsanti di opzione per acquisire la possibilità che la persona comunichi. In caso contrario, usare la logica condizionale per abilitare un pulsante per passare alla schermata successiva e, in caso contrario, rivelare uno script nella stessa schermata per tentare di pianificare una chiamata con il cliente. Analogamente, definire lo script di chiamata nelle schermate successive.

Infine, [definire la navigazione tra le schermate](/powerapps/maker/canvas-apps/functions/function-navigate). In questo esempio, oltre a spostarsi in sequenza tra le schermate, è possibile passare all'utente dalla seconda schermata all'ultima schermata (la fine dello script che ringrazia il lead per il loro tempo) se il lead non è interessato a una conversazione.

Per rendere disponibile l'app agli utenti, pubblicare l'app. Considerare il modo in cui tale scenario può essere trasformato tramite la disponibilità di un'app autonoma che fornisce script di chiamata e supporta l'immissione di dati rapidi.

Si supponga di voler incorporare questa esperienza in Dynamics 365 Sales. Per eseguire questa operazione, iniziare con la creazione di un iframe in un modulo Sales di Dynamics 365. Passare quindi alla sezione **app** dal menu PowerApps, selezionare l'app appena pubblicata, copiare il collegamento Web nella scheda **Dettagli** e incollarlo come URL per l'iframe. 

A questo punto, si supponga di voler rendere disponibile l'app direttamente all'interno del modulo principale principale e di trovarsi nel contesto del lead, in modo che l'app non richieda all'utente di selezionare un lead nella prima schermata. Per passare le informazioni rilevanti all'app, è sufficiente modificare l'URL di iframe per aggiungere una stringa di query che contiene queste informazioni, ad esempio ID di lead o account, usando JavaScript che viene eseguito in un determinato evento, ad esempio il caricamento del modulo. Aggiornare quindi l'app per rimuovere la prima schermata (per la selezione del lead) e accedere invece ai valori passati all'app tramite la stringa di query usando la [funzione param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>Domande frequenti sulla sostituzione di finestre

Sono state rilevate dipendenze dalle app Canvas? 
- Le dipendenze dalle app Canvas vengono rilevate nello stesso modo delle dipendenze nelle app Dynamics 365.

È possibile avviare un'app Canvas come popup da un pulsante della barra dei comandi?
- Sì. A tale scopo, è sufficiente impostare l'URL di destinazione su quello dell'app Canvas, ottenuto dalla sezione dei **Dettagli** dell'app, come descritto in precedenza.

I flussi di lavoro possono essere chiamati da un'app Canvas?
- Questa operazione non è supportata. Si consiglia invece di usare un flusso. Altre informazioni: [Introduzione ai flussi di un pulsante con l'input dell'utente](button-flow-with-user-input-tokens.md)

È possibile convertire automaticamente I dialoghi nei flussi di processi aziendali o nelle app Canvas?
- Non esiste un metodo automatico per convertire i dialoghi nei flussi di processi aziendali o nelle app Canvas.


## <a name="see-also"></a>Vedere anche
[Esercitazione: creare un flusso del processo di business per standardizzare i processi](create-business-process-flow.md) </br>
[Cosa sono le app Canvas in PowerApps?](/powerapps/maker/canvas-apps/getting-started)


