---
title: Procedure consigliate per l'uso di attributi di entità del flusso di processo business | Documentazione Microsoft
description: Procedure consigliate per l'uso di attributi di entità di business processo del flusso.
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: 950f03d78e708f00f28b68daf7c1012fae231c95
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64472973"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Le procedure consigliate con gli attributi del flusso di processo di business


Gli attributi correlati al processo legacy nelle entità è deprecata. Ecco alcune procedure consigliate per l'uso di *fase attiva* (activestageid) attributo nell'entità del flusso di processo di business. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Creazione di report per la fase attiva di un flusso di processo di business

Si supponga che si desidera ottenere una visualizzazione della pipeline di vendita di creazione di report attiva fase che il **causare processo opportunità di vendita** si trova in.

Per indicare i processi di business dalla fase, uno in precedenza, potrebbe essere definito una vista in ogni entità correlata del flusso del processo di business e quindi segnalare i *fase attiva* campo (activestageid).

Con la deprecazione del *fase attiva* campo (activestageid) in entità correlate, esistono due modi per eseguire segnalazioni su flussi di processi aziendali.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Opzione 1: Le visualizzazioni e grafici, in business elaborano entità flusso **(scelta consigliata)**

Nelle versioni 9.0 e versioni successive, ogni flusso di processo di business crea la propria entità di Common Data Service, in genere con lo stesso nome di flusso del processo di business. Per indicare il flusso del processo di business, selezionare l'entità per il flusso del processo di business che si desidera includere nel report e quindi creare le visualizzazioni e grafici, proprio come in precedenza.

In questo esempio, seguire questa procedura per passare al **Lead a opportunità di vendita processo** entità:
1. Passare a https://web.powerapps.com.
1. Selezionare il **dati**.
1. Selezionare il **Entities**.
1. Impostare il filtro **tutti**.
1. Cercare e quindi selezionare il **Lead a opportunità di vendita processo** entità.

   ![portare a entità di processo di vendita opportunità](media/best-practices-entity-attributes/lead-opportunity-process.png)

In questo caso, è possibile definire le visualizzazioni e grafici, come avviene in un'altra entità.

![dettagli di entità traduzione processo](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Un vantaggio di questo approccio è che è possibile usare una singola visualizzazione o un grafico al report in flussi di processi aziendali che si estendono su più entità.

Inoltre, poiché l'entità di flusso di processo di business non è diverso da un'altra entità personalizzata in Common Data Service, è possibile aggiungere campi personalizzati all'entità per tenere traccia di eventuali informazioni aggiuntive che necessarie.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Opzione 2: copiare fase attiva a un'entità correlata

In alternativa, per continuare a creare report disattivato l'entità correlata, creare un flusso per copiare il *fase attiva* (activestageid) campo dell'entità di flow processo di business in un campo personalizzato per le entità di Common Data Service correlati.

Ecco alcuni aspetti da tenere presenti quando si usa questo approccio:

1.  È possibile avere più di un flusso di processo di business in esecuzione in una singola entità. Con questo approccio, è consigliabile disporre di un campo personalizzato che memorizza la fase attiva per ogni flusso di processo di business che viene eseguito nell'entità. Questo approccio garantisce l'integrità del report.

1.  Come creazione di report è determinato dall'entità correlata, non è possibile creare una singola visualizzazione che un report sui flussi di processi aziendali che si estendono su più entità.

## <a name="using-the-active-stage-to-run-logic"></a>Con la fase attiva per l'esecuzione per la logica

Ecco alcuni casi in cui è possibile eseguire per l'esecuzione per la logica che si basa sulla fase attiva:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Con la fase attiva per eseguire una logica lato client

Come si usa il processo di business, esistono molti aspetti che è possibile eseguire automaticamente. Ad esempio:

-   Modificare il flusso del processo di business attive basato sulle informazioni disponibili appena il flusso del processo di business o form.

-   Spostare la fase attiva alla fase successiva o precedente, in base ai valori immessi gli utenti per passaggi o i campi del modulo.

-   Nascondere o mostrare tabulazioni form e i campi in base la fase selezionata.

-   Mostra messaggi informativi ed eseguire calulations basata i flussi del processo di business attiva, la fase attivo o selezionato o eventi, ad esempio spostando la fase attiva.

> [!TIP]
> Per questi scenari, usare il set supportato dei [API client](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) per flussi di processi aziendali.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Con la fase attiva per eseguire la logica lato server

Potrebbero esserci casi in cui automazione in base alle esigenze del flusso processo aziendale deve essere eseguita sul lato server. Ad esempio:

-   Inviare un messaggio di posta elettronica a un utente se il **qualifica** la fase delle **opportunità di vendita processo** è attiva per più di 15 giorni.

-   Creare automaticamente un set di attività rilevanti per la fase attiva del **opportunità di vendita processo** ogni volta che viene modificato.

-   Completare automaticamente il **opportunità di vendita processo** quando viene completata l'attività di chiamata telefonica di chiusura.

> [!TIP]
> Usare i flussi di lavoro di Common Data Service classici o flussi che è definire per l'entità per il flusso del processo di business.
> 

Per compilare un flusso di lavoro di Common Data Service di classico che consente di creare attività per soluzione interna esamina e procedere con il cliente nel **Proponi** fase della **opportunità di vendita processo**:

1. Creare il certificato nel **processo vendite delle opportunità** entità e impostarla perché venga eseguita ogni volta che il **fase attiva** campo le modifiche all'entità. 
1. Definire una condizione per controllare se il **fase attiva** campo equals **Proponi**. 
1. Creare un record di appuntamento e telefonata per la revisione interno della soluzione e la chiamata dei clienti a esaminare la soluzione rispettivamente.

   ![Chiudere il completamento di fase](media/best-practices-entity-attributes/close-stage-followup.png)
