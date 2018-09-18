---
title: Gestire i flussi dal telefono | Microsoft Docs
description: Visualizzare un elenco dei flussi, abilitarli o disabilitarli e visualizzare eventi, azioni e cronologia di esecuzione di ogni flusso
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4a35166ec57e81b957f7659e0e670e80bbf510ca
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689549"
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>Gestire i flussi dal telefono in Microsoft Flow dal telefono
Visualizzare un elenco di tutti i flussi che sono stati creati e, per ogni flusso, visualizzare i relativi eventi e le azioni, abilitarlo o disabilitarlo ed esaminare la cronologia di esecuzione.

**Prerequisiti**

* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows) in un [dispositivo supportato](getting-started.md#use-the-mobile-app). Le immagini in questo argomento riflettono la versione dell'app per iPhone, ma sono simili a quelle per Android e Windows Phone.
* Se non si ha già un flusso, crearne uno nel [sito Web per Microsoft Flow](https://flow.microsoft.com/). Per semplificare il test, usarne uno che sia possibile attivare manualmente anziché attendere un evento esterno.

Il flusso in questa esercitazione viene eseguito quando si riceve posta da un indirizzo specifico:

![Attivare il flusso alla ricezione di posta dall'indirizzo specifico](./media/mobile-manage-flows/create-trigger.png)

È possibile configurare un flusso di questo tipo con l'indirizzo di posta elettronica personale per il test e un indirizzo diverso (ad esempio, quello del responsabile) quando il flusso è pronto per l'uso reale.

Quando viene eseguito il flusso, invia una notifica push personalizzata, con questa sintassi, al telefono:

![Inviare messaggi a Slack](./media/mobile-manage-flows/create-event.png)

**Nota:** è anche possibile [monitorare l'attività di flusso](mobile-monitor-activity.md) dall'app per dispositivi mobili.

## <a name="manage-a-flow"></a>Gestire un flusso
1. Aprire l'app per dispositivi mobili e quindi toccare **Flussi personali** nella parte inferiore della schermata per elencare tutti i flussi.
   
    Ogni voce indica il nome del flusso, le icone per i relativi eventi e azioni, la data/ora dell'ultima esecuzione e un'icona che indica se l'ultima esecuzione è stata completata.
   
    ![Elenco di flussi](./media/mobile-manage-flows/flow-list.png)
2. Toccare un flusso per visualizzare le opzioni per la sua gestione.
   
    ![Opzioni per gestire un flusso](./media/mobile-manage-flows/flow-details.png)
3. Toccare **Abilita flusso** per abilitare o disabilitare il flusso.
4. Toccare **Vedi flusso** per mostrare gli eventi e le azioni relativi a tale flusso, toccare ogni evento o azione per espanderli e quindi toccare **Indietro**.
   
    ![Eventi e azioni per un flusso](./media/mobile-manage-flows/flow-event-action.png)
5. Toccare **Cronologia esecuzioni** per mostrare operazioni riuscite, errori o entrambi per il flusso.
   
    ![Elenco di esecuzioni](./media/mobile-manage-flows/history-mixed.png)
6. Toccare un'esecuzione per mostrare se ogni evento e azione sono riusciti e, in tal caso, quanto tempo (in secondi) è stato impiegato.
   
    ![Dettagli dell'esecuzione](./media/mobile-manage-flows/flow-run.png)

