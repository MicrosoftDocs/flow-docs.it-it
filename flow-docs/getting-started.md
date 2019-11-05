---
title: Introduzione | Microsoft Docs
description: Modi rapidi per iniziare ad automatizzare il lavoro e la vita con Power automatizzato
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 54d1478f34743b6059692b927da8baf2c49a35a7
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589840"
---
# <a name="get-started-with-power-automate"></a>Introduzione a Power Automate

[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/hCuxuUaGC6Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Benvenuto! Power automatizzate è un servizio che consente di creare flussi di lavoro automatizzati tra le app e i servizi preferiti per sincronizzare file, ricevere notifiche, raccogliere dati e altro ancora.

I tipi principali di flussi sono i flussi [automatici](get-started-logic-flow.md), di [pulsanti](introduction-to-button-flows.md), [pianificati](run-scheduled-tasks.md)e di [processi aziendali](business-process-flows-overview.md) .

## <a name="types-of-flows"></a>Tipi di flussi

Power automatizzate è uno dei tre pilastri della piattaforma Power. Fornisce una piattaforma di codice bassa per l'automazione di flussi di lavoro e processi. Ecco un elenco dei diversi tipi di flussi:

| **Tipo di flusso**                                                                       | **Caso d'uso**                                                                                  | **Destinazione**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Flussi automatizzati](get-started-logic-flow.md)                 | Creare un flusso che esegua una o più attività automaticamente dopo che è stato attivato da un evento. | [Connettori](https://docs.microsoft.com/connectors/) per servizi cloud o locali. |
| [Flussi di pulsanti](introduction-to-button-flows.md)              | Esegui attività ripetitive da qualsiasi luogo, in qualsiasi momento, tramite il tuo dispositivo mobile.                        |                                                                                        |
| [Flussi pianificati](run-scheduled-tasks.md)                    | Creare un flusso che esegua una o più attività in base a una pianificazione.             |                                                                                        |
| [Flussi del processo di business](business-process-flows-overview.md) | Definire una serie di passaggi che gli utenti devono seguire per portarli a un risultato desiderato.                 | Processi umani                                                                        |
| [Flussi dell'interfaccia utente (anteprima)](ui-flows/overview.md)                                                | Registrare e automatizzare la riproduzione dei passaggi manuali sul software legacy.                    | Applicazioni desktop e Web che non dispongono di API disponibili per l'automazione.    |

È possibile creare e gestire tutti i flussi dalla scheda **flussi personali** in Power automatizzate.

Gli utenti di Dynamics 365 possono anche avere familiarità con i processi di Common Data Service classici che includono, [flussi di lavoro](configure-workflow-steps.md), [azioni](create-actions.md), [flussi di attività per dispositivi mobili](create-mobile-task-flow.md)e [finestre di dialogo](use-cds-for-apps-dialogs.md).

Il primo passaggio consiste nell' [iscriversi](sign-up-sign-in.md)oppure, se si dispone già di un account con Power Automate, [accedere](https://flow.microsoft.com/signin) al tablet, al computer desktop o addirittura al telefono.

## <a name="check-out-the-start-page"></a>Vedere la pagina iniziale ##

[Nella pagina iniziale](https://flow.microsoft.com) di Power Automate è possibile [esplorare un set eterogeneo di modelli](https://flow.microsoft.com/templates) e ottenere informazioni sulle funzionalità chiave per l'automazione dell'energia elettrica. È possibile ottenere una rapida idea delle operazioni possibili e del modo in cui Power automatizzate può aiutare la propria azienda e la propria vita.

Con l'automazione dell'energia elettrica è possibile:

- Ricerca di modelli e servizi con facilità.

    ![Pagina iniziale del flusso 1](./media/getting-started/flowhome1.png)

- È possibile scegliere tra i servizi più diffusi.

    ![Pagina iniziale del flusso 2](./media/getting-started/flowhome2.png)

- Vedere una panoramica di ogni flusso.

    ![Pagina iniziale del flusso 3](./media/getting-started/flowhome3.png)

Ogni modello è progettato per uno scopo specifico. Ad esempio, sono disponibili modelli per l'invio di un messaggio di testo quando il capo Invia un messaggio di posta elettronica all'utente, aggiungendo i lead di Twitter a Dynamics 365 o eseguendo il backup dei file. Questi modelli sono solo la punta dell'iceberg. Hanno lo scopo di ispirarti alla creazione di flussi personalizzati per i processi esatti che ti servono.

## <a name="create-your-first-flow"></a>Creare il primo flusso ##

1. Selezionare un modello utile. Un modello semplice consiste [**nel ricevere promemoria giornalieri nella posta elettronica**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![modello di promemoria giornaliero](./media/getting-started/template-details.png)

1. Selezionare **continua**.

    ![Crea connessione](./media/getting-started/create-connection.png)

1. Immettere gli indirizzi di posta elettronica a cui verrà inviato il promemoria giornaliero. Immettere quindi il messaggio di promemoria. Infine, selezionare **Crea flusso**, quindi verificare che il flusso sia in esecuzione come previsto.

    ![Fornire le credenziali per la connessione](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > È possibile esplorare le condizioni che attivano il flusso e l'azione risultante da tale evento. Provare a usare le impostazioni per creare il flusso. È anche possibile aggiungere o eliminare azioni.

1. Selezionare **fine**.

[Seguire questa esercitazione](get-started-logic-template.md) per altre informazioni sulla creazione di flussi dai modelli.

## <a name="get-creative"></a>Ottieni la creatività ##

Ora che è stato creato il primo flusso da un modello, usare una delle [origini dati](https://flow.microsoft.com/connectors/) più di 150 che Power automatizzate supporta per [creare flussi personalizzati da zero](get-started-logic-flow.md).

![Creazione di un flusso](./media/getting-started/build-a-flow.png)

Quando si crea un flusso da zero, si controlla l'intero flusso di lavoro. Ecco alcune idee per iniziare:

- [Scorre con molti passaggi](multi-step-logic-flow.md).
- [Eseguire attività in base a una pianificazione](run-scheduled-tasks.md).
- [Creare un flusso di approvazione](wait-for-approvals.md).
- [Osservare un flusso in azione](see-a-flow-run.md).
- [Pubblicare un modello](publish-a-template.md).
- [Creare flussi da un modello di Microsoft teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Visualizza il codice

Non è necessario essere uno sviluppatore per creare flussi. Tuttavia, Power automatizzate fornisce una funzionalità di **visualizzazione del codice** che consente a chiunque di esaminare più in dettaglio il codice generato per tutte le azioni e i trigger in un flusso. La visualizzazione del codice potrebbe offrire una migliore comprensione dei dati usati da trigger e azioni. Seguire questa procedura per visualizzare il codice generato per i flussi dall'interno della finestra di progettazione di Power automatici: 

1. Selezionare la voce di menu **...** nell'angolo superiore destro di qualsiasi **azione** o **trigger**. 
1. Selezionare **Visualizza codice**.

    ![Visualizza codice](media/getting-started/peek-code.png)

1. Si noti la rappresentazione JSON completa delle azioni e dei trigger. Sono inclusi tutti gli input, ad esempio il testo immesso direttamente e le espressioni usate. È possibile selezionare le espressioni e incollarle nell'editor espressioni di **contenuto dinamico** . Questo può anche fornire un modo per verificare che i dati previsti siano presenti nel flusso.

    ![Visualizza codice](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Trova facilmente i flussi

Quando i succhi creativi iniziano a *fluire*, è possibile creare molti flussi. Non preoccuparti, trovare i flussi è facile: è sufficiente usare la casella di ricerca nella schermata **flussi personali**, **flussi del team**, **connessioni**o **soluzioni** per visualizzare solo i flussi che corrispondono ai termini di ricerca immessi.

![Filtra o Cerca flussi](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Il filtro di ricerca trova solo i flussi che sono stati caricati nella pagina. Se il flusso non viene trovato, provare a selezionare **carica altro** nella parte inferiore della pagina.

## <a name="get-notifications-when-somethings-wrong"></a>Ricevi notifiche quando si verifica un errore

Usare il centro notifiche di Power automatizzate, disponibile in alto a destra nella finestra di progettazione, per visualizzare rapidamente un elenco dei flussi non riusciti di recente. Il centro notifiche Visualizza un numero che indica il numero di flussi non riusciti di recente.

Dal centro notifiche è possibile passare alla pagina **attività** di Power Automate per visualizzare tutti i flussi eseguiti di recente, notifiche inviate o non riusciti.

![Centro notifiche](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Usare l'app per dispositivi mobili ##

Scaricare l'app Power automatizzata per dispositivi mobili per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows). Con questa app è possibile [monitorare l'attività del flusso](mobile-monitor-activity.md), [gestire i flussi](mobile-manage-flows.md) e [creare flussi dai modelli](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Siamo qui per aiutarti ##

Siamo lieti di scoprire cosa fai con Power automatizzate e vogliamo assicurarci che tu abbia un'esperienza ottimale. Assicurarsi di consultare le esercitazioni per l' [apprendimento guidato](https://flow.microsoft.com/guided-learning/) e [partecipare alla community](https://go.microsoft.com/fwlink/?LinkID=787467) per porre domande e condividere le proprie idee. Se si verificano problemi, [contattare il supporto tecnico](https://go.microsoft.com/fwlink/?LinkID=787479) .
