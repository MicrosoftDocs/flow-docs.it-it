---
title: Sostituire i flussi di lavoro di Common Data Service classici con Microsoft Flow | Microsoft Docs
description: Descrive Microsoft Flow funzionalità e i modelli consigliati per usare Flow anziché un flusso di lavoro classico.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c824f726df991aba9aa1290eb117cf87113041a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548515"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Sostituire i flussi di lavoro di Common Data Service classici con i flussi
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Questo argomento mette a confronto le funzionalità di Microsoft Flow con il flusso di lavoro classico.

Microsoft Flow presenta vantaggi significativi rispetto al modello di flusso di lavoro classico; si consiglia di usare Microsoft Flow per automatizzare i processi anziché il flusso di lavoro classico. 

Creare flussi invece dei flussi di lavoro di Common Data Service classici per creare nuovi processi di automazione. Inoltre, è consigliabile esaminare i processi di flusso di lavoro classici esistenti e prendere in considerazione la possibilità di sostituirli con i flussi.

## <a name="feature-capability-comparison"></a>Confronto funzionalità funzionalità

In questa tabella viene riepilogato un confronto tra le funzionalità di Microsoft Flow e dei flussi di lavoro classiche. 

*Si aggiungono continuamente nuove funzionalità ai Microsoft Flow in modo che siano alla pari e addirittura migliori delle funzionalità di flusso di lavoro classiche. Verranno aggiornate le informazioni contenute in questa tabella come Microsoft Flow acquisisce funzionalità; controllare spesso. Per informazioni sulle funzionalità di flusso imminenti che consentiranno di sostituire il flusso di lavoro classico con Flow, vedere Novità [e pianificazioni per Microsoft Flow](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) nelle note sulla versione di aprile 2019.*

<table>
<tr>
<th colspan="2">Funzionalità</th>
<th>Microsoft Flow</th>
<th>Flusso di lavoro classico</th>
</tr>
<tr>
<td rowspan="5">Modeling</td>
<td>Diramazione condizionale</td>
<td>Sì</td>
<td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ciclo
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Condizioni di attesa nei campi
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ramo parallelo
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Connettori predefiniti a sistemi esterni (trigger ed esecuzione di azioni in servizi esterni)
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Composizione
                    
                </td>
                <td>
                    
   Contenuto dinamico
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Accesso alla pre-immagine dei dati dell'evento
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Esegui i flussi di lavoro figlio
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Eseguire azioni Common Data Service (incluso personalizzato)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Eseguire attività del flusso di lavoro personalizzate
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Raggruppare i passaggi da eseguire in una transazione
                    
                </td>
                <td>
                    
   Sì (insiemi di modifiche)
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Flussi di lavoro di approvazione
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Esecuzione
                    
                </td>
                <td>
                    
   Attiva modifiche ai campi
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Attivare in modo condizionale i valori dei campi (ad esempio, in una determinata data in un campo di data)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Attiva su più eventi di entità Common Data Service
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Esegui su richiesta
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ambiti RunAs    <br/>
   (ad esempio, Organization, business unit, User)
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Esegui in base a una pianificazione
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Esegui in modo sincrono (in tempo reale)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Cronologia
                    
                </td>
                <td>
                    
   Controllo
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Eseguire analisi
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Creazione e portabilità
                    
                </td>
                <td>
                    
   Supporto della soluzione
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Finestra di progettazione moderna
                    
                </td>
                <td>
                    
   Sì
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
<td>Creazione assistita da intelligenza artificiale</td>
<td>Sì</td>
<td>No</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Scenario di esempio: sostituire il flusso di lavoro con un flusso

Si immagini uno scenario di vendita in cui è stata rilasciata una citazione per un cliente e che ora è necessario richiedere l'approvazione del team di gestione prima di inviare le virgolette al cliente. Con i flussi di lavoro classici, questo non sarebbe stato facile e la maggior parte delle soluzioni a questo scopo richiederebbe a uno sviluppatore di scrivere attività del flusso di lavoro personalizzate per recuperare le voci delle virgolette.

Con i flussi, questo è più semplice da compilare come illustrato nella procedura dettagliata in un secondo momento, in cui vengono illustrate alcune delle funzionalità Microsoft Flow per supportare lo scenario. Sono inclusi:

-   Creazione di un flusso che viene eseguito su richiesta

-   Recupero di un elenco di record correlati a un'entità Common Data Service

-   Ciclo su un elenco di record

-   Invio di richieste di approvazione

Per consentire al venditore di attivare la richiesta di approvazione su richiesta:

1. Accedere per [Microsoft Flow](https://flow.microsoft.com/) e creare un flusso in una soluzione. Altre informazioni: [creare un flusso in una soluzione](create-flow-solution.md). 

1. Dall'elenco dei trigger selezionare **Common Data Service (ambiente corrente): quando viene selezionato un record** e selezionare **virgolette** come entità. Questo trigger consente di eseguire un flusso su richiesta su un record o un elenco di record.

1. Con il trigger configurato, aggiungere azioni da eseguire nel flusso. In questo modo il responsabile approvazione fornirà i dettagli di riepilogo necessari per identificare gli elementi e i valori tra virgolette. Per iniziare, aggiungere l'azione **Common Data Service (ambiente corrente) – elenco record** . Poiché si desidera ottenere singole voci da un'offerta, impostare l'entità su **quote Lines**. Per assicurarsi di elencare solo le voci delle virgolette che appartengono all'offerta per la quale è stato attivato il flusso, si specificherà un criterio di filtro di stile OData. Nel campo **query filtro** Digitare *\_EQ quoteid_value* , quindi selezionare *quote* nell'elenco di valori dinamici visualizzati.

    ![Definire il flusso](media/define-flow-1.png "Definire il flusso")

1. Per riepilogare le voci di virgolette per l'approvazione, aggiungere l'azione **Inizializza variabile** . Impostare il campo **nome** su *virgolette di riepilogo* e il **tipo** su stringa (dall'elenco a discesa) e lasciare vuoto il campo **valore** .

1. Aggiungere l'azione **Accoda a variabile stringa** e quindi selezionare la variabile di *Riepilogo della riga di virgoletta* creata in precedenza. Nel campo **valore** selezionare *quantità, nome, prezzo per unità, importo esteso e importo manuale* dall'elenco di valori dinamici. La finestra di progettazione Microsoft Flow identifica che questi valori si trovano in un elenco di voci di virgolette e aggiunge questa azione in un ciclo **applica a ogni** per assicurarsi che le informazioni di ogni voce vengano aggiunte al riepilogo.

    ![Definire il flusso](media/define-flow-2.png "Definire il flusso")

1. Per richiedere l'approvazione per il riepilogo delle virgolette creato, aggiungere l' **approvazione: avviare e attendere un'azione di approvazione** . Selezionare un tipo di approvazione (ad esempio, approva/rifiuta – First per rispondere), fornire alla richiesta di approvazione un **titolo** , ad esempio il nome dell'offerta per cui viene richiesta l'approvazione, selezionato nell'elenco dei valori dinamici, immettere l'indirizzo di posta elettronica per il persona che deve rivedere e approvare le virgolette nel campo **assegnato a** . Nel campo Dettagli aggiungere la variabile di *Riepilogo della riga di virgolette* , insieme a tutte le altre informazioni che potrebbero essere rilevanti usando la selezione di valori dinamici (ad esempio, importo totale).

1. Per determinare cosa accade quando un'approvazione viene accettata o rifiutata, aggiungere l'azione della **condizione** . Selezionare *risultato* dall'elenco di valori dinamici dal primo campo della condizione, *contenuto* nell'elenco a discesa nel secondo campo e immettere *Accept* nel terzo campo della condizione. Infine, aggiungere azioni in base al risultato dell'approvazione (ad esempio, inviare un messaggio di posta elettronica di notifica).

    ![Definire il flusso](media/define-flow-3.png "Definire il flusso")

A questo punto è stata creata la struttura di approvazione in modo che il responsabile approvazione disponga di tutte le informazioni necessarie per prendere una decisione sui passaggi successivi. Ecco il flusso di esempio completo su richiesta per richiedere l'approvazione:

![Struttura del flusso di approvazione](media/approval-flow-structure.png "Struttura del flusso di approvazione")

Quando si esegue questo flusso in base alle virgolette, vengono riepilogate le virgolette per tale virgoletta e viene inviata una richiesta di approvazione che il responsabile approvazione può rispondere a da Microsoft Flow o il messaggio di posta elettronica di cui è possibile eseguire l'azione che ricevono. Di seguito è riportato un esempio di visualizzazione:

![Flusso in azione](media/flow-in-action.png "Flusso in azione")

## <a name="recommended-patterns"></a>Modelli consigliati


-   **Flussi di lavoro con la logica condizionale Else-If**  
    
    Anziché utilizzare le condizioni, è consigliabile utilizzare l' [azione switch](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement) .

-   **Flussi di lavoro eseguiti dal plug-in/codice**  
    
    È consigliabile riprogettare il flusso per iniziare con i trigger.

    -   Usare i trigger Common Data Service per eseguire i flussi in base agli eventi al suo interno.

    -   Per eseguire i flussi in base agli eventi in un servizio esterno, sfruttare più di 260 connettori predefiniti.

    -   Per gli scenari in cui è necessario un connettore non disponibile, è possibile creare facilmente un connettore personalizzato [per imparare a creare connettori personalizzati](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Infine, se esistono scenari in cui non è possibile attivare il flusso con Common Data Service connettore, uno dei connettori predefiniti o creare un connettore personalizzato, sfruttare il [trigger quando viene ricevuta una richiesta http](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) per richiamare il flusso

-   **Flussi di lavoro eseguiti in modo ricorsivo**  
    
    Usare invece il ciclo [Do-Until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) o [apply to Each](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop) in Flows

-   **Flussi di lavoro che richiedono un elenco di record**  
    
    Usare l'azione **Elenca record** . Quando si usa questa azione, definire i criteri di filtro dei record usando la sintassi OData per ottimizzare l'azione riducendo al minimo il numero di record che si vuole recuperare.

-   **Flussi di lavoro in sospensione per l'esecuzione in base a una pianificazione**  
    
    Utilizzare il trigger di **ricorrenza** per eseguire la logica di business a intervalli periodici.

-   **Flussi di lavoro per cui sono state gestite le esecuzioni per garantire l'esecuzione delle attività in un'unica transazione**  
    
    [Usare l' [azione](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) dell'insieme di modifiche per assicurarsi che tutte le azioni al suo interno vengano eseguite come una singola unità atomica in cui tutti hanno esito positivo o negativo come gruppo. Se una delle azioni di un set di modifiche ha esito negativo, viene eseguito il rollback delle modifiche apportate dalle operazioni completate.

-   **Monitorare le esecuzioni del flusso di lavoro per gli errori**  
    
    In Microsoft Flow, utilizzare l' **impostazione Esegui dopo** in un'azione per configurarla per l'esecuzione in caso di esito negativo dell'azione precedente. Ad esempio, inviare una notifica Microsoft Flow mobile quando l'azione **Aggiorna un record** ha esito negativo o scade.

## <a name="faqs"></a>FAQ


-   **Ho una licenza di Dynamics 365. È possibile utilizzare Microsoft Flow?**

    Ogni utente di Dynamics 365 è autorizzato a usare Microsoft Flow. Esaminare le informazioni sulle licenze: <https://flow.microsoft.com/pricing/>

-   **Con quale frequenza è possibile attivare i flussi?**

    -   I flussi di Dynamics 365 (o Common Data Service) vengono eseguiti quasi in tempo reale dopo il trigger perché usano webhook (nessun polling necessario)

    -   Come per l'accesso diretto alle API, nel sistema sono presenti limitazioni/limiti, completamente documentati qui: <https://docs.microsoft.com/flow/limits-and-config>

    -   In particolare, è previsto un limite di 100.000 azioni per 5 minuti, per flusso e un singolo ciclo in un flusso non può elaborare più di 100.000 elementi contemporaneamente

    -   Massimo 6 GB di velocità effettiva per 5 minuti

-   **Per quanto tempo è possibile eseguire un singolo flusso?**  
    
    Si verifica il timeout di una singola esecuzione del flusso dopo 30 giorni.

-   **Ricerca per categorie spostare i flussi tra gli ambienti?**  
    
    Proprio come i flussi di lavoro classici, è possibile creare flussi nelle soluzioni per supportare il ciclo di vita dell'applicazione completo per i processi.

-   **Le dipendenze Microsoft Flow registrate in Common Data Service?**  
    
    Analogamente ad altri componenti in una soluzione, tutte le dipendenze per i flussi nelle soluzioni vengono registrate in Common Data Service.

-   **Quali sono i flussi di lavoro sincroni?** 
 
    È necessario rivalutare la necessità di flussi di lavoro sincroni per identificare se l'obiettivo o parti del flusso di lavoro possono essere compilate utilizzando un flusso. In particolare, dai dati di telemetria i flussi di lavoro sincroni rappresentano un collaboratore significativo all'esperienza complessiva di prestazioni insufficienti per gli utenti finali. Per molti utilizzi, sebbene sia preferibile suddividere queste azioni come asincrone, in modo che l'utente possa continuare con l'attività mentre Microsoft Flow continua a garantire il completamento dell'azione.

-   **Con Microsoft Flow, i dati vengono mantenuti all'interno dell'area (ovvero la stessa area dell'ambiente Dynamics 365 o Common Data Service)?**  
    
    Sì, Microsoft Flow usa sempre la stessa area Common Data Service.

-   **È necessario apportare modifiche al proxy/firewall?**  
    
    Vedere riferimento alla [configurazione degli indirizzi IP](limits-and-config.md#ip-address-configuration) per stabilire se è necessario apportare modifiche al proxy o al firewall.
