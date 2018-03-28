---
title: Note sulla versione | Microsoft Docs
description: Problemi comuni e novità delle versioni di Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/12/2018
ms.author: stepsic
ms.openlocfilehash: 4d88b0baee16fb0aeea24e2f2c84806595f21662
ms.sourcegitcommit: 753d52fa29d04f2eb774f7bec29b8d5793ccbb93
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2018
---
# <a name="release-notes"></a>Note sulla versione
## <a name="top-questions"></a>Domande principali
1. Il flusso non è riuscito. Come correggerlo?
   
   1. Identificare l'errore. Iniziare selezionando l'icona delle notifiche nella parte superiore del portale Web oppure la scheda **Attività** nell'app per dispositivi mobili. Selezionare il flusso visualizzato.
   2. Sono ora visibili i dettagli del flusso. Trovare il passaggio contrassegnato dall'icona di punto esclamativo rosso per vedere il messaggio di errore relativo al flusso.
   3. A seconda del messaggio di errore, dovrebbe essere possibile **modificare** il flusso e correggerlo. [Altre informazioni su come correggere gli errori comuni del flusso](fix-flow-failures.md).
2. Come si usa una condizione avanzata o un'espressione?
   
   * Leggere le informazioni su come [aggiungere condizioni](add-condition.md).
   * Se si vogliono più casi in un flusso, è fare clic su o toccare **Aggiungi condizione** dall'interno di una condizione esistente.
   * Creare un'espressione avanzata facendo riferimento a [una funzione in App per la logica](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Come funzionano le licenze con Office 365?
   
   * Gli utenti di Office 365 ottengono l'accesso completo attraverso il piano Microsoft Flow per Office 365. Per altre informazioni, vedere i [piani tariffari per Microsoft Flow](https://flow.microsoft.com/pricing/).
   * Gli amministratori potranno consultare le informazioni sulle [licenze per Microsoft Flow](organization-q-and-a.md), tra cui Office 365.

## <a name="known-issues-and-resolutions"></a>Problemi noti e soluzioni
1. Gli elenchi di SharePoint nei siti personali che non rientrano nella categoria *Elenco personalizzato* non sono supportati. Per risolvere il problema, creare un elenco personalizzato in un sito di SharePoint standard.
2. I flussi non possono effettuare operazioni di scrittura nei campi di tassonomia degli elenchi di SharePoint. Finché non viene corretta questa situazione, è consigliabile utilizzare un campo a stringa semplice.
3. I trigger di file non verranno generati per i file aggiunti nelle cartelle annidate all'interno della cartella selezionata.

## <a name="whats-new"></a>Novità

### <a name="release-2018-02-09"></a>Versione 09-02-2018

- **Disponibilità elevata del gateway**: creare cluster a disponibilità elevata di gateway di gestione dati locali per mantenere connessioni attive in caso di malfunzionamento di singoli computer.
- **Miglioramento di Applica a ogni**: con Microsoft Flow - Piano 1 e Piano 2 è possibile elaborare fino a 100.000 elementi in una singola esecuzione e 50 azioni in parallelo in cicli Applica a ogni. 

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) su questa versione.

### <a name="release-2018-01-29"></a>Versione 29-01-2018

- **Flussi all'interno di Microsoft Teams**: da Teams è possibile creare e gestire flussi, esaminare le approvazioni ricevute e inviate e avviare i flussi direttamente all'interno dell'app desktop Teams o in teams.microsoft.com - [vedere qui per altre informazioni](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Notifiche di modifiche condivise**: ogni volta che un flusso personale viene modificato da un collega, si riceverà una notifica tramite posta elettronica con indicazione di chi ha modificato quale flusso.
- **Nuove espressioni**: sono stati aggiunti due nuovi set di espressioni: uno per analizzare gli URL e un altro per gestire gli oggetti JSON.
- **Tre nuovi connettori**: questa settimana sono disponibili due nuovi connettori Plumsail: Plumsail SP e Plumsail Forms e un nuovo connettore per kintone.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) su questa versione.

### <a name="release-2018-01-17"></a>Versione 17-01-2018

- **Informazioni sul profilo di Office 365**: sono state aggiunte nuove azioni per il connettore Utenti di Office 365 utilizzabili con i profili utente e le foto.
- **Aggiunta a variabili stringa**: è possibile aggiungere stringhe all'interno di cicli per creare tabelle o altri elenchi.
- **Connettore Infobip**: Infobip è un servizio che supporta comunicazioni di livello aziendale, inclusi chiamate vocali e trigger per SMS in ingresso.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/o365-profile-infobip/) su questa versione.

### <a name="release-2017-12-20"></a>Versione 2017-12-20

Microsoft Flow Analytics è ora disponibile in tutte le aree di Microsoft Flow ed è quindi possibile ottenere altre informazioni dettagliate sull'integrità dei flussi in esecuzione nell'ambiente specifico.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) su questa versione.


### <a name="release-2017-12-14"></a>Versione 2017-12-14

- **Miglioramenti al connettore di Outlook**: è possibile salvare un messaggio di posta elettronica come file con estensione "eml", rispondere automaticamente a inviti del calendario e attivare flussi quando si è citati in un thread di posta elettronica.
- **Miglioramenti alle connessioni**: Microsoft Flow memorizza le connessioni usate più di recente e mostra tutti i connettori appena aggiunti.
- **Cinque nuovi connettori**: sono ora disponibili le istanze di contenitore di Azure, Azure Kusto, Metatask, Microsoft To-Do e Plumsail Documents.
- **Miglioramenti per HTTP**: l'azione HTTP supporta ora la codifica Chunked.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/outlook-connector-more/) su questa versione.

### <a name="release-2017-12-05"></a>Versione 2017-12-05

Il pannello di avvio di Microsoft Flow è ora disponibile in tutte le aree. Questo pannello consente di aggiungere valori a un flusso quando lo si esegue all'interno di un elenco di SharePoint o di una raccolta documenti.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) su questa versione.


### <a name="release-2017-11-28"></a>Versione 2017-11-28

- **Metadati gestiti**: è possibile leggere dati da e scrivere dati in colonne in SharePoint che usano il tipo metadati gestiti, definito anche tassonomia.
- **Accodamento alle matrici**: è possibile aggiungere elementi alla fine delle matrici usando una nuova azione Accoda a variabile di matrice.
- **Tago**: è disponibile un nuovo connettore per Tago, che semplifica la connessione di dispositivi elettronici con dati esterni per migliorare il processo decisionale tramite l'analisi contestuale.
- **iPhone X**: è disponibile una nuova versione dell'app Microsoft Flow che usa interamente lo schermo di iPhone X e offre miglioramenti alla velocità di caricamento delle immagini.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/managed-metadata-tago/) su questa versione.

### <a name="release-2017-11-09"></a>Versione 2017-11-09

- **Integrazione per OneDrive for Business**: è ora disponibile [un pulsante per Flow in OneDrive for Business](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) che consente di creare o attivare flussi su cartelle o file selezionati.
- **Trigger per lo strumento di pianificazione**: è possibile avviare flussi quando viene creata una nuova attività, quando un'attività viene assegnata a un utente o quando viene completata un'attività.
- **Allegati di SharePoint**: è possibile usare gli allegati nelle voci elenco di SharePoint, ovvero elencare, scaricare, aggiungere o eliminare allegati.
- **Connettore per la gestione dei flussi**: è possibile creare flussi che automatizzano la gestione di altri flussi nell'ambiente, ad esempio per aggiungere automaticamente autorizzazioni ai flussi.
- **Quattro nuovi connettori**: sono ora disponibili il Servizio visione artificiale personalizzato di Azure, D&B Optimizer, Enadoc e Derdak SIGNL4. 
- **Altre azioni del connettore**: è possibile eseguire query SQL, ottenere trigger di posta elettronica più veloci, usare qualsiasi metodo con HTTP con Azure AD e altro ancora.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) su questa versione.

### <a name="release-2017-11-02"></a>Versione 2017-11-02

- **Log di controllo**: gli eventi di controllo di Microsoft Flow sono ora disponibili nel Centro sicurezza e conformità di Office 365 per tutti i tenant.
- **Correzioni ai widget di Flow**: è stato risolto un problema nell'app per dispositivi mobili Flow che provocava il mancato caricamento dei pulsanti nel widget.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/security-and-compliance-center/) su questa versione.

### <a name="release-2017-10-19"></a>Versione 2017-10-19

- **Aggiunta annidata a ogni elemento**: è possibile aggiungere azioni Applica a ogni, filtrare e selezionare in altre azioni sui contenitori di tipo Applica a ogni.
- **Azioni data/ora**: sono disponibili nuove azioni per ottenere l'ora locale e per l'aggiunta, la sottrazione o la formattazione degli orari.
- **Quattro nuovi connettori**: sono ora disponibili Content Moderator, Docparser, Microsoft Kaizala e Pitney Bowes Data Validation.
- **Esperienza di connessione migliorata**: nel portale di Flow vengono visualizzate notifiche quando una connessione viene interrotta e vengono mostrate informazioni più dettagliate sulla connessione.
- **Raccolta disponibile ovunque**: è disponibile una nuova raccolta di modelli per [i dipendenti ovunque si trovino](https://flow.microsoft.com/collections/onthego/).
- **Input per il pulsante Indirizzo di posta elettronica**: è possibile raccogliere gli indirizzi di posta elettronica dagli utenti quando eseguono i pulsanti.
- **Input per il pulsante File**: è possibile ottenere i file caricati, ad esempio foto, dagli utenti quando eseguono i pulsanti.
- **Prima esecuzione e accesso automatico**: le esperienze relative alla prima esecuzione sono state migliorate nell'app per dispositivi mobili ed è ora disponibile l'accesso automatico.
- **Trigger più veloci per Microsoft Forms**: Forms attiverà i flussi in modo molto più rapido rispetto al passato, ovvero più di una volta all'ora.
- **Input dei pulsanti tra le sessioni**: i pulsanti attivati sul telefono cellulare memorizzeranno gli input precedenti.
- **Feed delle attività per dispositivi mobili**: il feed delle attività è stato migliorato per includere riepiloghi delle esecuzioni più dettagliati e informazioni più precise per la risoluzione dei problemi.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/nested-apply-to-each/) su questa versione.

### <a name="release-2017-10-03"></a>Versione 2017-10-03

- **Approvazione necessaria da parte di tutti**: è possibile richiedere che una richiesta di approvazione inviata a più persone debba essere approvata da tutti gli utenti che l'hanno ricevuta.
- **Nuove azioni per OneDrive for Business**: è possibile generare file PDF per i file archiviati in OneDrive for Business ed eseguire quattro nuove azioni.
- **Connettore per Apache Impala**: Apache Impala (incubating) è il database di analisi nativo open source per Apache Hadoop.
- **Aggiunta di descrizioni dei flussi**: è possibile specificare descrizioni per i flussi in modo che i colleghi possano visualizzare un riepilogo delle funzionalità del flusso in caso di condivisione.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) su questa versione.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Versione 2017-09-25 - Aggiornamento del terzo trimestre per Microsoft Flow

- **Maggiore integrazione con SharePoint nella prima versione**: sono disponibili nuovi flussi predefiniti per l'invio per la revisione e un pannello di Flow per la raccolta di input in caso di esecuzione di un flusso per i tenant della prima versione.
- **Dynamics 365 for Customer Engagement**: Flow è ora integrato nell'interfaccia utente di Dynamics 365 for Customer Engagement.
- **Microsoft Trust Center**: Flow è elencato in Microsoft Trust Center, che include certificazioni come HIPAA, ISO e SOC.
- **Analisi di utilizzo**: ogni flusso ha un dashboard di Power BI incorporato con analisi di utilizzo di base.
- **Log di controllo nella prima versione**: tutti gli eventi di gestione dei flussi vengono registrati nel Centro sicurezza e conformità di Office 365 per i tenant della prima versione.
- **Sei nuovi connettori**: sono ora disponibili LinkedIn, gruppi di Office 365, Skype for Business, Adobe Sign, Bizzy e la raccolta dati di Azure Log Analytics.
- **Trigger SQL**: è possibile eseguire flussi quando viene aggiunta una nuova riga o quando viene aggiornata una riga in una tabella SQL.
- **Connettori locali personalizzati**: i connettori personalizzati possono ora usare il gateway dati locale per la connessione agli endpoint interni sulla rete.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/q3-2017-update/) su questa versione.

### <a name="release-2017-09-21"></a>Versione 2017-09-21

- **Download della cronologia dei flussi**: è possibile scaricare la cronologia di esecuzione di un flusso come file CSV da aprire in Excel.
- **Ricorrenza avanzata**: è possibile creare pianificazioni ricorrenti per attivare i flussi, ad esempio per l'attivazione solo nei giorni feriali.
- **IntelliSense**: quando si digita un'espressione, IntelliSense fornirà suggerimenti per i parametri.
- **Quattro nuovi connettori**: sono ora disponibili connettori per i servizi HTTP di Azure AD, Amazon Redshift, Pubblicazione della Griglia di eventi di Azure e FlowForma.
- **Condivisione dei collegamenti**: è disponibile una nuova azione per la generazione di collegamenti condivisibili per file di OneDrive o per BLOB di archiviazione di Azure.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/download-history-recurrence/) su questa versione.


### <a name="release-2017-08-25"></a>Versione 2017-08-25
* **Proprietà del documento e altro ancora per SharePoint** - [Possibilità di eseguire la lettura e di impostare le proprietà della raccolta documenti di SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/) e di usare campi aggiuntivi, ad esempio collegamenti all'elemento di SharePoint.
* **Raccolte di flussi**: le raccolte di flussi sono un set di raccolte di modelli organizzate in base al ruolo o al mercato verticale.
* **Ricondivisione di pulsanti**: quando si condividono pulsanti con i colleghi, questi possono condividerli a loro volta con altre persone.
* **Raccolta di elenchi dai pulsanti**: è possibile definire menu a discesa di opzioni che possono essere scelte dagli utenti quando toccano il pulsante.
* **Sette nuovi connettori**: AWeber, Azure Log Analytics, Tabelle di Azure, DocFusion365, Griglia di eventi di Azure, Hub eventi di Azure e StaffHub. 
* **Miglioramenti a Slack e MySQL**: è possibile creare o unire canali in Slack ed eseguire la scrittura dei dati in database MySQL.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/button-updates-seven-connectors/) su questa versione.

### <a name="release-2017-08-02"></a>Versione 02-08-2017
* **Scrivere nei campi Persona, Opzione e Ricerca**: le opzioni Crea elemento e Aggiorna elemento di SharePoint [ora supportano la possibilità di impostare](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) campi Persona, Opzione e Ricerca.
* **Altre impostazioni azione**: l'utente ha ora maggiore controllo sulla modalità di esecuzione di azioni e trigger, inclusi i criteri dei tentativi di configurazione e la paginazione.
* **Quattro nuovi connettori**: è ora possibile usare Archiviazione file di Azure, Elastic Forms, Plivo e Video Indexer.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/four-connector-action-settings/) su questa versione.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Versione 27-07-2017 - Aggiornamento secondo trimestre per Microsoft Flow
* **Importazione ed esportazione**: è possibile importare ed esportare soluzioni di flusso tra ambienti o dall'ambiente di test a quello di produzione. 
* **Uso di espressioni nelle azioni**: è possibile immettere espressioni in qualsiasi azione e visualizzare la Guida in linea per usarle.
* **Passaggio alle App per la logica di Azure**: è possibile salvare i flussi come risorsa App per la logica di Azure che può essere distribuita in Visual Studio o nel portale di Azure.
* **Visibilità dell'amministratore**: è possibile scaricare l'utilizzo di Microsoft Flow nel tenant per comprendere esattamente dove e come vengono usati i flussi.
* **Flussi in Dynamics 365**: è possibile usare i flussi di Dynamics 365 per le Operations & Financials, Business Edition.
* **Trovare più facilmente gli scenari**: è possibile esplorare tutte le operazioni possibili con il connettore e quindi usare qualsiasi trigger come punto di partenza per la creazione di flussi.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/q2-2017-update/) su questa versione.

### <a name="release-2017-07-13"></a>Versione 07-13-2017
* **Pubblicazione modelli migliorata**: è possibile pubblicare qualsiasi flusso creato, assieme alle relative categorie, nella raccolta pubblica.
* **Ricevere gli eventi nel calendario di Outlook**: una nuova azione che consente di restituire tutti gli eventi tra due orari nel calendario.
* **Nuove funzionalità per dispositivi mobili**: è possibile eseguire flussi su richiesta e inviare di nuovo le esecuzioni non riuscite nell'app mobile.
* **Menu a discesa dinamici nei connettori personalizzati**: è possibile creare elenchi a discesa dinamici, trigger di polling e testare i connettori personalizzati.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) su questa versione.

### <a name="release-2017-06-28"></a>Versione 28-06-2017
* **Aggiornare le impostazioni relative alla lingua**: è possibile personalizzare la lingua e l'area usate da Microsoft Flow tramite il menu Impostazioni.
* **Cinque nuovi connettori**: è stato aggiunto il supporto per Adobe Creative Cloud, Bing Maps, Bing Search, JotForm e Freshservice.
* **Configurare i timeout**: è possibile modificare la durata dell'esecuzione delle azioni di lunga durata, ad esempio le approvazioni, prima del "timeout" e della continuazione del flusso.
* **Includere commenti in Outlook per l'approvazione**: quando si riceve una richiesta di approvazione, è possibile fornire commenti senza dover uscire da Outlook.
* **Colori personalizzati per i connettori personalizzati**: è ora possibile immettere un colore da usare per gli sfondi dei connettori personalizzati.
* **Salvare come flussi del team**: è possibile creare copie di qualsiasi flusso, inclusi i flussi del team.
* **Eliminare le informazioni sui flussi**: quando si elimina un flusso, verrà visualizzato l'elenco di tutte le esecuzioni in sospeso per tale flusso.
* **Filtri nella pagina Connettori**: è possibile cercare connettori specifici nella pagina Connettori e applicare filtri in base al tipo di connettore.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/language-settings-3-connectors/) su questa versione.

### <a name="release-2017-06-19"></a>Versione 19-06-2017
È ora possibile visualizzare lo stato di tutte le richieste di approvazione in sospeso inviate. È anche possibile esplorare e gestire tutte le approvazioni in sospeso direttamente dal dispositivo mobile.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) su questa versione.

### <a name="release-2017-06-15"></a>Versione 15-06-2017
* **Conversione del contenuto**: è disponibile un nuovo connettore che consente di convertire il contenuto HTML in testo normale, operazione utile per la gestione dei messaggi di posta elettronica con formattazione HTML.
* **Tre nuovi connettori di database**: è stato aggiunto il supporto di sola lettura per MySQL, PostgreSQL e Teradata. Questi connettori si connettono tramite il gateway dati locale.
* **Altri tre connettori**: è possibile connettersi ad Azure Application Insights, Calendly e Teamwork Projects.
* **Migliore visualizzazione per la gestione degli errori**: le procedure eseguite dopo gli errori vengono ora visualizzate con frecce tratteggiate rosse, per semplificarne l'identificazione.
* **Riquadro relativo ai dettagli dell'esecuzione**: in caso di errore di un flusso, è ora disponibile un nuovo riquadro a destra che include alcune procedure utili per la risoluzione dei problemi del flusso.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/seven-connectors-and-html/) su questa versione.

### <a name="release-2017-06-04"></a>Versione 04-06-2017
* **Disponibilità generale per Windows Phone** - [ l'app per dispositivi mobili Microsoft Flow è ora disponibile a livello generale per Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Messaggi di posta elettronica relativi agli errori dei flussi**: è possibile ricevere notifiche tramite posta elettronica in caso di errori di un flusso. I messaggi di posta elettronica relativi agli errori verranno inviati solo una volta alla settimana e possono essere attivati o disattivati dall'utente.
* **Selezionare l'azione per le tabelle**: usare la nuova azione di selezione per modificare il set di colonne da includere nelle tabelle.
* **Connettore per Microsoft Forms**: Microsoft Forms è una novità di Office 365 Education, che consente a docenti e studenti di creare in modo semplice e rapido quiz, sondaggi, questionari, registrazioni e altro ancora.
* **Piano Office 365 Enterprise K1**: PowerApps e Microsoft Flow sono ora inclusi nel piano Office 365 Enterprise K1, con quote specifiche.
* **Intestazioni HTTP più facili**: analogamente all'azione di selezione, è possibile specificare un nome e un valore per l'intestazione compilando semplicemente le caselle di testo relative all'azione.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) su questa versione.

### <a name="release-2017-05-23"></a>Versione 23-05-2017
* **Connettore Microsoft Teams** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) è un'area di lavoro basata su chat in Office 365 che riunisce persone, conversazioni e contenuti, insieme agli strumenti necessari al team, che permette di collaborare più facilmente e conseguire risultati migliori.
* **Widget in iOS e Android**: i widget di Microsoft Flow sono collegamenti a pulsanti che consentono di attivare un pulsante in modo più semplice e rapido direttamente dalla schermata iniziale.
* **Creare passaggi di "gestione degli errori"**: è possibile definire uno o più passaggi da eseguire dopo l'esito negativo di un'operazione. Ad esempio, si può ricevere immediatamente una notifica se il flusso non riesce a creare un record in Dynamics 365.
* **Variabili integer e float**: è possibile inizializzare e incrementare o ridurre i contatori all'interno di un'esecuzione del flusso per contare il numero di esecuzioni di un determinato set di logica.
* **Pagina dei dettagli del flusso**: quando si seleziona un flusso nell'elenco **Flussi personali**, verrà visualizzata una pagina con informazioni dettagliate su tale flusso, ad esempio chi ha accesso e la cronologia di esecuzione.
* **Quote di esecuzione del flusso per gli amministratori**: gli amministratori possono ora monitorare l'utilizzo dell'esecuzione del flusso nell'intera organizzazione rispetto alla quota di esecuzione aziendale comune e ottenere una suddivisione della quota, per meglio comprendere quali licenze contribuiscono alla loro quota.
* **Miglioramenti del trigger di richiesta HTTP**: è possibile usare metodi HTTP diversi e aggiungere segmenti di percorso per il trigger della richiesta.
* **Connettori di due partner**: Microsoft Flow può ora connettersi a Parserr, un servizio di analisi della posta elettronica, e a Cognito Forms, un servizio di form online.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/error-handling/) su questa versione.

### <a name="release-2017-05-12"></a>Versione 12-05-2017
* **Integrazione di raccolte documenti di SharePoint**: è possibile selezionare qualsiasi file in una raccolta documenti e avviare un flusso, ad esempio per inviarlo al gestore per l'approvazione, [e molto altro](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Connettore di Microsoft Planner**: Microsoft Planner consente di unire con facilità team, attività, documenti e conversazioni per risultati migliori.
* **Visualizzazione amministratore delle licenze**: gli amministratori possono visualizzare tutte le licenze di Microsoft Flow e PowerApps (sia la versione di valutazione che quella a pagamento) nell'Interfaccia di amministrazione di Microsoft Flow.
* **Piano della community di PowerApps**: il piano della community di PowerApps è un piano gratuito che permette ai singoli utenti di esplorare, imparare e ottimizzare le competenze per PowerApps, Microsoft Flow e Common Data Service.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/planner-community-and-licenses/) su questa versione.

### <a name="release-2017-05-09"></a>Versione 09-05-2017
* **Connettore Azure AD**: esiste un nuovo connettore per l'esecuzione di azioni di amministrazione da Microsoft Flow, tra cui la creazione di utenti o la loro aggiunta ai gruppi.
* **Miglioramenti per Outlook di Office 365**: è ora possibile attivare i flussi dalle Cassette postali condivise e inviare messaggi a una Cassetta postale condivisa. È anche possibile impostare o leggere le risposte automatiche.
* **Disponibile in Canada**: è ora possibile creare flussi personalizzati in Canada.
* **Creare webhook delle API personalizzate**: gli sviluppatori di connettori personalizzati ora possono aggiungere trigger alle API personalizzate con i webhook.
* **Gestire i proprietari del flusso nell'interfaccia di amministrazione**: gli amministratori dell'ambiente possono gestire i proprietari del flusso nell'interfaccia di amministrazione di Microsoft Flow.
* **Documentazione di riferimento dei connettori**: è ora disponibile una [documentazione completa di riferimento sui connettori in docs.microsoft.com](https://docs.microsoft.com/Connectors/).
* **Due servizi partner**: sono stati rilasciati due nuovi servizi partner, Nexmo e Paylocity.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/canada-mailboxes-aad) su questa versione.

### <a name="release-2017-04-27"></a>Versione 27-04-2017
* **Creare flussi con passaggi paralleli**: è possibile creare flussi con l'esecuzione parallela, vale a dire che si possono eseguire due o più passaggi esattamente nello stesso momento.
* **Cinque nuovi servizi supportati**: Approvazioni, Benchmark Email, Capsule CRM, LiveChat e Outlook Customer Manager.
* **Monitorare i tentativi di azioni**: Microsoft Flow eseguirà nuovi tentativi quando si verificano errori con i servizi. Ora è possibile vedere quanti tentativi automatici sono stati eseguiti e i dettagli su ciò che si è verificato.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/parallel-actions/) su questa versione.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Versione 17-04-2017 - Aggiornamento primo trimestre per Microsoft Flow
* **Esperienze moderne di approvazione**: creare flussi di lavoro in cui gli approvatori possano approvare in modo sicuro all'interno dell'app per dispositivi mobili Microsoft Flow o dal centro approvazioni unificato sul sito Web di Microsoft Flow.
* **Disponibilità generale dei flussi del team**: più persone possono possedere e gestire un flusso insieme ai flussi del team, che ora sono generalmente disponibili.
* **Creare connettori per Microsoft Flow**: chiunque può inviare il proprio connettore Microsoft Flow gratuitamente perché tutti possano usarlo.
* **Finestra di progettazione semplificata**: per alcuni modelli, una nuova versione della finestra di progettazione presenta solo i campi necessari a creare un flusso, semplificandone l'uso.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/q1-2017-update/) su questa versione.

### <a name="release-2017-04-11"></a>Versione 11-04-2017
* **Nuove azioni per creare tabelle ed elenchi**: nuove azioni Crea tabella HTML, Crea tabella CSV e Aggiungi che possono elaborare elenchi di elementi (anziché l'unica azione precedente Applica a ogni).
* **Inserire passaggi ovunque**: è ora possibile inserire un nuovo passaggio in qualsiasi punto nel flusso di lavoro senza la necessità di eseguire il trascinamento e rilascio.
* **Quattro nuovi servizi**: Flow supporta ora 10 to 8 Scheduling, Act!, Inoreader e l'API Visione artificiale. Con l'API Visione artificiale è possibile elaborare immagini per catturarne il contenuto testuale (operazione nota come OCR, riconoscimento ottico dei caratteri) o per aggiungere automaticamente tag alle immagini in base al loro contenuto.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) su questa versione.

### <a name="release-2017-04-03"></a>Versione 03-04-2017
* **Versione Beta di Windows Phone**: è disponibile la versione beta del programma Windows Phone App per ottenere un'anteprima dell'app di Windows Phone. [Altre informazioni](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **Muhimbi PDF**: è ora possibile convertire file Microsoft Word in formato PDF, aggiungere filigrane, unire i documenti e altro ancora con Muhimbi PDF. [Altre informazioni](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Attivare flussi dai pulsanti fisici**: si annuncia la partnership con due prodotti principali nello spazio del pulsante fisico: Flic di Shortcut Labs e Bttn di The Button Corporation. [Altre informazioni](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Versione 22-03-2017
* **Creare una copia del flusso di**: è ora possibile eseguire una copia del flusso per lavorare su versioni bozza o duplicare un flusso creato in precedenza.
* **Due nuovi servizi**: aggiunto il supporto per Toodledo, che consente di gestire l'elenco attività con la creazione e l'aggiornamento di attività, e Zendesk, che fornisce un servizio clienti e supporta una piattaforma di ticketing.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/make-a-copy/) su questa versione.

### <a name="release-2017-03-15"></a>Versione 15-03-2017
* **Condividere i pulsanti con i colleghi**: è ora possibile condividere i pulsanti di un flusso con altri utenti, rendendo più semplice per qualsiasi utente aziendale eseguire operazioni rapide.
* **Attivare i pulsanti dalla schermata iniziale**: i collegamenti ai pulsanti di un flusso dalla schermata iniziale e da quella di blocco dei dispositivi mobili accelerano più che mai l'attivazione di un flusso.
* **Flussi dei team nell'app Microsoft Flow**: è ora possibile visualizzare i flussi che hanno altri proprietari nell'app Microsoft Flow per iOS o Android.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/button-sharing/) su questa versione.

### <a name="release-2017-03-10"></a>Versione 03-10-2017
* **Migliore esperienza di connettore personalizzato**: è ora possibile usare una raccolta Postman per creare un connettore personalizzato, quindi modificare, aggiungere e verificare le azioni.
* **Due nuovi servizi**: aggiunto il supporto per PowerApps Notifications e PivotalTracker.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/new-updates-custom-api/) su questa versione.

### <a name="release-2017-02-27"></a>Versione 27-02-2017
* **Attivare i pulsanti di flusso**: è ora possibile attivare i pulsanti flusso direttamente dal sito Web di Microsoft Flow. Quando si esamina l'elenco dei flussi, è sufficiente selezionare il menu "..." e scegliere il comando Esegui ora.
* **Cinque nuovi servizi**: aggiunto il supporto per Oracle Database, Intercom, FreshBooks, LeanKit e WebMerge.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) su questa versione.

### <a name="release-2017-02-21"></a>Versione 21-02-2017
* **Visualizzare i flussi di ambiente**: gli amministratori di ambiente possono ora visualizzare l'elenco completo di tutti i flussi all'interno di un determinato ambiente, nonché abilitare, disabilitare o eliminare i flussi.
* **Due nuovi servizi**: aggiunto il supporto per Automazione di Azure e Basecamp 2.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) su questa versione.

### <a name="release-2017-02-16"></a>Versione 16-02-2017
* **Cinque nuovi servizi**: aggiunto il supporto per Azure Data Lake, Bitbucket (un servizio di hosting basato su Web per i progetti che usano il controllo delle revisioni GIT), Eventbrite, Infusionsoft e Pipedrive.
* **Autenticazione HTTP personalizzata**: nella finestra di progettazione del flusso è ora possibile usare l'autenticazione con gli endpoint HTTP personalizzati.
* **Analizzare i messaggi JSON**: è possibile analizzare i dati JSON dal trigger Richiesta HTTP o che vengono restituiti dall'azione HTTP.
* **Filtro dell'esecuzione del flusso**: migliorati i filtri per le esecuzioni del flusso, con opzioni più specifiche che includono la visualizzazione di flussi in esecuzione o esecuzioni annullate.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) su questa versione.

### <a name="release-2017-02-06"></a>Versione 06-02-2017
* **Flusso del team**: i flussi del team consentono di condividere la proprietà e la gestione di un flusso tra più persone in modo che, se qualcuno lascia l'organizzazione, i flussi creati continuino a essere eseguiti.
* **Condivisione di connettori personalizzati**: i connettori personalizzati, come i flussi dei team, possono essere condivisi e gestiti collettivamente all'interno di un'organizzazione.
* **Supporto per Gmail e LUIS**: connessione a Gmail e a LUIS (Language Understanding Intelligent Service) di Servizi cognitivi di Azure.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/team-flows/) su questa versione.

### <a name="release-2017-01-30"></a>Versione 30-01-2017
* **Input dei pulsanti Flow**: i pulsanti Flow ora possono ricevere gli input dell'utente in fase di esecuzione, quindi gli autori del flusso possono definire le informazioni passate quando viene usato il pulsante.
* **Attività di Outlook e HelloSign**: il servizio Attività di Outlook consente di gestire le attività, mentre HelloSign abilita la funzionalità di firma elettronica protetta.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/button-user-inputs/) su questa versione.

### <a name="release-2017-01-23"></a>Versione 23-01-2017
* **Ricerca in base al servizio** -Eseguire ricerche in base al servizio quando si aggiunge un trigger o un'azione per vedere tutte le azioni per ogni servizio.
* **Switch case** - Aggiungere blocchi Switch per avere diversi rami di logica parallela.
* **Più azioni di posta elettronica** -Nuove funzionalità nei servizi Office 365 Outlook e Outlook.com per lavorare con messaggi di posta elettronica contrassegnati.
* **Cinque nuovi servizi**- Connessione a file system di rete o locali, servizio di pagamento Stripe, IBM Informix, IBM DB2 e UserVoice.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/search-by-service/) su questa versione.

### <a name="release-2017-01-14"></a>Versione 14-01-2017
* **Inviare di nuovo le esecuzioni** - Se un flusso ha restituito un errore che si vuole risolvere per rieseguire il flusso, è possibile inviare di nuovo l'esecuzione non riuscita.
* **Annullare le esecuzioni** - Quando un flusso si blocca è ora possibile annullare esplicitamente l'esecuzione.
* **Due nuovi servizi** - È stato aggiunto il supporto per GoToTraining e GoToWebinar.
* **Collegamenti mobili** - È possibile condividere modelli direttamente dall'app per dispositivi mobili ed è stato aggiunto un collegamento di download veloce per le app nella parte superiore del sito Web.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/managing-runs/) su questa versione.

### <a name="release-2016-12-29"></a>Versione 29-12-2016
Microsoft Flow supporta ora DocuSign, per gestire eSignature e Digital Transaction Management, SurveyMonkey, per i sondaggi basati sul Web, e l'app per prendere appunti OneNote (solo account aziendali).

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/final-2016-services/) su questa versione.

### <a name="release-2016-12-20"></a>Versione 20-12-2016
* **Esegui ora**: è ora possibile attivare un trigger ricorrente su richiesta; ad esempio, se è pianificata l'esecuzione di un report ogni giorno, ma è necessario eseguirlo anche **ora**.
* **Sei nuovi servizi** - Creare flussi che si connettano a MSN Meteo, Medium, Contatti Google, Buffer, Harvest e TypeForm.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/run-now-and-six-more-services/) su questa versione.

### <a name="release-2016-12-14"></a>Versione 14-12-2016
È ora possibile sfruttare informazioni utili quando si attiva un flusso del pulsante, ad esempio da dove è stato attivato il pulsante, da chi, a che ora e altro ancora.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/button-trigger-tokens/) su questa versione.

### <a name="release-2016-12-06"></a>Versione 06-12-2016
* **Introduzione alla formazione guidata** - Introduzione a una raccolta di corsi in sequenza che abbinano video a documentazione per presentare le funzionalità complete e potenti di Microsoft Flow.
* **Due nuovi servizi** - Nei flussi è ora possibile usare Freshdesk, una soluzione per l'assistenza ai clienti, e GoToMeeting, uno strumento per riunioni online.
* **Supporto di webhook HTTP** - Un flusso può ora essere un endpoint per webhook con registrazione e annullamento della registrazione automatici.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/guided-learning-and-two-services/) su questa versione.

### <a name="release-2016-11-23"></a>Versione 23-11-2016
* **Supporto degli avvisi di Power BI in Flow** - Trasformare le informazioni dettagliate in azioni attivando i flussi da avvisi dati di Power BI.
* **Miglioramenti dell'applicazione per dispositivi mobili** - È stata aggiunta la possibilità di creare flussi da zero, oltre all'esperienza già esistente di creazione da modelli. Sono state inoltre migliorate le prestazioni per la visualizzazione delle esecuzioni dei flussi.
* **Otto nuovi servizi** - È ora possibile connettersi ad Azure Resource Manager, code di Azure, Chatter, Disqus, Azure Cosmos DB, API Face di Servizi cognitivi, HipChat e Wordpress.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) su questa versione.

### <a name="release-2016-11-15"></a>Versione 15-11-2016
* **Programma per i partner Microsoft Flow** - Per Microsoft Flow esiste ora una programma per partner certificati pensato per promuovere lo sviluppo di relazioni e sfruttare talenti ed esperienze con Microsoft Flow di diverse aziende in tutto il mondo.
* **Sei nuovi servizi** - Questa settimana verranno anche rilasciati sei servizi: Asana, Campfire, EasyRedmine, JIRA, Redmine e Vimeo.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/partner-program-six-new-services/) su questa versione.

### <a name="release-2016-10-31---general-availability"></a>Versione 31-10-2016: disponibilità generale
* **Prezzi e licenze**: sono ora disponibili il piano gratuito e il piano a pagamento e il prodotto è incluso in Office 365 e Dynamics 365.
* **Interfaccia di amministrazione di Microsoft Flow**: grazie alla nuova interfaccia di amministrazione, la soluzione è ora dedicata alle aziende. Nell'interfaccia di amministrazione è possibile gestire gli ambienti all'interno dell'organizzazione.
* **Criteri di prevenzione della perdita dei dati**: gli amministratori possono creare criteri di prevenzione della perdita di dati per controllare il flusso di dati tra i servizi.
* **Disponibilità di Android**: l'app Microsoft Flow per telefoni è ora disponibile sia per iOS che per Android. L'app consente di ricevere notifiche, monitorare l'attività e avviare flussi con il semplice tocco di un pulsante.
* **Nuove esperienze di finestra di progettazione**: ora è possibile effettuare ricerche nei contenuti dinamici trasmessi di passaggio in passaggio, di conseguenza è più rapido consultare i dati desiderati.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/announcing-ga/) su questa versione.

### <a name="release-2016-10-26"></a>Versione 26-10-2016
* **Flussi di un pulsante**: molte operazioni servono in qualsiasi momento e da qualsiasi dispositivo. Ora, grazie ai flussi di un pulsante, è possibile eseguirle con il semplice clic di un pulsante su dispositivo mobile.
* **Annuncio degli ambienti**: gli ambienti sono spazi distinti in cui archiviare e gestire i flussi dell'organizzazione. Gli ambienti sono distribuiti geograficamente, il che significa che i flussi, le app e i dati aziendali che risiedono in un ambiente si troveranno nell'area geografica in cui si trova l'ambiente.
* **Sei nuovi servizi**: aggiunta del supporto per Bit.ly, Analisi del testo dei Servizi cognitivi, Dynamics NAV, Dynamics 365 for Financials, Instapaper e Pinterest.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/environments-for-makers/) su questa versione.

### <a name="release-2016-10-16"></a>Versione 16-10-2016
* **I connettori personalizzati supportano altri tipi di autenticazione**: ora i connettori personalizzati supportano l'autenticazione con chiave API e consentono di eseguire l'autenticazione in qualsiasi servizio che supporti la specifica OAuth 2.0 completa.
* **Supporto per tre nuovi servizi**: è stato aggiunto il supporto per Basecamp 3, Blogger e PagerDuty.
* **Miglioramenti della finestra di progettazione**: grazie alle prestazioni migliorate, ora per ogni azione è possibile aggiornare e ripristinare le connessioni direttamente dal menu "..."; è stato inoltre aggiunto un nuovo passaggio per terminare l'esecuzione di un flusso.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/early-october-updates/) su questa versione.

### <a name="release-2016-09-25"></a>Versione 25-09-2016
Ora è possibile creare flussi tramite cellulare. L'utente può esplorare un'ampia raccolta di modelli, consultare l'elenco dei servizi o selezionare una categoria di modelli. [Ulteriori informazioni e domande](https://flow.microsoft.com/blog/mobile-creation/) su questa versione.

### <a name="release-2016-09-22"></a>Versione 22-09-2016
* **Strumento Microsoft per la selezione grafica degli utenti**: il nuovo strumento Microsoft per la selezione degli utenti è integrato direttamente nell'interfaccia utente di Microsoft Flow per consentire di scegliere il contatto o l'indirizzo e-mail corretto.
* **Supporto di Microsoft Dynamics AX**: dall'interno di ogni flusso è ora possibile eseguire operazioni online con i dati di Dynamics AX, dalla creazione di nuovi record all'esecuzione di query sui dati.
* **Due nuovi servizi offerti dai partner**: ora è possibile utilizzare appFigures o Insightly dai flussi.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/more-september-updates/) su questa versione.

### <a name="release-2016-09-14"></a>Versione 14-09-2016
* **Incorporamento nel proprio sito Web o nella propria app**: ora gli sviluppatori possono incorporare Microsoft Flow direttamente nei loro siti Web o app per consentire agli utenti di automatizzare con facilità le attività personali o professionali.
* **Utilizzo di un flusso come endpoint HTTP**: ora è possibile utilizzare un flusso come API HTTP. L'apposito trigger disponibile nel flusso consente di rispondere alla richiesta in ingresso aggiungendo una scheda di risposta.
* **Supporto di Todoist**: Todoist assicura la visibilità di tutti i progetti, professionali e personali.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/extend-web-site-application/) su questa versione.

### <a name="release-2016-09-01"></a>Versione 01-09-2016
Microsoft Flow è ora disponibile per tutti gli utenti. Inizialmente l'anteprima era disponibile solo per gli indirizzi e-mail forniti dall'azienda o dall'istituto di istruzione di ogni utente, ad esempio quelli utilizzati con Office 365 Business oppure Office 365 Enterprise. Oggi l'anteprima è ufficialmente disponibile a titolo gratuito per tutti gli utenti, indipendentemente dall'indirizzo e-mail che utilizzano. [Ulteriori informazioni e domande](https://flow.microsoft.com/blog/available-for-everyone/) su questa versione.

### <a name="release-2016-08-31"></a>Versione 31-08-2016
* **Istruzioni condizionali annidate**: ora è possibile aggiungere una seconda condizione (o terza, ecc.) all'interno di un'altra.
* **Apply to each**: il ciclo apply to each consente di controllare l'elenco a ripetizione.
* **Do-until**: il loop do-until consente di ripetere un passaggio fino al raggiungimento di una determinata condizione.
* **Matrici di filtraggio**: esiste un solo filtro nativo che assicura che ogni elemento dell'elenco corrisponda a un'espressione definita.
* **Composizione delle variabili di stringhe**: ora è possibile comporre una variabile di stringa.
* **Ambiti**: gli ambiti sono un semplice metodo per raggruppare due o più azioni.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/build-advanced-flows/) su questa versione.

### <a name="release-2016-08-27"></a>Versione 27-08-2016
* **Commenti relativi ai passaggi**: con i commenti è possibile inserire annotazioni in ogni singola azione, per poter ricordare i requisiti dei flussi.
* **Supporto Smartsheet**: da questa settimana è possibile collegare Smartsheet, un servizio che consente di collaborare facilmente ai fogli nel cloud.
* **Miglioramenti dell'interfaccia utente durante la creazione di flussi**: ora il nome del flusso appare in primo piano e il pulsante Salva è stato spostato nella parte superiore della pagina per consentire di accedervi facilmente.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/add-comments-smartsheet/) su questa versione.

### <a name="release-2016-08-18"></a>Versione 18-08-2016
È ora possibile visualizzare in anteprima la nuova esperienza degli elenchi di SharePoint Online, in cui è stato integrato Microsoft Flow. [Ulteriori informazioni e domande](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) su questa versione.

### <a name="release-2016-08-13"></a>Versione 13-08-2016
* **Visual Studio Team Services**: con Flow, è ora possibile connettere Visual Studio Team Services a un'ampia gamma di servizi, tra cui l'e-mail di Office 365, Slack, Trello e Wunderlist.
* **Miglioramenti di SharePoint**: gli elenchi SharePoint supportano tutta una serie di tipi di dati, da oggetti semplici come singole righe di testo, data e ora fino a oggetti complessi, come utenti o gruppi, ricerche e scelte.
* **Verifica delle connessioni di Outlook in O365**: ogni nuova connessione di Outlook creata in O365 viene ora testata per verificare che sia utilizzabile.
* **Controllo booleano**: è stato aggiunto un controllo booleano per chiarire quali valori immettere nei campi di input booleani, ad esempio "Has Attachments" nel trigger "When a new email arrives".

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) su questa versione.

### <a name="release-2016-08-08"></a>Versione 08-08-2016
Anteprima pubblica di Microsoft Common Data Service integrata in Microsoft Flow. [Ulteriori informazioni e domande](https://flow.microsoft.com/blog/flow-and-common-data-model/) su questa versione.

### <a name="release-2016-08-05"></a>Versione 08-05-2016
* **SharePoint locale**: come con SharePoint Online, è possibile creare flussi relativi agli elenchi e alle raccolte documenti di SharePoint locale da zero o tramite modelli predefiniti.
* **Messaggi informativi nella finestra di progettazione**: per approfondire le funzionalità di ogni trigger e azione, sono stati aggiunti messaggi informativi per ogni passaggio dei vari flussi.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) su questa versione.

### <a name="release-2016-07-15"></a>Versione 07-15-2016
* **Quattro nuovi servizi aggiunti**: connettersi a Google Calendar, Google Task, YouTube e SparkPost.
* **Ridenominazione delle azioni**: ora è possibile rinominare le varie azioni in modo tale da distinguerle.
* **Ritardo per diversi periodi di tempo**: è ora possibile selezionare qualsiasi numero di secondi, minuti, ore o giorni.
* **Strumento di visualizzazione delle cartelle semplificato**: lo strumento di visualizzazione delle cartelle è stato semplificato; ora selezionando una cartella a sinistra verrà scelta la cartella in questione, mentre selezionandola a destra la cartella verrà aperta e sarà possibile scegliere le sottocartelle al suo interno.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/new-google-services-rename-more/) su questa versione.

### <a name="release-2016-07-08"></a>Versione 07-08-2016
Connettività locale per Microsoft Flow tramite il gateway dati locale. Questa caratteristica consente di stabilire connessioni protette a SQL Server e di integrarle con i flussi. [Ulteriori informazioni e domande](https://flow.microsoft.com/blog/on-premises-data-gateway/) su questa versione.

### <a name="release-2016-07-02"></a>Versione 07-02-2016
* **Supporto per Fogli Google**: in passato era possibile utilizzare Excel e Google Drive, ma questa settimana è stato aggiunto il supporto nativo per Fogli Google.
* **Avvio tramite modelli**: l'avvio tramite l'uso di modelli è stato ottimizzato. Ora è possibile selezionare direttamente nella pagina dei modelli gli account che si desidera utilizzare insieme a un modello.
* **Autorizzazione senza scadenza per SharePoint e Office 365**: ora l'accesso ai servizi basati su Azure Active Directory verrà rinnovato automaticamente tramite Microsoft Flow, pertanto tra le modifiche delle password i flussi continueranno tutti a funzionare.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/more-june-updates/) su questa versione.

### <a name="release-2016-06-20"></a>Versione 06-20-2016
* **Introduzione della nuova app per dispositivi mobili per Microsoft Flow**: da oggi esiste un nuovo importante componente, ovvero un'app per dispositivi mobili da scaricare in iOS (e presto anche in Android) per gestire, monitorare ed esplorare i flussi di lavoro automatizzati ovunque e in qualsiasi momento.  
* **Servizio Single Sign-On**: è stato implementato l'accesso Single Sign-On, che consente di eseguire l'autenticazione in Microsoft Flow con altri servizi Microsoft, come Office 365.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) su questa versione.

### <a name="release-2016-06-18"></a>Versione 06-18-2016
* **Nuovo servizio e-mail**: ora è possibile inviare messaggi e-mail direttamente da Microsoft Flow, senza doversi connettere all'account e-mail di lavoro o personale all'interno di Microsoft Flow.
* **Notifiche sul portale**: ora, ogni volta che si presenta un problema nei flussi, verrà visualizzata una notifica nella parte superiore del portale.
* **Tutte le attività del portale**: ora è possibile visualizzare le attività di tutti i flussi, facendo clic sulla nuova scheda delle attività nel sito Web di Flow.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/mail-and-all-activity/) su questa versione.

### <a name="release-2016-05-27"></a>Versione 05-27-2016
* **Esplorazione dei modelli in base al servizio**: ora esiste un modo per visualizzare tutti i servizi supportati (senza dover effettuare l'accesso). In questa pagina è possibile visualizzare la descrizione dei vari servizi e conoscere i modelli disponibili per ognuno.
* **Creazione e uso dei connettori personalizzati**: così com'è possibile creare connettori personalizzati in PowerApps, è possibile anche connettersi alle proprie API sul sito flow.microsoft.com:
* **Test dei flussi prima del termine**: ora, ogni volta che si salva un flusso, è possibile visualizzare all'istante i risultati della sua esecuzione, se si esegue l'azione di avvio.

[Ulteriori informazioni e domande](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) su questa versione.

### <a name="release-2016-05-07"></a>Versione 05-07-2016
Aggiunta di due nuovi servizi: Microsoft Project Online e Mandrill di MailChimp. [Ulteriori informazioni e domande](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) su questa versione.

### <a name="release-2016-04-27---public-preview"></a>Versione 27-04-2016: anteprima pubblica
Se sono stati usati i flussi logici come parte di [Microsoft PowerApps](https://powerapps.microsoft.com), la versione di anteprima di Microsoft Flow offre diverse nuove funzionalità:

* È ora possibile sfogliare una raccolta di decine di modelli e ordinarli per data di pubblicazione, nome o popolarità.
* È possibile [pubblicare i propri modelli](publish-a-template.md) nella raccolta dopo aver personalizzato un flusso.
* È possibile visualizzare la cronologia per ogni controllo ed esecuzione del proprio flusso.
* Quando si salva un flusso, è possibile [osservarlo subito in azione](see-a-flow-run.md) eseguendo semplicemente l'azione di trigger.
* Abbiamo una [nuova community](https://go.microsoft.com/fwlink/?LinkID=787467) in cui discutere di Flow o [sottoporre le proprie idee](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Passaggi successivi
Per eventuali problemi non trattati in queste note sulla versione o nelle [domande frequenti](frequently-asked-questions.md), [entrare nella community](https://go.microsoft.com/fwlink/?LinkID=787467) per porre domande oppure [contattare il supporto tecnico](http://go.microsoft.com/fwlink/?LinkID=787479).

