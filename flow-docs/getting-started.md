---
title: Attività iniziali | Microsoft Docs
description: Modalità rapide per iniziare ad automatizzare il lavoro e la vita con Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: hero-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f667401774e49505009cd416f6975ff38683a5c7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035218"
---
# <a name="get-started-with-microsoft-flow"></a>Attività iniziali con Microsoft Flow #

<iframe width="560" height="315" src="https://www.youtube.com/embed/iMteXfAvDSE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Benvenuti. Microsoft Flow è un servizio che consente di creare flussi di lavoro automatizzati tra le app e i servizi preferiti per sincronizzare file, ricevere notifiche, raccogliere dati e altro ancora.

I tipi di flusso principali sono flussi [automatizzati](get-started-logic-flow.md), [attivati da un pulsante](introduction-to-button-flows.md), [pianificati](run-scheduled-tasks.md) e [processi aziendali](business-process-flows-overview.md).

Gli addetti alla personalizzazione di Dynamics 365 Customer Engagement probabilmente conoscono i processi classici di Common Data Service che includono [flussi di lavoro](configure-workflow-steps.md), [azioni](create-actions.md), [flussi di attività per dispositivi mobili](create-mobile-task-flow.md) e [interazioni](use-cds-for-apps-dialogs.md).

Il primo passaggio consiste nel [registrarsi](sign-up-sign-in.md) oppure, se è già disponibile un account con Microsoft Flow, è possibile [accedere](https://flow.microsoft.com/signin) dal proprio tablet, computer desktop o smartphone.

## <a name="check-out-the-start-page"></a>Vedere la pagina iniziale ##

[Nella pagina iniziale](https://flow.microsoft.com) di Microsoft Flow è possibile [esplorare un set eterogeneo di modelli](https://flow.microsoft.com/templates) e ottenere informazioni sulle funzionalità principali di Microsoft Flow. È possibile farsi rapidamente un'idea delle operazioni eseguibili e dell'aiuto offerto da Microsoft Flow per svolgere le attività in ambito professionale e nella vita privata.

Con Microsoft Flow è possibile:

- Cercare facilmente modelli e servizi.

    ![Pagina iniziale di Flow 1](./media/getting-started/flowhome1.png)

- Scegliere tra i servizi più popolari.

    ![Pagina iniziale di Flow 2](./media/getting-started/flowhome2.png)

- Visualizzare una panoramica di ogni flusso.

    ![Pagina iniziale di Flow 3](./media/getting-started/flowhome3.png)

Ogni modello è progettato per uno scopo specifico. Ad esempio, sono disponibili modelli per l'invio di un SMS quando si riceve un messaggio di posta elettronica da mittenti specifici, l'aggiunta di lead di Twitter a Dynamics 365 o la creazione di una copia backup dei file. Questi modelli sono semplicemente alcuni esempi utilizzabili come fonte di ispirazione per creare flussi personalizzati per i processi esatti necessari.

## <a name="create-your-first-flow"></a>Creare il primo flusso ##

1. Selezionare un modello utile. Un modello molto semplice è [**Ricevi promemoria giornalieri nella posta elettronica**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![modello di promemoria giornaliero](./media/getting-started/template-details.png)

1. Selezionare **Continua**.

    ![Creare una connessione](./media/getting-started/create-connection.png)

1. Immettere gli indirizzi di posta elettronica a cui verrà inviato il promemoria giornaliero. Immettere quindi il messaggio di promemoria. Infine, selezionare **Crea flusso**, quindi verificare che il flusso sia in esecuzione come previsto.

    ![Specificare le credenziali per la connessione](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > È possibile esplorare le condizioni che attivano il flusso e l'azione risultante da tale evento. Sperimentare con le impostazioni per personalizzare il flusso. È anche possibile aggiungere o eliminare azioni.

1. Selezionare **Fine**.

[Seguire questa esercitazione](get-started-logic-template.md) per altre informazioni sulla creazione di flussi da modelli.

## <a name="get-creative"></a>Spazio alla creatività ##

Dopo aver creato il primo flusso da un modello, usare una delle più di [150 origini dati](https://flow.microsoft.com/connectors/) supportate da Microsoft Flow per [creare flussi personalizzati da zero](get-started-logic-flow.md).

![Creazione di un flusso](./media/getting-started/build-a-flow.png)

Quando si crea un flusso da zero, si ha il controllo dell'intero flusso di lavoro. Ecco alcune idee per iniziare:

- [Flussi con più passaggi](multi-step-logic-flow.md).
- [Run tasks on a schedule](run-scheduled-tasks.md) (Eseguire attività con una pianificazione).
- [Creare un flusso di approvazione](wait-for-approvals.md).
- [Osservare i flussi in azione](see-a-flow-run.md).
- [Pubblicare un modello](publish-a-template.md).
- [Creare flussi da un modello di Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Visualizza il codice

Non è necessario essere uno sviluppatore di creare flussi, tuttavia, Microsoft Flow forniscono un **Visualizza codice** funzionalità che permette a chiunque di esaminare più da vicino il codice generato per tutte le azioni e trigger in un flusso. Visualizzazione codice è stato possibile consentono di comprendere meglio i dati che sono usati da azioni e trigger. Seguire questi passaggi per visualizzare il codice generato per i flussi da all'interno della finestra di progettazione di Microsoft Flow: 

1. Selezionare il **...**  voce di menu in alto a destra di qualsiasi **azione** oppure **trigger**. 
1. Selezionare **Visualizza codice**.

    ![Visualizza codice](media/getting-started/peek-code.png)

1. Si noti che la rappresentazione JSON completa le azioni e trigger. Sono inclusi tutti gli input, ad esempio il testo che immesso direttamente e le espressioni usate. È possibile selezionare le espressioni qui e quindi incollarli nel **del contenuto dinamico** editor espressioni. Ciò consente anche di visualizzare un modo per verificare i dati che prevede siano presenti nel flusso.

    ![Visualizza codice](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Trovare con facilità i flussi

Quando la creatività succhi inizio *trasmessi*, è possibile creare molti flussi. Non ti preoccupare, la ricerca dei flussi è facile: puoi usare la casella di ricerca nel **flussi personali**, **flussi Team**, **connessioni**, oppure **soluzioni** schermata per visualizzare flussi solo che corrispondono ai criteri di ricerca che immesso.

![Flussi di ricerca o filtro](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Il filtro di ricerca individua solo i flussi che sono stati caricati nella pagina. Se non si trova il flusso, provare a selezionare **carica altro** nella parte inferiore della pagina.

## <a name="get-notifications-when-somethings-wrong"></a>Ricevere notifiche quando qualcosa non va

Usare il centro di notifica di Microsoft Flow (nella parte superiore destra della finestra di progettazione) a rapidamente vedere un elenco dei flussi non riuscite di recente. Il centro notifiche presenta un numero che indica il numero di flussi che non è riuscito recente.

Nell'area di notifica, è possibile passare al **attività** pagina di Microsoft Flow per visualizzare tutti i flussi che di recente è stato eseguito, inviare notifiche o non è riuscita.

![Centro notifiche](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Usare l'app per dispositivi mobili ##

Scaricare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows). Con questa app, è possibile [monitorare l'attività del flusso](mobile-monitor-activity.md), [gestire i flussi](mobile-manage-flows.md) e [creare flussi dai modelli](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Siamo qui per aiutare ##

Per Microsoft è importante scoprire cosa fanno i clienti con Microsoft Flow e assicurare un'esperienza ottimale agli utenti. Consultare le esercitazioni per l'[apprendimento guidato](https://flow.microsoft.com/guided-learning/) e [unirsi alla community](http://go.microsoft.com/fwlink/?LinkID=787467) per porre domande e condividere le proprie idee. [Contattare il supporto tecnico](http://go.microsoft.com/fwlink/?LinkID=787479) se si riscontrano problemi.
