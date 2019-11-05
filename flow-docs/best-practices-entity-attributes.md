---
title: Procedure consigliate per l'utilizzo degli attributi dell'entità flusso del processo di business | MicrosoftDocs
description: Informazioni sulle procedure consigliate per l'utilizzo degli attributi dell'entità flusso del processo di business.
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
ms.openlocfilehash: b46eac7317db8f5b63ebcd7b8b1fe8c79109bc11
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545295"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Procedure consigliate per l'utilizzo degli attributi di flusso del processo di business
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]


Gli attributi legacy correlati ai processi nelle entità sono deprecati. Di seguito sono riportate alcune procedure consigliate per l'utilizzo dell'attributo della *fase attiva* (activestageid) nell'entità del flusso del processo di business. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Creazione di report sulla fase attiva di un flusso del processo di business

Supponiamo che si desideri ottenere una visualizzazione della pipeline di vendita segnalando la fase attiva in cui si trova il **lead to Opportunity Sales process** .

In precedenza, per creare report sui processi di business per fase, è possibile definire una vista in ogni entità correlata del flusso del processo di business e quindi creare un report nel campo *fase attiva* (activestageid).

Con la deprecazione del campo *attivo della fase* (activestageid) sulle entità correlate, esistono due modi per creare report sui flussi del processo di business.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Opzione 1: visualizzazioni e grafici sull'entità del flusso del processo di business **(scelta consigliata)**

Nelle versioni 9,0 e successive ogni flusso del processo di business crea il proprio Common Data Service entità, in genere con lo stesso nome del flusso del processo di business. Per creare un report sul flusso del processo di business, selezionare l'entità per il flusso del processo di business in cui si desidera creare un report, quindi creare visualizzazioni e grafici come in precedenza.

In questo esempio, seguire questa procedura per passare all'entità **lead to Opportunity Sales process** :
1. Passare a https://web.powerapps.com.
1. Selezionare i **dati**.
1. Selezionare le **entità**.
1. Impostare il filtro su **tutti**.
1. Cercare e quindi selezionare l'entità **lead to Opportunity Sales process** .

   ![responsabile dell'entità del processo di vendita delle opportunità](media/best-practices-entity-attributes/lead-opportunity-process.png)

Qui è possibile definire visualizzazioni e grafici come per qualsiasi altra entità.

![dettagli dell'entità del processo di traduzione](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Un vantaggio di questo approccio consiste nel fatto che è possibile utilizzare una singola vista o un grafico per creare report sui flussi del processo di business che si estendono su più entità.

Poiché l'entità del flusso del processo di business non è diversa da qualsiasi altra entità personalizzata in Common Data Service, è possibile aggiungere campi personalizzati all'entità per tenere traccia di eventuali informazioni aggiuntive necessarie.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Opzione 2: copiare la fase attiva in un'entità correlata

In alternativa, per continuare a segnalare l'entità correlata, creare un flusso per copiare il campo *fase attiva* (activestageid) dall'entità del flusso del processo di business in un campo personalizzato delle entità Common Data Service correlate.

Ecco alcuni aspetti da tenere presenti quando si usa questo approccio:

1.  È possibile che più di un flusso di processo di business sia in esecuzione in una singola entità. Con questo approccio, è preferibile avere un campo personalizzato che archivia la fase attiva per ogni flusso del processo di business eseguito nell'entità. Questo approccio garantisce l'integrità della creazione di report.

1.  Poiché la creazione di report viene determinata dall'entità correlata, non è possibile creare una singola vista che segnali i flussi del processo di business che si estendono su più entità.

## <a name="using-the-active-stage-to-run-logic"></a>Uso della fase attiva per eseguire la logica

Di seguito sono riportati alcuni casi in cui potrebbe essere necessario eseguire la logica basata sulla fase attiva:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Uso della fase attiva per eseguire la logica lato client

Quando si usa il processo di business, è possibile che si desideri eseguire automaticamente alcune operazioni. Ad esempio:

-   Modificare il flusso del processo aziendale attivo in base alle informazioni appena disponibili sul form o sul flusso del processo di business.

-   Spostare la fase attiva nella fase successiva o precedente, in base ai valori immessi dagli utenti per i passaggi o i campi del modulo.

-   Nascondere o visualizzare le schede e i campi del modulo in base alla fase selezionata.

-   Visualizzare i messaggi informativi ed eseguire calulations in base ai flussi del processo aziendale attivo, alla fase attiva o selezionata o a eventi come lo scorrimento della fase attiva.

> [!TIP]
> Per gli scenari di questo tipo, usare il set di [API client](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) supportato per i flussi del processo di business.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Uso della fase attiva per eseguire la logica sul lato server

Potrebbero esserci casi in cui l'automazione basata sul flusso del processo di business deve essere eseguita sul lato server. Ad esempio:

-   Invia un messaggio di posta elettronica a un utente se la fase **qualificata** del **processo Sales opportunity** è attiva per più di 15 giorni.

-   Creare automaticamente un set di attività rilevanti per la fase attiva del **processo di Sales opportunity** ogni volta che viene modificato.

-   Termina automaticamente il **processo Sales opportunity** quando viene completata l'attività telefonata per la chiusura.

> [!TIP]
> Usare i flussi o flussi di lavoro di Common Data Service classici definiti nell'entità per il flusso del processo di business.
> 

Per creare un flusso di lavoro di Common Data Service classico che crea attività per le revisioni della soluzione interna e per completare il cliente nella fase **proposta** del **processo di vendita opportunità**:

1. Crearla nell'entità **processo Sales Opportunities** e impostarla in modo che venga eseguita ogni volta che viene modificato il campo della **fase attiva** dell'entità. 
1. Definire una condizione per verificare se il campo della **fase attiva** è uguale a **Proponi**. 
1. Creare un appuntamento e un record telefonata per la revisione interna della soluzione e la chiamata del cliente per esaminare la soluzione rispettivamente.

   ![completamento della fase di chiusura](media/best-practices-entity-attributes/close-stage-followup.png)
