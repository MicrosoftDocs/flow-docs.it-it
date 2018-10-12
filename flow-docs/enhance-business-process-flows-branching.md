---
title: Migliorare i processi aziendali con la creazione dei rami | MicrosoftDocs
description: Informazioni su come usare la creazione dei rami in un processo aziendale
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a7e1dc8d366ac9f23682362c8a673eb67df65975
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690515"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Esercitazione: Migliorare i processi aziendali con la creazione dei rami

I processi aziendali consentono di familiarizzare con le varie fasi dei processi di vendita, marketing o servizio fino al completamento. Nei casi più semplici, è consigliabile scegliere un processo aziendale lineare. Tuttavia, in scenari più complessi è possibile migliorare un processo aziendale usando i rami. Se per il processo aziendale si dispone delle autorizzazioni di creazione, sarà possibile creare un processo aziendale con più rami usando la logica `If-Else`. La condizione per la creazione dei rami può essere costituita da più espressioni logiche che usano una combinazione di operatori `AND` e `OR`. Il ramo viene selezionato automaticamente in tempo reale, in base alle regole stabilite durante la definizione del processo. Ad esempio, per la vendita di automobili è possibile configurare un singolo processo aziendale che, dopo una fase di qualifica si divide in due rami distinti in base a una regola (il cliente preferisce una automobile nuova o un'automobile usata, il suo budget è superiore o inferiore a 20.000 dollari, e così via). Un ramo sarà riservato alla vendita di automobili nuove mentre l'altro alla vendita di automobili usate. Per informazioni sui processi aziendali, vedere [Panoramica dei processi aziendali](business-process-flows-overview.md).  
  
 Il diagramma seguente illustra un processo aziendale in cui sono stati creati rami.  
  
 ![Diagramma di flusso che illustra il processo di vendita di automobili](media/example-car-sales-flow-chart.png "Diagramma di flusso che illustra i passaggi del processo di vendita di automobili")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Informazioni necessarie per la progettazione di un processo aziendale con i rami  
 Tenere conto delle informazioni seguenti durante la progettazione di un processo aziendale con i rami:  
  
-   Un processo può contemplare un massimo di 5 entità univoche.  
  
-   È possibile usare un massimo di 30 fasi per ogni processo e un massimo di 30 passaggi per ogni fase.  
  
-   La profondità di ogni ramo non può superare i 5 livelli.  
  
-   La regola di creazione dei rami si deve basare sui passaggi della fase immediatamente precedente.  
  
-   È possibile combinare più condizioni in una regola usando l'operatore `AND` o `OR`, ma non è possibile usare entrambi gli operatori.  
  
-   Quando si definisce un processo, è facoltativamente possibile selezionare una relazione di entità. Si deve trattare di una relazione uno-a-molti (1:N).  
  
-   Nello stesso record di dati possono essere eseguiti simultaneamente più processi attivi.  
  
-   È possibile trascinare e rilasciare i riquadri (Fasi, Passaggi, Condizioni, e così via) per riorganizzarli nel processo.  
  
-   Durante l'unione dei rami, tutti i rami peer devono essere uniti per formare un'unica fase. È necessario che tutti i rami peer siano uniti in un'unica fase, oppure ogni ramo peer dovrà terminare il processo. Un ramo peer non può unirsi ad altri rami e al tempo stesso terminare il processo.  
  
> [!NOTE]
> - È possibile accedere più volte a un'entità usata nel processo (più cicli di entità chiusi).  
> - Un processo può tornare alla fase precedente indipendentemente dal tipo di entità. Ad esempio, se è la fase attiva è **Deliver Quote** in un record di offerta, gli utenti possono tornare alla fase attiva **Propose** in un record di opportunità.  
>   
>   In un altro esempio, si supponga che un processo si trovi attualmente nella fase **Present Proposal**: **Qualify Lead** > **Identify Needs** > **Create Proposal** > **Present Proposal** > **Close**. Se la proposta presentata al cliente richiede un'indagine più approfondita per identificare le esigenze del cliente, gli utenti possono semplicemente selezionare la fase **Identify Needs** del processo e scegliere **Set Active**.  
  
<a name="CarSelling365"></a>   
## <a name="dynamics-365-customer-engagement-example-car-selling-process-flow-with-two-branches"></a>Esempio di Dynamics 365 Customer Engagement: Processo di vendita di automobili con due rami
 
Esaminiamo l'esempio del processo aziendale con due rami, per la vendita di automobili nuove e usate.  
  
 Verrà prima creato un nuovo processo denominato **Car Sales Process**.  
  
1.  [Aprire Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e nel riquadro di spostamento a sinistra selezionare **Processi**.  
  
2.  Selezionare **Nuovo** per creare un nuovo processo.  
  
3.  In **Categoria** specificare **Processo aziendale** e in **Entità** scegliere **Lead**.  
  
4.  Aggiungere la prima fase al processo denominata **Qualify** e aggiungervi i passaggi **Purchase Time frame** e **Car Preference**.  
  
5.  Dopo la comune fase **Qualify**, il processo viene suddiviso in due rami separati, usando il riquadro **Condizione**.  
  
    1.  Configurare il riquadro delle condizioni usando regole che soddisfano i requisiti aziendali  
  
    2.  Per aggiungere il primo ramo a una fase, aggiungere un riquadro della fase nel percorso "Yes" del riquadro delle condizioni  
  
    3.  Per aggiungere il secondo ramo che viene eseguito quando la condizione non viene soddisfatta, aggiungere un altro riquadro della fase nel percorso "No" del riquadro delle condizioni.  
  
> [!TIP]
>  È possibile aggiungere un'altra condizione nel percorso "No" di un riquadro delle condizioni esistente per creare una struttura a rami più complessa.  
  
 ![Immagine della fase di qualifica creata](media/example-car-sales-qualify-stage.JPG "Immagine della fase di qualifica creata")  
  
 Se **Car preference** = **New**, il processo passa alla fase **New Car Sales**, in caso contrario, passa alla fase **Pre-Owned Car Sales** nel secondo ramo, come illustrato di seguito.  
  
 ![Immagine della fase di vendita di automobili nuove](media/example-car-sales-new-stage-1.JPG "Immagine della fase di vendita di automobili nuove")  
  
 ![Fase di vendita di automobili usate](media/example-car-sales-pre-owned-stage.JPG "Fase di vendita di automobili usate")  
  
 Dopo aver completato tutti i passaggi nella fase **New Car Sales** o **Pre-Owned Car Sales**, il processo torna al flusso principale, vale a dire alla fase **Deliver Quote**.  
  
 ![Fase di invio dell'offerta](media/example-car-sales-deliver-quote-stage.JPG "Fase di invio dell'offerta")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Impedire la diffusione di informazioni  
 Si consideri un processo aziendale con rami per l'elaborazione di una richiesta di prestito bancario, come illustrato di seguito. Le entità personalizzate usate nelle fasi sono visualizzate tra parentesi.  
  
 ![Diagramma dei passaggi in un processo di esempio per impedire la diffusione di informazioni](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Diagramma dei passaggi in un processo di esempio per impedire la diffusione di informazioni")  
  
 In questo scenario il responsabile prestiti della banca deve poter accedere al record Request, ma non può avere visibilità sull'indagine della richiesta. A prima vista, sembrerebbe sufficiente assegnare al responsabile prestiti un ruolo di sicurezza in cui si specifica il divieto di accesso all'entità Investigation. Esaminiamo però l'esempio più nel dettaglio per considerare valida questa soluzione.  
  
 Si supponga che un cliente richieda alla banca un prestito di oltre 60.000 dollari. Nella prima fase il responsabile esamina la richiesta. Se viene soddisfatta la regola del ramo che controlla se l'importo dovuto alla banca supererà i 50.000 dollari, la fase successiva del processo sarà stabilire se la richiesta è di tipo fraudolento. Se si stabilisce che si tratta effettivamente di un caso di frode, il processo passerà all'apertura di un'azione legale nei confronti del richiedente. Non potendo accedere all'entità Investigation, il responsabile prestiti non avrà visibilità sulle due fasi investigative.  
  
 Tuttavia, se il responsabile apre il record Request, potrebbe visualizzare l'intero processo in tutte le sue fasi. Non solo potrà visualizzare la fase di indagine sulla frode, ma potrà anche risalire all'esito dell'indagine, dal momento che può visualizzare la fase Legal Action del processo. Selezionando la fase potrà anche visualizzare l'anteprima dei passaggi delle fasi di indagine. Anche se non potrà visualizzare i dati o lo stato di completamento della fase, potrà conoscere le possibili azioni intraprese nei confronti del richiedente durante le fasi di indagine e di azione legale.  
  
 In questo processo il responsabile prestiti visualizzerà le fasi Fraud e Legal Action, che costituiscono un'errata diffusione di informazioni. È consigliabile prestare particolare attenzione alle informazioni che possono essere diffuse in seguito alla creazione dei rami. In questo esempio, per evitare la diffusione di informazioni, è necessario suddividere il processo in due processi distinti, uno per l'elaborazione della richiesta e un altro per le attività di indagine sulla frode. Il processo per il responsabile sarà il seguente:  
  
 ![Diagramma dei passaggi aggiuntivi in un processo per impedire la diffusione di informazioni](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Diagramma dei passaggi aggiuntivi in un processo per impedire la diffusione di informazioni")  
  
 Il processo relativo all'indagine sarà autonomo e includerà le fasi seguenti:  
  
 ![Diagramma dei passaggi aggiuntivi in un processo di indagine per casi di diffusione di informazioni](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Diagramma dei passaggi aggiuntivi in un processo di indagine per casi di diffusione di informazioni")  
  
 Per sincronizzare la decisione di approvazione o negazione dal record Investigation al record Request, sarà necessario usare un flusso di lavoro.  
  
### <a name="next-steps"></a>Passaggi successivi  
 [Creare un processo aziendale](create-business-process-flow.md)   
 [Creare una logica di business personalizzata tramite i processi](guide-staff-through-common-tasks-processes.md)   
 
