---
title: Note sulla versione | Microsoft Docs
description: Problemi comuni e novità per Microsoft Flow versioni
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
ms.date: 08/31/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6c414538c31aa17ed5ab6ba1498812576a8024ae
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548858"
---
# <a name="release-notes"></a>Note sulla versione
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="top-questions"></a>Domande principali
1. Il flusso non è riuscito. Ricerca per categorie correggerla?
   
   1. Identificare l'errore. Per iniziare, passare all'icona notifiche nella parte superiore del portale Web oppure selezionare la scheda **attività** nell'app per dispositivi mobili. Il flusso dovrebbe essere visualizzato ed è possibile selezionarlo.
   2. Si stanno ora esaminando i dettagli del flusso. Trovare il passaggio con l'icona di punto esclamativo rosso. verrà visualizzato il messaggio di errore relativo al flusso.
   3. A seconda del messaggio di errore, dovrebbe essere possibile **modificare** il flusso e correggerlo. Scopri di [più su come correggere gli errori comuni del flusso](fix-flow-failures.md).
2. Ricerca per categorie utilizzare una condizione o un'espressione avanzata?
   
   * Leggere le informazioni sull' [aggiunta di condizioni](add-condition.md).
   * Se si desiderano più case in un flusso, selezionare **Aggiungi condizione** dall'interno di una condizione esistente.
   * Creare un'espressione avanzata facendo riferimento a [una funzione in app per la logica](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Come funzionano le licenze con Office 365?
   
   * Se si è un utente di Office 365, si ottiene l'accesso completo tramite il piano Microsoft Flow per Office 365. Per ulteriori informazioni, vedere i [piani tariffari per Microsoft Flow](https://flow.microsoft.com/pricing/) .
   * Se si è un amministratore, vedere le informazioni sulle [licenze per Microsoft Flow](organization-q-and-a.md), incluso con Office 365.

## <a name="known-issues"></a>Problemi noti
1. Gli elenchi di SharePoint nei siti personali e che non sono di tipo *elenco personalizzato* non sono supportati. Per risolvere questo problema, creare un elenco personalizzato in un sito di SharePoint standard.
2. I trigger di file non verranno generati per i file aggiunti all'interno delle cartelle nidificate all'interno della cartella selezionata.

## <a name="whats-new"></a>Novità

> [!IMPORTANT]
>
> **Annuncio delle note sulla versione**
>
> Si sta chiedendo le funzionalità imminenti e rilasciate di recente in Microsoft Flow?
>[Visualizzare le note sulla versione del 2018 ottobre](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). Sono stati acquisiti tutti i dettagli, end-to-end, dall'alto verso il basso, che è possibile usare per la pianificazione. Per ulteriori informazioni, esaminare [ogni versione settimanale](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) con le funzionalità e i miglioramenti che contiene.
>
> Le note sulla versione precedenti alla versione ottobre 2018 rimarranno qui per riferimento futuro, ma tutte le nuove versioni saranno incluse solo nei percorsi precedenti e non in questa pagina.

### <a name="release-2018-09-24"></a>Versione 2018-09-24

- **Accesso amministrativo per la guida e il supporto** : aprire i ticket di supporto per Microsoft Flow nell'interfaccia di amministrazione di piattaforma Power e fornire dettagli aggiuntivi sugli errori del flusso di lavoro.
- **Riprogettazione della community di Flow** : ricerca di ciò che ti serve è stato semplificato nella community di Microsoft Flow.
- **Miglioramenti al connettore Microsoft teams** : nuovi trigger per Microsoft teams, in modo da poter eseguire un flusso quando sono presenti nuovi messaggi in un canale.
- **Altre azioni di SharePoint** : sono disponibili nuove azioni per lo trasferimento di file e altro nel connettore di SharePoint.
- **Nuovi report di analisi amministrazione** : l'ambiente e l'analisi a livello di tenant sono stati aggiunti all'interfaccia di amministrazione della piattaforma applicativa aziendale.
- **Integrazione di Power query** : è in corso la compilazione di un'esperienza Power query che consentirà ai creatori di eseguire il data shaping di mashup di dati da SQL Server.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) su questa versione.

### <a name="release-2018-08-31"></a>Versione 2018-08-31

- **Testare il flusso usando dati di esempio** : usare dati di esempio dai connettori per testare il flusso durante la compilazione dall'interno della finestra di progettazione Microsoft Flow. Quando si testa il flusso con dati di esempio, si conferma che il flusso verrà eseguito come previsto quando viene distribuito nell'ambiente di produzione.
- **Cinque nuovi connettori** : sono stati aggiunti quattro nuovi connettori di gestione: PowerApps per i creatori di App, piattaforma Power per gli amministratori, PowerApps per gli amministratori, Microsoft Flow per gli amministratori e Microsoft School Data Sync.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/test-data-management-connectors/) su questa versione.

### <a name="release-2018-08-24"></a>Versione 2018-08-24

- **Nuovi modelli di sincronizzazione del calendario** : nuovi modelli di calendario che copiano eventi tra Google Calendar e Office 365 o Outlook.com.
- **Supporto di più valori per SharePoint** -lettura e scrittura per campi con più valori in SharePoint che sono tipi scelta, persona o ricerca.
- **Inviare approvazioni per conto di altri utenti dell'organizzazione** : inviare approvazioni per conto di altri utenti dell'organizzazione, ad esempio la persona che ha caricato il file nell'elenco di SharePoint, invece della persona che ha creato il flusso.
- **Altri tipi di input di pulsante** : i pulsanti hanno due nuovi tipi di input: Number e Yes/No.
- **Aggiornamenti del connettore** : nuovo connettore NetDocuments, miglioramenti ai connettori di Azure e altro ancora.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/button-types-more/) su questa versione.

### <a name="release-2018-08-02"></a>Versione 2018-08-02

Il programma Microsoft Flow Preview è il modo per accedere in anticipo alle funzionalità e agli aggiornamenti imminenti per Microsoft Flow. Per ottenere l'accesso in anticipo alle funzionalità più recenti, è sufficiente creare e quindi usare un ambiente nell'area di anteprima.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/flow-preview-program/) su questa versione.

### <a name="release-2018-07-23"></a>Versione 2018-07-23

- **Compilare ed eseguire flussi da Excel** : con il pulsante nuovo **flusso** , accessibile dalla scheda **dati** della barra multifunzione, è possibile creare e attivare le automazioni da Microsoft Flow sui dati della tabella in Excel. Automatizzare l'elaborazione dei dati o la copia/importazione dei dati.
- **Creazione di un** flusso del processo di business: un flusso del processo di business è un nuovo tipo di flusso Interactive-Human con stato basato sul Common Data Service. Usare questi nuovi flussi per definire un set di fasi e passaggi che gli utenti devono seguire. Possono andare avanti e indietro in base alle esigenze.
- **Creare un flusso per Microsoft to-do in Outlook Web App** : se qualcuno è \@indicato in Outlook Web App, verrà visualizzato un collegamento per creare un flusso. Questo flusso crea automaticamente le attività per la \@persona citata in Microsoft, in base al contenuto del messaggio di posta elettronica.
- **Supporto** per la visualizzazione di SharePoint: il connettore SharePoint supporta ora la selezione di una visualizzazione SharePoint specifica su trigger e azioni. Questa operazione consente di filtrare le colonne in modo da visualizzare solo i campi presenti nella visualizzazione selezionata.
- **Quattro nuovi connettori** : sono stati aggiunti IOT Central di Azure, una soluzione SaaS (software-as-a-Service) estremamente scalabile, il sondaggio 123, l'integrazione di progettazione LMS365 e ProjectWise.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) su questa versione.

### <a name="release-2018-06-29"></a>Versione 2018-06-29

- **Richiesta di flusso di disconnessione incorporato in SharePoint** : quando si seleziona un file o un elemento in SharePoint, viene visualizzata una nuova **richiesta di flusso di** disconnessione. Questo flusso non richiede alcuna configurazione o configurazione e invia una richiesta di approvazione con un solo clic.
- **Due nuovi connettori** : sono stati aggiunti Cloud Connect studio e PoliteMail.
- **Miglioramenti della cronologia e della pagina di creazione** : l'elenco della cronologia di esecuzione viene aggiornato includendo i tempi di esecuzione esatti e la pagina Crea aggiungendo un nuovo video di procedura dettagliata.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) su questa versione.

### <a name="release-2018-06-08"></a>Versione 2018-06-08

- I **cmdlet di PowerShell** , sia i creatori di flussi che gli amministratori tenant, possono ora usare PowerShell per gestire i flussi a livello di codice.
- **Miglioramenti al bot Flow Team** : il bot di Flow in Microsoft teams può eseguire i pulsanti di flusso e descrivere i flussi.
- **Tre nuovi connettori** : è stato aggiunto il supporto per Marketo, ElasticOCR e DynamicSignal. 
- **Informazioni aggiuntive sulla condivisione** : sono state aggiunte informazioni aggiuntive quando si condividono o si eseguono flussi condivisi, in modo da conoscere esattamente le autorizzazioni che altri utenti riceveranno.
- **Rimozione automatica degli URL di SharePoint** : quando si copia e incolla un URL di SharePoint nel browser, il testo potrebbe contenere testo aggiuntivo oltre il sito. questo testo verrà rimosso automaticamente per potersi connettere solo al sito.
- **Documentazione sulle richieste GDPR** : è stata creata una guida completa e un set di strumenti per le organizzazioni aziendali per gestire le richieste di diritti dei soggetti interessati.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) su questa versione.

### <a name="release-2018-05-21"></a>Versione 2018-05-21

- **Flussi "di proprietà di" elenchi e librerie di SharePoint** : i flussi che funzionano con gli elenchi e le librerie di SharePoint possono essere condivisi con tali elenchi o librerie. Quindi, invece di essere condivise con singoli utenti o gruppi, vengono condivise con tutti gli utenti che hanno accesso all'elenco. Quando gli utenti vengono aggiunti o rimossi dall'elenco o dalla raccolta, l'appartenenza viene automaticamente modificata di conseguenza.
- **Analisi dei dettagli dell'errore** : nuovo report incorporato che fornisce informazioni su tutti gli errori che si verificano all'interno di un flusso.
- **Condividere i flussi con i gruppi di office 365** : è possibile rendere il proprietario di un flusso in un gruppo di Office 365 Modern ed è possibile condividere i flussi di un pulsante con i gruppi di Office 365 in modo che chiunque nel gruppo possa eseguire il flusso.
- **Miglioramenti di SharePoint Connector** : sono disponibili due nuove funzionalità di SharePoint Connector, ovvero i flussi di trigger quando vengono eliminati elementi o file e viene chiamato qualsiasi endpoint HTTP supportato dall'API REST di SharePoint.
- **Due nuovi connettori** : è stato aggiunto il supporto per Azure Data Factory e MailParser

[Scopri di più e poni domande](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) su questa versione.

### <a name="release-2018-05-01"></a>Versione 2018-05-01

- **Testo RTF nei messaggi di approvazione** : usare Markdown per formattare i dettagli di approvazione inviati.
- **Pulsanti con più input di selezione** : pulsanti di flusso di compilazione che usano un elenco di selezione multipla per raccogliere più di un valore in una sola volta.
- **Usare i flussi più ampi** : l'app per dispositivi mobili Microsoft Flow supporta ora la visualizzazione orizzontale e la finestra di progettazione Web ha una barra di scorrimento orizzontale.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) su questa versione.

### <a name="release-2018-04-12"></a>Versione 2018-04-12

- **Restituire i dati a PowerApps da** flussi di compilazione di flussi che possono essere chiamati da un'app compilata con PowerApps e restituire i dati all'app. Usare la finestra di progettazione del flusso visivo con trascinamento della selezione per compilare la logica necessaria per le app. 
- **Aggiungere più record agli input di matrice** : è stato aggiunto un generatore di elenchi in Microsoft Flow che può essere usato per aggiungere più allegati a un messaggio di posta elettronica, ad esempio.
- **Flussi di test con dati di esecuzione precedenti** : è stato aggiunto un nuovo pulsante flusso di test alla finestra di progettazione che consente di testare il flusso con i dati del trigger delle esecuzioni di flusso precedenti.
- **Nuovi campi del flusso di lavoro ()** : è ora possibile accedere al nome dell'ambiente e al nome visualizzato del flusso con l'espressione Workflow ().

[Scopri di più e poni domande](https://flow.microsoft.com/blog/return-data-to-powerapps/) su questa versione.

### <a name="release-2018-04-04"></a>Versione 2018-04-04

- Le approvazioni **per le** approvazioni Common Data Service-moderne sono basate sulla versione più recente del Common Data Service. Ciò significa che è possibile compilare flussi che leggono lo stato delle approvazioni inviate o ricevute con il connettore Common Data Service.
- **Trovare gli errori in applica a ogni** : passare direttamente agli errori nei cicli nella visualizzazione di esecuzione del flusso, anche quando sono presenti centinaia di elementi nel ciclo.
- **Riassegnare le approvazioni** : è possibile assegnare qualsiasi approvazione ricevuta a un altro utente dell'organizzazione per delegare l'approvazione a tali approvazioni. 
- **Elenchi di stanze** : il connettore Office 365 Outlook ha aggiunto azioni per ottenere i dati delle sale nell'organizzazione.
- **Vedere i dettagli dei pulsanti di Flow** : quando si esegue un flusso che è stato condiviso con l'utente, è ora possibile visualizzare tutte le azioni usate dal flusso.
- **Area Regno Unito** -è ora possibile creare ambienti per archiviare i dati nel Regno Unito.
- **Due nuovi connettori** : è stato aggiunto il supporto per l'amministrazione di AtBot e l'hub contenuto marketing.
- **Nuova pagina di destinazione della documentazione** : aggiornamento della pagina di destinazione della documentazione in modo che il contenuto venga raggruppato per l'utente, ovvero un utente esperto, un utente intermedio o un esperto. 

[Scopri di più e poni domande](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) su questa versione.

### <a name="release-2018-03-13"></a>Versione 2018-03-13

- **Cronologia delle approvazioni** : consente di visualizzare tutte le richieste di approvazione inviate, incluse le risposte, i commenti inviati e l'ora esatta in cui si sono verificati.
- **Quattro nuovi connettori** : sono stati aggiunti Excel online (business), Excel online (OneDrive), Azure SQL data warehouse e Pitney Bowes Tax Calculator.
- **Descrizioni comandi del contenuto dinamico** : passare il puntatore del mouse sul contenuto dinamico per vedere dove proviene dall'interno delle azioni e le espressioni di anteprima senza aprire l'editor di espressioni completo.
- **Controllo della concorrenza** : abilitare il controllo della concorrenza affinché un determinato flusso disponga di una sola esecuzione alla volta.
- **Ripetizione esponenziale** : nuovo tipo di criteri di ripetizione che spaziano i tentativi in modo esponenziale nel tempo.
- **Conformità dell'accessibilità** : sono stati rilasciati nuovi documenti di conformità che descrivono come Microsoft Flow soddisfano gli standard di accessibilità.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/approval-history-accessibility/) su questa versione.

### <a name="release-2018-02-09"></a>Versione 2018-02-09

- **Disponibilità elevata del gateway** : creare cluster a disponibilità elevata di gateway dati locali per garantire le connessioni quando i singoli computer si arrestano.
- Il **miglioramento si applica a ogni** -con Flow Plan 1 o Flow Plan 2 processo fino a 100.000 elementi in una singola esecuzione e 50 azioni in parallelo in si applicano a ogni ciclo. 

[Scopri di più e poni domande](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) su questa versione.

### <a name="release-2018-01-29"></a>Versione 2018-01-29

- **Microsoft teams** : dai team è possibile creare e gestire i flussi, esaminare le approvazioni ricevute e inviate e avviare i flussi direttamente nell'app desktop dei team o in teams.Microsoft.com. per [altre informazioni](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/), vedere qui.
- **Notifiche di modifica condivise** : ogni volta che un flusso di cui si è proprietari viene modificato da un collaboratore, si riceverà una notifica tramite posta elettronica che informa che il flusso è stato modificato.
- **Nuove espressioni** -sono stati aggiunti due nuovi set di espressioni: uno per analizzare gli URL e un altro per lavorare con gli oggetti JSON.
- **Tre nuovi connettori** : questa settimana sono disponibili due nuovi connettori Plumsail: Plumsail SP e Plumsail Forms e un nuovo connettore per kintone.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) su questa versione.

### <a name="release-2018-01-17"></a>Versione 2018-01-17

- **Informazioni sul profilo di office 365** : sono state aggiunte nuove azioni al connettore utenti di Office 365 che funzionano con profili utente e foto.
- **Accoda a variabili di stringa** : è possibile aggiungere stringhe all'interno dei cicli per compilare tabelle o altri elenchi.
- **Connettore Infobip** : Infobip è un servizio che consente la comunicazione di livello aziendale, incluse le chiamate vocali e l'attivazione di SMS in ingresso.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/o365-profile-infobip/) su questa versione.

### <a name="release-2017-12-20"></a>Versione 2017-12-20

Microsoft Flow Analytics è ora disponibile in tutte le aree Microsoft Flow, il che significa che è possibile ottenere informazioni più dettagliate sull'integrità dei flussi in esecuzione all'interno dell'ambiente.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) su questa versione.


### <a name="release-2017-12-14"></a>Versione 2017-12-14

- **Miglioramenti di Outlook Connector** : è possibile salvare un messaggio di posta elettronica come file ". eml", rispondere automaticamente agli inviti del calendario e attivare i flussi quando si è citati in un thread di posta elettronica.
- **Miglioramenti delle connessioni** : Microsoft Flow memorizza le connessioni usate più di recente e Mostra tutti i connettori appena aggiunti.
- **Cinque nuovi connettori** : sono stati aggiunti i documenti istanze di contenitore di Azure, Azure kusto, Metatask, Microsoft to-do e Plumsail.
- **Miglioramenti http** : l'azione http supporta ora la codifica Chunked.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/outlook-connector-more/) su questa versione.

### <a name="release-2017-12-05"></a>Versione 2017-12-05

Il pannello Microsoft Flow Launch è ora disponibile in tutte le aree geografiche. Questo pannello consente di aggiungere valori a un flusso quando lo si esegue all'interno dell'elenco di SharePoint o della raccolta documenti.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) su questa versione.


### <a name="release-2017-11-28"></a>Versione 2017-11-28

- **Metadati gestiti** : per leggere i dati e scrivere in colonne in SharePoint che usano i metadati gestiti (noto anche come. Tassonomia).
- **Accoda a matrici** : consente di aggiungere elementi alla fine delle matrici usando una nuova azione Aggiungi alla variabile di matrice.
- **Tago** : nuovo connettore per Tago, che consente di connettere facilmente i dispositivi elettronici con dati esterni per prendere decisioni più intelligenti mediante l'analisi contestuale.
- **iPhone x** : una nuova versione dell'app Microsoft Flow che usa l'intero schermo di iPhone x e che offre un miglioramento della velocità per il caricamento di immagini.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/managed-metadata-tago/) su questa versione.

### <a name="release-2017-11-09"></a>Versione 2017-11-09

- **Integrazione di OneDrive for business** : è [ora disponibile un pulsante Flow all'interno di OneDrive for business](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) che può creare o attivare flussi in file o cartelle selezionati.
- **Trigger di Planner** : avviare i flussi quando viene creata una nuova attività, quando un'attività viene assegnata all'utente o quando ne viene completata una.
- **Allegati di SharePoint** -usare allegati negli elementi elenco di SharePoint: elencare, scaricare, aggiungere o eliminare allegati.
- **Connettore di gestione del flusso** : creare flussi che automatizzano la gestione di altri flussi nell'ambiente (ad esempio, aggiungono automaticamente le autorizzazioni ai flussi).
- **Quattro nuovi connettori** : sono stati aggiunti servizio visione artificiale personalizzato di Azure, D & B Optimizer, Enadoc e Derdak SIGNL4. 
- **Altre azioni del connettore** : eseguire query SQL, ottenere trigger di posta elettronica più veloci, usare qualsiasi metodo con HTTP con Azure ad e altro ancora.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) su questa versione.

### <a name="release-2017-11-02"></a>Versione 2017-11-02

- **Registrazione di controllo** : gli eventi di controllo Microsoft Flow sono ora disponibili in Office 365 Centro sicurezza e conformità per tutti i tenant.
- **Correzioni dei widget di Flow** : è stato risolto un problema nell'app Microsoft Flow per dispositivi mobili che ha causato il caricamento dei pulsanti nel widget.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/security-and-compliance-center/) su questa versione.

### <a name="release-2017-10-19"></a>Versione 2017-10-19

- **Annidato Apply a each** : è possibile aggiungere Apply a each actions, Filter e SELECT in other Apply per ogni azione del contenitore.
- **Azioni di data e ora** : nuove azioni per il recupero delle ore locali, l'aggiunta, la sottrazione o la formattazione degli orari.
- **Quattro nuovi connettori** : sono stati aggiunti content moderator, docparser, Microsoft Kaizala e Pitney Bowes Data Validation.
- **Esperienza di connessione migliorata** : notifiche nel portale di Microsoft Flow quando una connessione è interruppe e dettagli di connessione più completi.
- **Raccolta on-the-go** : nuova raccolta di modelli per [i lavoratori in viaggio](https://flow.microsoft.com/collections/onthego/).
- **Input del pulsante di indirizzo di posta elettronica** : raccoglie gli indirizzi di posta elettronica dagli utenti quando eseguono i pulsanti.
- **Input del pulsante file** : consente di ottenere i file caricati, ad esempio le foto, dagli utenti quando eseguono i pulsanti.
- La **prima esecuzione e l'accesso automatico** migliorano le esperienze di prima esecuzione nell'app per dispositivi mobili, incluso l'accesso automatico.
- **Trigger Microsoft form più veloci** : i moduli attiveranno i flussi molto più rapidamente di prima (in precedenza una volta all'ora).
- **Input di pulsanti tra sessioni** : i pulsanti attivati sul telefono cellulare ricorderanno gli input precedenti.
- Feed **attività per dispositivi mobili** : feed attività migliorato per includere riepiloghi e dettagli della risoluzione dei problemi più dettagliati.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/nested-apply-to-each/) su questa versione.

### <a name="release-2017-10-03"></a>Versione 2017-10-03

- **Tutti devono approvare** : è necessario che venga inviata una richiesta di approvazione a più di una persona per consentire a tutti gli utenti che hanno ricevuto la richiesta di approvarlo.
- **Nuove azioni OneDrive for business** : genera i file PDF per i file archiviati in OneDrive for business e altre quattro nuove azioni.
- **Connettore Apache Impala** : Apache Impala (incubating) è il database di analisi nativo open source per Apache Hadoop.
- **Aggiungere descrizioni del flusso** : assegnare le descrizioni dei flussi in modo che i colleghi possano visualizzare un riepilogo del flusso.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) su questa versione.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Versione 2017-09-25: aggiornamento del terzo trimestre per Microsoft Flow

- **Integrazione più approfondita di SharePoint nella prima versione** : sono disponibili nuovi flussi di invio per la revisione e un pannello di flusso per la raccolta di input quando si esegue un flusso per i tenant della prima versione.
- **App dynamics 365** : Flow è ora integrato nell'interfaccia utente per le app Dynamics 365, ad esempio le vendite Dynamics 365 e il servizio clienti Dynamics 365.
- **Microsoft Trust Center** -Microsoft Flow è elencato in Microsoft Trust Center, che mostra certificazioni come HIPAA, ISO e SOC.
- **Analisi di utilizzo** : ogni flusso ha un dashboard Power bi incorporato con analisi dell'utilizzo di base.
- **Registrazione di controllo nella prima versione** : tutti gli eventi di gestione dei flussi vengono registrati nel centro sicurezza e conformità di Office 365 per i tenant della prima versione.
- **Sei nuovi connettori** : sono stati aggiunti LinkedIn, gruppi di Office 365, Skype for business, Adobe Sign, Bizzy e Azure log Analytics Data Collection.
- **Trigger SQL** : vengono eseguiti flussi quando viene aggiunta una nuova riga o viene aggiornata una riga in una tabella SQL.
- **Connettori personalizzati** locali: i connettori personalizzati possono ora usare il gateway dati locale per connettersi agli endpoint interni nella rete.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/q3-2017-update/) su questa versione.

### <a name="release-2017-09-21"></a>Versione 2017-09-21

- **Scaricare la cronologia dei flussi** : scaricare la cronologia di esecuzione di un flusso come file CSV per aprirlo in Excel.
- **Ricorrenza avanzata** : consente di creare pianificazioni ricorrenti per attivare i flussi, ad esempio, solo nei giorni feriali.
- **IntelliSense** -quando si digitano espressioni, IntelliSense fornisce suggerimenti per i parametri.
- **Quattro nuovi connettori** : sono stati aggiunti connettori per Azure ad Servizi http, Amazon spostamento, pubblicazione della griglia di eventi di Azure e FlowForma.
- **Condivisione dei collegamenti** : nuova azione per generare collegamenti condivisibili per i file OneDrive o i BLOB di archiviazione di Azure.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/download-history-recurrence/) su questa versione.


### <a name="release-2017-08-25"></a>Versione 2017-08-25
* **Proprietà del documento e altro ancora per sharepoint** - [leggere e impostare le proprietà della raccolta documenti di SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)e utilizzare campi aggiuntivi come collegamenti all'elemento di SharePoint.
* **Raccolte di flussi** : le raccolte di flussi sono un set di raccolte di modelli organizzati in base al ruolo o verticalmente.
* **Ricondivisione** dei pulsanti: quando si condividono i pulsanti con i colleghi, è possibile ricondividerli anche con altri utenti.
* **Raccogli elenchi dai pulsanti** : consente di definire elenchi a discesa di opzioni da cui gli utenti possono scegliere quando toccare il pulsante.
* **Sette nuovi connettori** : Aweber, Azure log Analytics, tabelle di Azure, DocFusion365, griglia di eventi di Azure, Hub eventi di Azure e StaffHub. 
* **Miglioramenti a slack e MySQL** : creare o aggiungere canali in slack ed è possibile scrivere nei database MySQL.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/button-updates-seven-connectors/) su questa versione.

### <a name="release-2017-08-02"></a>Versione 2017-08-02
* **Campi di scrittura su persona, scelta e ricerca** : l'elemento di creazione elemento e aggiornamento di SharePoint [supporta ora la possibilità di impostare i](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) campi persona, opzione e ricerca.
* **Altre impostazioni azione** : è ora disponibile un maggiore controllo sulla modalità di esecuzione di trigger e azioni, inclusa la configurazione di criteri di ripetizione dei tentativi e di paginazione.
* **Quattro nuovi connettori** : ora è possibile usare archiviazione file di Azure, moduli elastici, Plivo e video Indexer.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/four-connector-action-settings/) su questa versione.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Versione 2017-07-27-aggiornamento Q2 per Microsoft Flow
* **Importazione ed esportazione** : esportazione e importazione di soluzioni di flusso tra ambienti o da test in produzione. 
* **Usare le espressioni in Actions** : immettere espressioni in qualsiasi azione e ottenere informazioni inline su come usarle.
* **Espandi fino ad app per la logica di Azure** : Salva i flussi come risorsa app per la logica di Azure che può essere distribuita tramite Visual Studio o il portale di Azure.
* **Visibilità amministratore** : scaricare Microsoft Flow utilizzo nel tenant per capire esattamente dove e come vengono usati i flussi.
* **Flussi in dynamics 365** -usare i flussi all'interno di Dynamics 365 per Operations & Financials, Business Edition.
* **Trovare più facilmente gli scenari** : esplorare tutti gli elementi che il connettore può eseguire e quindi usare qualsiasi trigger come punto di partenza per la compilazione dei flussi.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/q2-2017-update/) su questa versione.

### <a name="release-2017-07-13"></a>Versione 2017-07-13
* **Pubblicazione del modello migliorata** : pubblicare tutti i flussi creati, insieme alle relative categorie, nella raccolta pubblica.
* **Ottenere gli eventi nel calendario di Outlook** : una nuova azione per restituire tutti gli eventi tra due volte nel calendario.
* **Nuova funzionalità per dispositivi mobili** : eseguire flussi su richiesta e inviare di nuovo le esecuzioni non riuscite nell'app per dispositivi mobili.
* **Elenchi a discesa dinamici nei connettori personalizzati** : creare elenchi a discesa dinamici, trigger di polling e test dei connettori personalizzati.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) su questa versione.

### <a name="release-2017-06-28"></a>Versione 2017-06-28
* **Aggiornare le impostazioni della lingua** : è possibile personalizzare la lingua e l'area che Microsoft Flow USA dal menu impostazioni.
* **Cinque nuovi connettori** : è stato aggiunto il supporto per Adobe Creative Cloud, Bing Maps, ricerca Bing, JotForm e Freshservice.
* **Configurare i timeout** : modificare le azioni temporali con esecuzione prolungata, ad esempio le approvazioni, eseguire prima di "timeout" e il flusso continua.
* **Includi commenti in Outlook per le approvazioni** : quando si riceve una richiesta di approvazione, è possibile fornire commenti senza mai uscire da Outlook.
* **Colori del marchio del connettore personalizzato** : è ora possibile immettere un colore per i connettori personalizzati che verranno usati per gli sfondi.
* **Salva con nome per i flussi del team** : crea copie di tutti i flussi, inclusi i flussi del team
* **Elimina informazioni sul flusso** : quando si elimina un flusso, viene visualizzato l'elenco di tutte le esecuzioni in sospeso per quel flusso.
* **Filtro nella pagina connettori** : consente di cercare i connettori desiderati nella pagina connettori e filtrare in base al tipo di connettore.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/language-settings-3-connectors/) su questa versione.

### <a name="release-2017-06-19"></a>Versione 2017-06-19
È ora possibile visualizzare lo stato di tutte le richieste di approvazione in sospeso inviate. Inoltre, è possibile esplorare e agire su tutte le approvazioni in sospeso direttamente dal dispositivo mobile.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) su questa versione.

### <a name="release-2017-06-15"></a>Versione 2017-06-15
* **Conversione del contenuto** : nuovo connettore in grado di convertire contenuto HTML in testo normale, utile per la gestione di messaggi di posta elettronica in formato HTML.
* **Tre nuovi connettori di database** : è stato aggiunto il supporto di sola lettura per MySQL, PostgreSQL e Teradata. Questi connettori si connettono tramite il gateway dati locale.
* **Altri tre connettori** : si connettono ai progetti applicazione Azure Insights, caprestito e teamwork.
* **Visualizzazione migliore per la gestione degli** errori: i passaggi eseguiti dopo gli errori vengono ora visualizzati con frecce punteggiate rosse per poterli identificare facilmente.
* **Riquadro dei dettagli esecuzione** : quando un flusso non riesce, è ora disponibile un nuovo riquadro di destra che contiene alcuni passaggi utili per correggere il flusso.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/seven-connectors-and-html/) su questa versione.

### <a name="release-2017-06-04"></a>Versione 2017-06-04
* **GA per Windows Phone** - [l'app per dispositivi mobili Microsoft Flow è stata rilasciata a livello generale per Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Messaggi di** posta elettronica in caso di errori di flusso: ricevere una notifica tramite posta elettronica quando si verifica un flusso non riuscito. Questi messaggi di errore vengono inviati solo una volta alla settimana e possono essere attivati o disattivati dall'utente.
* **Selezionare l'azione per le tabelle** : utilizzare la nuova azione Seleziona per modificare il set di colonne che verrà incluso nelle tabelle.
* **Connettore Microsoft Forms** : Microsoft Forms è una nuova parte di Office 365 Education che consente a docenti e studenti di creare quiz personalizzati in modo rapido e semplice, sondaggi, questionari, registrazioni e altro ancora.
* **Piano di office 365 Enterprise K1** : PowerApps e Microsoft Flow sono ora inclusi nel piano Office 365 Enterprise K1 con determinate quote.
* Le **intestazioni HTTP sono più semplici** . Analogamente all'azione SELECT, è possibile fornire un nome di intestazione e un valore di intestazione semplicemente compilando le caselle di testo sull'azione.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) su questa versione.

### <a name="release-2017-05-23"></a>Versione 2017-05-23
* **Microsoft teams connector** - [Microsoft teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) è un'area di lavoro basata su chat in Office 365 che riunisce persone, conversazioni e contenuti, oltre agli strumenti necessari ai team, in modo che possano collaborare facilmente per ottenere maggiori risultati.
* I **widget nei widget iOS e Android** -Microsoft Flow sono tasti di scelta rapida che consentono di attivare il pulsante direttamente dalla schermata iniziale in modo più semplice e rapido.
* **Creare passaggi per la gestione degli errori** : definire uno o più passaggi da eseguire dopo che un'azione ha esito negativo. Ad esempio, se il flusso non riesce a creare un record in Dynamics 365, ricevere immediatamente una notifica.
* **Variabili Integer e float** : inizializzazione e incremento o decremento dei contatori all'interno di un'esecuzione del flusso per conteggiare il numero di esecuzioni di un determinato set di logica.
* **Pagina dei dettagli del flusso** : quando si seleziona un flusso nell'elenco **flussi personali** , viene visualizzata una pagina con i dettagli relativi a tale flusso, ad esempio gli utenti che hanno accesso e la cronologia di esecuzione.
* **Quote di esecuzione del flusso per** gli amministratori: gli amministratori possono ora monitorare l'utilizzo delle esecuzioni dei flussi in un'organizzazione rispetto alla quota di esecuzione aziendale comune e ottenere una ripartizione della quota per comprendere le licenze che contribuiscono alla quota.
* **Miglioramenti del trigger di richiesta http** : usare metodi HTTP diversi e aggiungere segmenti di percorso per il trigger di richiesta.
* **Due connettori partner** : Microsoft Flow ora possono connettersi a parserr, a un servizio di analisi della posta elettronica e a moduli Cognito, un servizio basato su form online.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/error-handling/) su questa versione.

### <a name="release-2017-05-12"></a>Versione 2017-05-12
* **Integrazione con le raccolte documenti di SharePoint** : è possibile selezionare qualsiasi file in una raccolta documenti e avviare un flusso, ad esempio per inviarlo al responsabile per l'approvazione [e molto altro ancora](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Microsoft Planner Connector** : Microsoft Planner consente di riunire in modo semplice team, attività, documenti e conversazioni per ottenere risultati migliori.
* **Visualizzazione amministratore delle licenze** : gli amministratori possono visualizzare tutte le licenze Microsoft Flow e PowerApps (versione di valutazione e a pagamento) nell'interfaccia di amministrazione di Microsoft Flow.
* **Piano della community di PowerApps** : il piano della community di PowerApps è un piano gratuito che consente agli utenti di esplorare, apprendere e compilare competenze per PowerApps, Microsoft Flow e Common Data Service.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/planner-community-and-licenses/) su questa versione.

### <a name="release-2017-05-09"></a>Versione 2017-05-09
* **Connettore Azure ad** : è disponibile un nuovo connettore per l'esecuzione di azioni di amministratore da Microsoft Flow, inclusa la creazione di utenti o l'aggiunta di tali azioni ai gruppi.
* **Miglioramenti di Office 365 Outlook** : i flussi possono ora essere attivati da cassette postali condivise e inviare messaggi a una cassetta postale condivisa. Possono inoltre impostare o leggere le risposte automatiche.
* **Disponibile in Canada** -è ora possibile creare i flussi in Canada.
* **Creare webhook API** personalizzati: gli sviluppatori di connettori personalizzati possono ora aggiungere trigger alle API personalizzate con i webhook.
* **Gestire i proprietari del flusso nell'interfaccia di amministrazione** : gli amministratori dell'ambiente possono gestire i proprietari del flusso nell'interfaccia di amministrazione di Microsoft Flow.
* Informazioni di **riferimento sulla documentazione del connettore** : è ora disponibile un [riferimento completo al connettore in docs.Microsoft.com](https://docs.microsoft.com/Connectors/).
* **Due servizi partner** : sono stati rilasciati due nuovi servizi partner: Nexmo e Paylocity.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/canada-mailboxes-aad) su questa versione.

### <a name="release-2017-04-27"></a>Versione 2017-04-27
* **Flussi di compilazione con passaggi paralleli** : creare flussi con esecuzione parallela: ciò significa che è possibile eseguire due o più passaggi esattamente allo stesso tempo.
* Sono **supportati cinque** nuovi servizi, ovvero cinque nuovi servizi: approvazioni, benchmark E-mail, capsula CRM, LiveChat e Outlook Customer Manager.
* Esegui il **monitoraggio dei tentativi per le azioni** : Microsoft Flow ritenterà quando si verificano errori con i servizi. Vedere ora il numero di tentativi automatici eseguiti e i dettagli di ciò che si è verificato.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/parallel-actions/) su questa versione.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Versione 2017-04-17-aggiornamento Q1 per Microsoft Flow
* **Esperienze di approvazione moderne** : creare flussi di lavoro in cui i responsabili approvazione possono approvare in modo sicuro dall'app per dispositivi mobili Microsoft Flow o dal centro di approvazioni unificate nel sito Web Microsoft Flow.
* **Disponibilità generale dei flussi del team** : più persone possono possedere e gestire un flusso insieme ai flussi del team, ora disponibili a livello generale.
* **Connettori di compilazione per Microsoft Flow** : chiunque può inviare il proprio connettore Microsoft Flow gratuitamente per il resto del mondo da usare.
* **Una finestra di progettazione "dietetica"** : per determinati modelli, una nuova versione della finestra di progettazione presenta solo i campi necessari per creare un flusso, semplificando l'esperienza.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/q1-2017-update/) su questa versione.

### <a name="release-2017-04-11"></a>Versione 2017-04-11
* **Nuove azioni per compilare tabelle ed elenchi** : nuova creare una tabella HTML, creare azioni di join e tabelle CSV in grado di elaborare gli elenchi di elementi, anziché il precedente solo applicabile.
* **Inserire i passaggi ovunque** : è ora possibile inserire un nuovo passaggio in qualsiasi punto del flusso di lavoro senza dover trascinare la selezione.
* **Quattro nuovi servizi** : Flow supporta ora da 10 a 8 la pianificazione, Act!, Inoreader e il API visione artificiale. Con la API Visione artificiale è possibile elaborare le immagini per ottenere il contenuto di testo (noto come OCR) o contrassegnare automaticamente le immagini in base al relativo contenuto.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) su questa versione.

### <a name="release-2017-04-03"></a>Versione 2017-04-03
* **Windows Phone beta** : il programma Windows Phone app beta è disponibile per ottenere un'anteprima dell'app nel Windows Phone. [Altre](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/)informazioni.
* **MUHIMBI PDF** -è ora possibile convertire i file di Microsoft Word in formato PDF, aggiungere filigrane, unire documenti e altro con Muhimbi PDF. [Altre](https://flow.microsoft.com/blog/convert-files-using-muhimbi/)informazioni.
* **Attivare flussi da pulsanti fisici** : annuncio di relazioni con due dei prodotti principali nello spazio dei pulsanti fisico: Flic by Shortcut Labs e BTTN by the Button Corporation. [Altre informazioni](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Versione 2017-03-22
* **Creare una copia del flusso** : è ora possibile creare una copia del flusso per lavorare sulle versioni bozza o duplicare un flusso creato in precedenza.
* **Due nuovi servizi** : aggiunta del supporto per Toodledo-Gestisci l'elenco attività creando e aggiornando attività, Zendesk, che fornisce un servizio clienti e supporta la piattaforma di ticketing.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/make-a-copy/) su questa versione.

### <a name="release-2017-03-15"></a>Versione 2017-03-15
* **Condividere i pulsanti con i colleghi** : è ora possibile condividere i pulsanti di flusso con altri utenti, semplificando l'esecuzione di attività rapide da parte di qualsiasi utente aziendale.
* **Pulsanti di attivazione dalla schermata iniziale: i** tasti di scelta rapida per scorrere i pulsanti dalle schermate Home e di blocco dei dispositivi mobili rendono più veloce che mai attivare un flusso.
* **Flussi del team nell'app Microsoft Flow** : ora è possibile visualizzare i flussi con altri proprietari nell'app Microsoft Flow per iOS o Android.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/button-sharing/) su questa versione.

### <a name="release-2017-03-10"></a>Versione 2017-03-10
* **Miglioramento dell'esperienza del connettore personalizzato** : è ora possibile usare una raccolta di post per creare un connettore personalizzato, modificare, aggiungere e testare le azioni.
* **Due nuovi servizi** : sono state aggiunte le notifiche di PowerApps e il supporto di PivotalTracker.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/new-updates-custom-api/) su questa versione.

### <a name="release-2017-02-27"></a>Versione 2017-02-27
* **Attivare i pulsanti di flusso** : è ora possibile attivare i pulsanti di flusso direttamente da Microsoft Flow. Quando si esamina l'elenco dei flussi, è sufficiente selezionare "..." e scegliere il comando Esegui ora.
* **Cinque nuovi servizi** : è stato aggiunto il supporto Oracle database, interfono, Freshbooks, LeanKit e webmerge.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) su questa versione.

### <a name="release-2017-02-21"></a>Versione 2017-02-21
* **Visualizzare i flussi dell'ambiente** : gli amministratori dell'ambiente possono ora visualizzare l'elenco completo di tutti i flussi all'interno di un determinato ambiente, nonché abilitare, disabilitare o eliminare i flussi.
* **Due nuovi servizi** : è stato aggiunto il supporto di automazione di Azure e Basecamp 2.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) su questa versione.

### <a name="release-2017-02-16"></a>Versione 2017-02-16
* **Cinque nuovi servizi** : è stato aggiunto il supporto per Azure Data Lake, Bitbucket (un servizio di hosting basato su Web per i progetti che usano il controllo delle revisioni git), Eventbrite, Infusionsoft e PipeDrive.
* **Autenticazione HTTP personalizzata** : nella finestra di progettazione del flusso è ora possibile usare l'autenticazione con endpoint HTTP personalizzati.
* **Analizzare i messaggi JSON** : è possibile analizzare i dati JSON dal trigger di richiesta HTTP o restituiti dall'azione http.
* **Filtro di esecuzione del flusso** : filtro migliorato per le esecuzioni dei flussi, con opzioni più specifiche, tra cui la visualizzazione dei flussi in esecuzione

[Scopri di più e poni domande](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) su questa versione.

### <a name="release-2017-02-06"></a>Versione 2017-02-06
* **Flussi del team** : i flussi del team consentono a più utenti di detenersi e gestire un flusso insieme e, se qualcuno lascia un'organizzazione, i flussi creati possono continuare a funzionare.
* **Condivisione di connettori personalizzati** : i connettori personalizzati, come i flussi del team, possono essere condivisi e gestiti collettivamente all'interno di un'organizzazione.
* **Supporto per Gmail e Luis** : connettersi a Gmail e servizi cognitivi di Azure Language Understanding Intelligent Service.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/team-flows/) su questa versione.

### <a name="release-2017-01-30"></a>Versione 2017-01-30
* **Input** dei pulsanti di flusso: i pulsanti Flow possono ora ricevere input dell'utente in fase di esecuzione, quindi gli autori del flusso possono definire le informazioni che vengono passate quando si tocca il pulsante.
* **Attività di Outlook e HelloSign** : il servizio attività di Outlook consente di gestire le attività e HelloSign Abilita le firme elettroniche sicure.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/button-user-inputs/) su questa versione.

### <a name="release-2017-01-23"></a>Versione 2017-01-23
* **Cerca** per servizio-Sfoglia per servizio quando si aggiunge un trigger o un'azione per visualizzare tutte le azioni per ogni servizio.
* **Switch case** -aggiungere blocchi switch per avere diversi rami di logica parallela.
* **Altre azioni di posta elettronica** : nuove funzionalità nei servizi Office 365 Outlook e Outlook.com per lavorare con messaggi di posta elettronica contrassegnati.
* **Cinque nuovi servizi** : si connettono a file system locali o di rete, il servizio di pagamento striping, IBM Informix, IBM DB2 e UserVoice.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/search-by-service/) su questa versione.

### <a name="release-2017-01-14"></a>Versione 2017-01-14
* **Reinvii esecuzioni** : se un flusso non è riuscito e si vuole provare a correggerlo ed eseguirlo di nuovo, è possibile inviare di nuovo l'esecuzione non riuscita.
* **Annulla esecuzioni** : quando un flusso si blocca, è ora possibile annullare in modo esplicito l'esecuzione.
* **Due nuovi servizi** : è stato aggiunto il supporto per GoToTraining e GoToWebinar.
* **Collegamenti per dispositivi mobili** : è possibile condividere i modelli direttamente dall'app per dispositivi mobili ed è stato aggiunto un collegamento di download rapido per le app nella parte superiore del sito Web.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/managing-runs/) su questa versione.

### <a name="release-2016-12-29"></a>Versione 2016-12-29
Microsoft Flow supporta ora DocuSign, per gestire eSignature e la gestione delle transazioni digitali; SurveyMonkey, per sondaggi basati sul Web; e l'app per prendere appunti di OneNote (solo account aziendali).

[Scopri di più e poni domande](https://flow.microsoft.com/blog/final-2016-services/) su questa versione.

### <a name="release-2016-12-20"></a>Versione 2016-12-20
* **Esegui ora** : è ora possibile attivare un trigger ricorrente su richiesta. ad esempio, se si dispone di un report pianificato ogni giorno, ma è necessario che il **report venga eseguito** .
* **Sei nuovi servizi** : crea flussi che si connettono a MSN Weather, medium, contatti Google, buffer, Harvest e TypeForm.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/run-now-and-six-more-services/) su questa versione.

### <a name="release-2016-12-14"></a>Versione 2016-12-14
È ora possibile sfruttare informazioni utili quando si attiva un flusso di un pulsante, ad esempio da dove è stato attivato il pulsante, da chi, a quale ora e altro ancora.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/button-trigger-tokens/) su questa versione.

### <a name="release-2016-12-06"></a>Versione 2016-12-06
* **Introduzione all'apprendimento guidato: introduzione** a una raccolta sequenziata di corsi che abbinano video a documentazione che consentono di comprendere le funzionalità complete e potenti di Microsoft Flow.
* **Due nuovi servizi** : i flussi possono ora usare Freshdesk, una soluzione di supporto clienti e GoToMeeting, uno strumento per la riunione online.
* **Supporto di Webhook http** : un flusso può ora essere un endpoint per i webhook che registreranno automaticamente e annullano la registrazione.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/guided-learning-and-two-services/) su questa versione.

### <a name="release-2016-11-23"></a>Versione 2016-11-23
* **Power bi supporto per gli avvisi in flow** -trasforma informazioni dettagliate in azione attivando flussi da avvisi dati Power bi.
* **Miglioramenti dell'applicazione per dispositivi mobili** : è stata aggiunta la possibilità di creare flussi da zero, oltre all'esperienza già esistente di creazione da modelli. Sono state anche migliorate le prestazioni durante la visualizzazione delle esecuzioni del flusso.
* **Otto nuovi servizi** -è ora possibile connettersi a Azure Resource Manager, code di Azure, Chatter, Disqus, Azure Cosmos DB, servizi cognitivi API viso, HipChat e Wordpress.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) su questa versione.

### <a name="release-2016-11-15"></a>Versione 2016-11-15
* **Microsoft Flow Partner Program** : Microsoft Flow dispone ora di un programma per i partner certificati per stabilire le connessioni e sfruttare i vantaggi offerti dai diversi Talent e dall'esperienza dell'azienda con Microsoft Flow in tutto il mondo.
* **Sei nuovi servizi** : in questa settimana verranno anche rilasciati sei servizi: asana, falò, EASYREDMINE, JIRA, Redmine e Vimeo.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/partner-program-six-new-services/) su questa versione.

### <a name="release-2016-10-31---general-availability"></a>Versione 2016-10-31-disponibilità generale
* **Prezzi e licenze** : ora disponibili per i piani gratuiti e a pagamento, oltre a quelli inclusi in Office 365 e Dynamics 365.
* **Microsoft Flow** interfaccia di amministrazione-pronto per l'uso aziendale con il nuovo centro di amministrazione. Nel centro di amministrazione è possibile gestire gli ambienti all'interno dell'organizzazione.
* **Criteri di prevenzione della perdita dei dati** : gli amministratori possono creare criteri di prevenzione della perdita dei dati per controllare il flusso dei dati tra i servizi.
* **Disponibilità di Android** : l'app Microsoft Flow Phone è ora disponibile sia per iOS che per Android. L'app consente di ricevere notifiche, monitorare l'attività e avviare i flussi con il tocco di un pulsante.
* **Nuove esperienze di progettazione** : è ora possibile eseguire ricerche nel contenuto dinamico passato da Step a Step, rendendo molto più rapido il riferimento ai dati desiderati.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/announcing-ga/) su questa versione.

### <a name="release-2016-10-26"></a>Versione 2016-10-26
* **Flussi di pulsanti** : sono disponibili innumerevoli operazioni che è possibile attivare in qualsiasi momento e in qualsiasi punto. Ora, con i flussi di un pulsante, è possibile fare clic su un pulsante, dal dispositivo mobile.
* **Annunciare gli ambienti** : gli ambienti sono spazi distinti per archiviare e gestire i flussi dell'organizzazione. Gli ambienti sono posizionati geograficamente, il che significa che i flussi, le app e i dati aziendali che si trovano all'interno di un ambiente si troveranno nell'area in cui si trova l'ambiente.
* **Sei nuovi servizi** : aggiunta del supporto per bit.ly, servizi cognitivi analisi del testo, Dynamics NAV, Dynamics 365 for Financials, Instapaper e Pinterest.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/environments-for-makers/) su questa versione.

### <a name="release-2016-10-16"></a>Versione 2016-10-16
* I **connettori personalizzati supportano più tipi di autenticazione** : i connettori personalizzati ora supportano l'autenticazione con chiave API e possono eseguire l'autenticazione in qualsiasi servizio che supporti la specifica OAuth 2,0 completa.
* Sono **supportati tre nuovi servizi** : è stato aggiunto il supporto per Basecamp 3, blogger e PagerDuty.
* **Miglioramenti della finestra di progettazione** : miglioramento delle prestazioni, ora è possibile aggiornare e ripristinare le connessioni direttamente dal "..." menu per ogni azione ed è stato aggiunto un nuovo passaggio denominato terminate che è possibile usare per terminare l'esecuzione di un flusso.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/early-october-updates/) su questa versione.

### <a name="release-2016-09-25"></a>Versione 2016-09-25
Creazione del flusso ora disponibile dai telefoni cellulari. Esplora la raccolta di modelli avanzati, naviga nell'elenco dei nostri servizi o seleziona una categoria di modelli per il drill-through. [Scopri di più e poni domande](https://flow.microsoft.com/blog/mobile-creation/) su questa versione.

### <a name="release-2016-09-22"></a>Versione 2016-09-22
* **Selezione Microsoft Graph people** : una nuova selezione Microsoft Graph persone è integrata direttamente nell'interfaccia utente di Microsoft Flow per consentire di scegliere il contatto o l'indirizzo di posta elettronica corretto.
* **Supporto di Microsoft Dynamics AX** : dall'interno dei flussi è ora possibile intervenire sui dati delle operazioni di Dynamics AX online, dalla creazione di nuovi record alle query per i dati.
* **Due nuovi servizi dei partner** : ora è possibile usare appFigures o insightly dai flussi.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/more-september-updates/) su questa versione.

### <a name="release-2016-09-14"></a>Versione 2016-09-14
* **Incorporamento nel sito Web o nell'app** : gli sviluppatori possono ora incorporare Microsoft Flow direttamente nelle app o nei siti Web per offrire agli utenti un modo semplice per automatizzare le attività personali o professionali.
* **Usare un flusso come endpoint HTTP** : ora è possibile usare un flusso come un'API HTTP. È presente un trigger denominato request all'interno di Flow ed è possibile scegliere di rispondere alla richiesta in ingresso aggiungendo una scheda di risposta.
* **Supporto Todoist** : Todoist offre una prospettiva su tutti i progetti, al lavoro e a casa.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/extend-web-site-application/) su questa versione.

### <a name="release-2016-09-01"></a>Versione 2016-09-01
Microsoft Flow ora disponibile per tutti gli utenti, abbiamo inizialmente aperto la versione di anteprima solo per gli indirizzi di posta elettronica forniti dall'azienda o dall'Istituto di istruzione, come quelli usati con Office 365 business o Office 365 Enterprise. Attualmente si annuncia che la versione di anteprima è ufficialmente disponibile, gratuita per tutti gli utenti, indipendentemente dalla posta elettronica. [Scopri di più e poni domande](https://flow.microsoft.com/blog/available-for-everyone/) su questa versione.

### <a name="release-2016-08-31"></a>Versione 2016-08-31
* **Condizionali annidati** : ora è possibile aggiungere una seconda condizione (o terza, ecc...) all'interno di un'altra.
* **Apply to each** : un ciclo apply to each consente di controllare l'elenco ripetuto.
* **Do-Until** : un ciclo Do-Until consente di ripetere un passaggio fino a quando non viene soddisfatta una determinata condizione.
* **Filtra matrici** : è disponibile un singolo passaggio di filtro nativo che può garantire che ogni elemento dell'elenco corrisponda a un'espressione definita dall'utente.
* **Comporre le variabili di stringa** : è ora possibile comporre una variabile di stringa.
* **Ambiti** : gli ambiti sono un modo semplice per raggruppare due o più azioni insieme.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/build-advanced-flows/) su questa versione.

### <a name="release-2016-08-27"></a>Versione 2016-08-27
* **Commenti sui passaggi** : i commenti semplificano l'annotazione di ogni singola azione con note, in modo da poter ricordare facilmente il flusso necessario
* **Supporto per Smartsheet** : questa settimana è stato aggiunto il supporto per la connessione a Smartsheet. Smartsheet è un servizio che semplifica la collaborazione con i fogli nel cloud.
* **Perfezionamenti dell'interfaccia utente durante la creazione di flussi** : il nome del flusso è in primo piano e il pulsante Salva è stato spostato nella parte superiore della pagina per facilitarne l'accesso.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/add-comments-smartsheet/) su questa versione.

### <a name="release-2016-08-18"></a>Versione 2016-08-18
È ora possibile visualizzare in anteprima la nuova esperienza degli elenchi moderni di SharePoint Online che include l'integrazione Microsoft Flow. [Scopri di più e poni domande](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) su questa versione.

### <a name="release-2016-08-13"></a>Versione 2016-08-13
* **Visual Studio Team Services** : con Flow è ora possibile connettere VSTS a un'ampia gamma di servizi, ad esempio O365 email, Slack, Trello e Wunderlist.
* I miglioramenti apportati **a SharePoint** : gli elenchi SharePoint supportano una gamma di tipi di dati da oggetti semplici quali singole righe di testo e data e ora a oggetti complessi, ad esempio persona o gruppo, ricerca e scelta.
* **Testare le connessioni di O365 Outlook** : ogni volta che si crea una nuova connessione O365 Outlook, il test verrà testato per assicurarsi di essere pronti a usarlo.
* **Controllo booleano** : è stato aggiunto anche un controllo booleano per chiarire i valori da immettere per i campi di input booleani, ad esempio con allegati in quando viene attivato un nuovo messaggio di posta elettronica.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) su questa versione.

### <a name="release-2016-08-08"></a>Versione 2016-08-08
Anteprima pubblica di Microsoft Common Data Service integrata nella Microsoft Flow. [Scopri di più e poni domande](https://flow.microsoft.com/blog/flow-and-common-data-model/) su questa versione.

### <a name="release-2016-08-05"></a>Versione 2016-08-05
* **SharePoint locale** : Analogamente a SharePoint Online, è possibile creare flussi intorno agli elenchi locali e alle librerie di documenti di SharePoint usando modelli predefiniti o creandoli da zero.
* **Informazioni-bolle nella finestra di progettazione** : per approfondire le funzionalità di ogni trigger e azione, abbiamo aggiunto le bolle di informazioni al di sopra di ogni passaggio del flusso.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) su questa versione.

### <a name="release-2016-07-15"></a>Versione 2016-07-15
* Sono stati **aggiunti quattro nuovi servizi** : Connetti a Google Calendar, Google Tasks, YouTube e SparkPost.
* **Rinominare le azioni** : ora è possibile distinguere le diverse azioni con una ridenominazione.
* **Ritardo per diversi periodi di tempo** : è ora possibile selezionare un numero qualsiasi di secondi, minuti, ore o giorni.
* **Visualizzatore cartelle più semplice** : è stato semplificato il visualizzatore cartelle. ora, selezionando a sinistra, la cartella verrà selezionata e verrà visualizzata la cartella a destra per poter scegliere le sottocartelle all'interno.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/new-google-services-rename-more/) su questa versione.

### <a name="release-2016-07-08"></a>Versione 2016-07-08
Connettività locale per Microsoft Flow usando il gateway dati locale. In questo modo è possibile stabilire connessioni protette per SQL Server e integrarle con i flussi. [Scopri di più e poni domande](https://flow.microsoft.com/blog/on-premises-data-gateway/) su questa versione.

### <a name="release-2016-07-02"></a>Versione 2016-07-02
* **Supporto per fogli Google** : in passato, abbiamo avuto la possibilità di usare Excel, oltre a Google Drive, ma questa settimana stiamo aggiungendo il supporto nativo di Google sheets.
* Per iniziare a **usare più rapidamente i modelli** , sono state apportate anche alcune ottimizzazioni per il modo in cui è possibile iniziare da modelli. A questo punto, è possibile selezionare gli account che si vuole usare per un modello direttamente inline nella pagina del modello.
* **Nessuna autorizzazione in scadenza per SharePoint e Office 365** -ora Microsoft Flow rinnova automaticamente l'accesso ai servizi basati su Azure Active Directory, quindi tutti i flussi continueranno a funzionare tra le modifiche delle password.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/more-june-updates/) su questa versione.

### <a name="release-2016-06-20"></a>Versione 2016-06-20
* **Introduzione alla nuova app per dispositivi mobili per Microsoft Flow** -oggi, siamo lieti di introdurre un'altra parte importante dell'offerta: un'app per dispositivi mobili ora disponibile per il download in iOS (presto anche in Android) che ti permette di gestire, monitorare ed esplorare il tuo flussi di lavoro automatizzati in qualsiasi momento e ovunque.  
* **Single Sign-on** : è stata implementata Single Sign-on che consente di eseguire l'autenticazione per Microsoft Flow con altri servizi Microsoft come Office 365.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) su questa versione.

### <a name="release-2016-06-18"></a>Versione 2016-06-18
* **Nuovo servizio di posta elettronica** : è ora possibile inviare messaggi di posta elettronica direttamente da Microsoft Flow, senza la necessità di connettersi agli account personali o di posta elettronica di lavoro all'interno di Microsoft Flow.
* **Notifiche nel portale** : ora è possibile visualizzare le notifiche nella parte superiore del portale ogni volta che un elemento si interrompe con i flussi.
* **Tutte le attività nel portale** : ora è possibile visualizzare l'attività in tutti i flussi facendo clic sulla scheda nuova attività nel sito Web di Microsoft Flow.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/mail-and-all-activity/) su questa versione.

### <a name="release-2016-05-27"></a>Versione 2016-05-27
* **Esplorare i modelli in base al servizio** : è ora disponibile un modo per visualizzare tutti i servizi supportati (senza dover eseguire l'accesso). Da questa pagina è possibile visualizzare una descrizione di ognuno dei servizi ed esaminare i modelli per il servizio in questione.
* **Creare e usare i connettori personalizzati** , esattamente come è possibile creare connettori personalizzati in PowerApps, è anche possibile connettersi alle API direttamente in flow.Microsoft.com:
* **Testare i flussi prima di terminare** : ogni volta che si salva un flusso, è ora possibile visualizzare i risultati dell'esecuzione del flusso nella pagina, se si esegue l'azione di avvio.

[Scopri di più e poni domande](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) su questa versione.

### <a name="release-2016-05-07"></a>Versione 2016-05-07
Sono stati aggiunti due nuovi servizi: Microsoft Project online e Mandrill by MailChimp. [Scopri di più e poni domande](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) su questa versione.

### <a name="release-2016-04-27---public-preview"></a>Versione 2016-04-27-anteprima pubblica
Se sono stati usati i flussi logici come parte di [Microsoft PowerApps](https://powerapps.microsoft.com), la versione di anteprima Microsoft Flow offre diverse nuove funzionalità:

* È ora possibile esplorare una raccolta di dozzine di modelli e ordinarli in base alla popolarità, al nome o alla data pubblicata.
* È possibile [pubblicare modelli personalizzati](publish-a-template.md) nella raccolta dopo aver personalizzato un flusso.
* È possibile visualizzare la cronologia per ogni controllo ed esecuzione del flusso.
* Quando si salva un flusso, è possibile [guardarlo in azione immediatamente](see-a-flow-run.md) eseguendo semplicemente l'azione trigger.
* Abbiamo una [nuova community](https://go.microsoft.com/fwlink/?LinkID=787467) per discutere di Flow o [inviare le tue idee](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Passaggi successivi
In caso di problemi non ancora trattati nelle presenti note sulla versione o nelle [domande frequenti](frequently-asked-questions.md), [partecipare alla community](https://go.microsoft.com/fwlink/?LinkID=787467) per porre domande oppure contattare il [supporto tecnico](https://go.microsoft.com/fwlink/?LinkID=787479).

