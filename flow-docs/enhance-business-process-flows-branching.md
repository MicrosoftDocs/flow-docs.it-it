---
title: Migliorare i flussi di processi aziendali con la diramazione con PowerApps | MicrosoftDocs
description: Informazioni su come usare la diramazione in un flusso del processo di business
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a03cefcb3e808bb7900b79b05e6c2b3f8ef7f5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544769"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Esercitazione: migliorare i flussi di processi aziendali con la diramazione
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I flussi del processo di business guidano l'utente attraverso diverse fasi di processi di vendite, marketing o servizi verso il completamento. In casi semplici, un flusso del processo di business lineare è una scelta efficace. Tuttavia, in scenari più complessi, è possibile migliorare un flusso del processo di business con la diramazione. Se si dispone delle autorizzazioni di creazione per i flussi del processo di business, sarà possibile creare un flusso del processo di business con più rami utilizzando la logica `If-Else`. La condizione di diramazione può essere costituita da più espressioni logiche che usano una combinazione di operatori `AND` o `OR`. La selezione del ramo viene eseguita automaticamente in tempo reale, in base alle regole definite durante la definizione del processo. Ad esempio, in vendita di automobili, è possibile configurare un singolo flusso del processo di business, che dopo una fase di qualificazione comune si divide in due rami distinti sulla base di una regola (il cliente preferisce una nuova auto o una macchina di proprietà precedente, è il budget superiore o inferiore a $20.000). E così via. ), un ramo, per la vendita di nuove automobili e di un altro ramo, per la vendita di automobili di proprietà predefinite. Per ulteriori informazioni sui flussi del processo di business, vedere [Cenni preliminari sui flussi dei processi di business](business-process-flows-overview.md).  
  
 Il diagramma seguente illustra un flusso del processo di business con rami.  
  
 ![Diagramma di flusso che illustra i passaggi del processo di vendita auto](media/example-car-sales-flow-chart.png "Diagramma di flusso che illustra i passaggi del processo di vendita auto")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Informazioni necessarie per la progettazione di flussi di processi aziendali con rami  
 Prendere nota delle informazioni seguenti quando si progetta il flusso del processo di business con i rami:  
  
-   Un processo può estendersi su un massimo di 5 entità univoche.  
  
-   È possibile utilizzare un massimo di 30 fasi per processo e un massimo di 30 passaggi per fase.  
  
-   Ogni ramo non può contenere più di 5 livelli di profondità.  
  
-   La regola di diramazione deve essere basata sui passaggi della fase che lo precede immediatamente.  
  
-   È possibile combinare più condizioni in una regola usando l'operatore `AND` o l'operatore di `OR`, ma non entrambi gli operatori.  
  
-   Quando si definisce un flusso di processo, è possibile selezionare facoltativamente una relazione tra entità. Questa relazione deve essere una relazione di entità 1: N (uno-a-molti).  
  
-   È possibile eseguire più di un processo attivo contemporaneamente nello stesso record di dati.  
  
-   È possibile ridisporre i riquadri (fasi, passaggi, condizioni e così via) nel flusso del processo tramite il trascinamento della selezione.  
  
-   Quando si uniscono i rami, tutti i rami peer devono essere Uniti in una sola fase. I rami peer devono essere tutti Uniti in una singola fase o ogni ramo peer deve terminare il processo. Un ramo peer non può eseguire il merge con altri rami e allo stesso tempo terminare il processo.  
  
> [!NOTE]
> - Un'entità usata nel processo può essere rivisitata più volte (più cicli di entità chiuse).  
> - Un processo può tornare alla fase precedente indipendentemente da un tipo di entità. Se, ad esempio, la fase attiva è **recapitata tra virgolette** in un record di virgolette, gli utenti del processo possono spostare la fase attiva di nuovo nella fase di **proproposta** su un record di opportunità.  
>   
>   In un altro esempio, si supponga che un processo sia **attualmente presente** nella fase proposta del flusso del processo: **qualifica lead** > **identificare le esigenze** > creare una **proposta** > **proposta presente** >  **Chiudi**. Se la proposta presentata al cliente richiede una maggiore ricerca per identificare le esigenze dei clienti, gli utenti possono semplicemente selezionare la fase di **identificazione delle esigenze** del processo e scegliere **Imposta attivo**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Esempio: flusso del processo di vendita auto con due rami
 
Esaminiamo l'esempio del flusso del processo di business con due rami, per la vendita di automobili nuove e di proprietà.  
  
 In primo luogo, verrà creato un nuovo processo denominato **Auto Sales process**.  
  
1.  [Aprire Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) , quindi nel riquadro di spostamento a sinistra selezionare **processi**.  
  
2.  Selezionare **nuovo** per creare un nuovo processo.  
  
3.  Specificare la **categoria** come **flusso del processo di business** e per l' **entità** primaria scegliere **Lead**.  
  
4.  Aggiungere la prima fase al processo denominato **qualificate** e aggiungere passaggi intervallo di **tempo di acquisto** e **preferenza dell'auto**.  
  
5.  Dopo la fase di **idoneità** comune, il processo viene suddiviso in due rami distinti, usando il riquadro **condizione** .  
  
    1.  Configurare il riquadro condizione con le regole che soddisfano i requisiti aziendali  
  
    2.  Per aggiungere il primo ramo per una fase, aggiungere un riquadro della fase nel percorso "Yes" del riquadro della condizione  
  
    3.  Per aggiungere il secondo ramo che viene eseguito quando la condizione non è soddisfatta, aggiungere un altro riquadro della fase nel percorso "No" del riquadro della condizione  
  
> [!TIP]
>  È possibile aggiungere un'altra condizione sul percorso "No" di un riquadro condizione esistente per creare rami più complessi.  
  
 ![Immagine che mostra la fase qualificata creata](media/example-car-sales-qualify-stage.JPG "Immagine che mostra la fase qualificata creata")  
  
 Se la **preferenza dell'auto** = **nuova**, il processo viene diramato alla nuova fase di **vendita dell'auto** , in caso contrario passa alla fase di vendita di **auto di proprietà** , nel secondo ramo, come illustrato di seguito.  
  
 ![Immagine che mostra la nuova fase di vendita auto](media/example-car-sales-new-stage-1.JPG "Immagine che mostra la nuova fase di vendita auto")  
  
 ![Fase&#45;di vendita auto di proprietà pre](media/example-car-sales-pre-owned-stage.JPG "Fase di vendita auto di proprietà preliminare")  
  
 Dopo aver completato tutti i passaggi della fase di **vendita del nuovo veicolo** o della fase di **vendita di auto di proprietà precedente** , il processo torna al flusso principale, con la fase di **offerta di consegna** .  
  
 ![Distribuisci fase preventivo](media/example-car-sales-deliver-quote-stage.JPG "Distribuisci fase preventivo")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Impedisci divulgazione di informazioni  
 Si consideri un flusso del processo di business con rami per l'elaborazione di una richiesta di prestito presso una banca, come illustrato di seguito. Le entità personalizzate utilizzate nelle fasi sono visualizzate tra parentesi.  
  
 ![Diagramma di flusso che illustra i passaggi in un processo di esempio per impedire la divulgazione di informazioni](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Diagramma di flusso che illustra i passaggi in un processo di esempio per impedire la divulgazione di informazioni")  
  
 In questo scenario, il responsabile del prestito bancario deve accedere al record di richiesta, ma il responsabile del prestito non deve avere visibilità sull'indagine della richiesta. A prima vista, sembra che sia possibile eseguire questa operazione assegnando al responsabile del prestito un ruolo di sicurezza che non specifica l'accesso all'entità di indagine. Tuttavia, esaminiamo l'esempio in modo più dettagliato e osserviamo se è vero.  
  
 Supponiamo che un cliente immetta la richiesta di prestito per oltre $60.000 alla banca. Il responsabile del prestito esamina la richiesta nella prima fase. Se la regola di diramazione che controlla se la quantità dovuta alla banca supera $50.000 è soddisfatta, la fase successiva del processo consiste nel verificare se la richiesta è fraudolenta. Se è determinato che questo è effettivamente un caso di illecito, il processo passa a un'azione legale per il richiedente. Il responsabile del prestito non deve avere visibilità sulle due fasi dell'indagine perché l'amministratore non ha accesso all'entità di indagine.  
  
 Tuttavia, se il responsabile del prestito apre il record di richiesta, tutti sarebbero in grado di visualizzare l'intero processo end-to-end. Non solo il responsabile del prestito sarà in grado di vedere la fase di indagine di frode, ma potrà anche identificare il risultato dell'indagine in quanto è stata in grado di vedere la fase di azione legale nel processo. Inoltre, l'ufficiale sarà in grado di visualizzare in anteprima i passaggi nelle fasi investigative scegliendo la fase. Anche se il responsabile del prestito non sarà in grado di visualizzare i dati o lo stato di completamento del passaggio, potrà identificare le azioni che sono state intraprese per il mittente della richiesta durante le fasi di analisi e azione legale.  
  
 In questo flusso di processo, il responsabile del prestito sarà in grado di vedere le fasi dell'indagine illecito e delle azioni legali, che costituiscono una divulgazione di informazioni non corretta. È consigliabile prestare particolare attenzione alle informazioni che possono essere divulgate a causa della diramazione. In questo esempio, suddividere il processo in due processi distinti, uno per l'elaborazione della richiesta e un altro per l'analisi di illecito, per impedire la divulgazione di informazioni. Il processo per il responsabile del prestito sarà simile al seguente:  
  
 ![Diagramma di flusso che mostra i passaggi aggiuntivi del processo per impedire la divulgazione di informazioni](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Diagramma di flusso che mostra i passaggi aggiuntivi del processo per impedire la divulgazione di informazioni")  
  
 Il processo per l'indagine sarà autonomo e includerà le fasi seguenti:  
  
 ![Diagramma di flusso che illustra i passaggi per un processo di indagine per i casi di divulgazione di informazioni](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Diagramma di flusso che illustra i passaggi per un processo di indagine per i casi di divulgazione di informazioni")  
  
 È necessario fornire un flusso di lavoro per sincronizzare la decisione approva/nega dal record di indagine al record della richiesta.  
  
### <a name="next-steps"></a>Passaggi successivi  
 [Creare un flusso del processo di business](create-business-process-flow.md)   
 [Creazione di una logica di business personalizzata con processi](guide-staff-through-common-tasks-processes.md)   
 
