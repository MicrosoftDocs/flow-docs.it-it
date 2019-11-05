---
title: Gestire i flussi dal telefono | Microsoft Docs
description: Visualizzare un elenco dei flussi, abilitarli o disabilitarli e visualizzare gli eventi, le azioni e la cronologia di esecuzione di ogni flusso
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
ms.openlocfilehash: 6f452f52d654d6f03a3262de8888c68cb2480704
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548626"
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>Gestire i flussi in Microsoft Flow dal telefono
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Visualizzare un elenco di tutti i flussi creati e, per ogni flusso, visualizzarne gli eventi e le azioni, abilitarli o disabilitarli ed esplorarne la cronologia di esecuzione.

**Prerequisiti**

* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows) su un [dispositivo supportato](getting-started.md#use-the-mobile-app). Le immagini in questo argomento riflettono la versione dell'app per iPhone, ma la grafica in Android e Windows Phone aspetto simile.
* Se non si dispone già di un flusso, crearne uno nel [sito Web per Microsoft Flow](https://flow.microsoft.com/). Per un test più semplice, è possibile utilizzarne uno che si può attivare autonomamente anziché attendere un evento esterno.

Il flusso in questa esercitazione viene eseguito quando si riceve posta da un indirizzo specifico:

![Attivare il flusso alla ricezione della posta da un indirizzo specifico](./media/mobile-manage-flows/create-trigger.png)

È possibile configurare un flusso di questo tipo con l'indirizzo di posta elettronica personale per il test e un indirizzo diverso (ad esempio, il Manager) quando il flusso è pronto per l'uso reale.

Quando il flusso viene eseguito, invia una notifica push personalizzata, con questa sintassi, al telefono:

![Invia messaggio a slack](./media/mobile-manage-flows/create-event.png)

**Nota**: è anche possibile [monitorare l'attività del flusso](mobile-monitor-activity.md) dall'app per dispositivi mobili.

## <a name="manage-a-flow"></a>Gestire un flusso
1. Aprire l'app per dispositivi mobili e quindi toccare **flussi personali** nella parte inferiore della schermata per elencare tutti i flussi.
   
    Ogni voce Mostra il nome del flusso, le icone per gli eventi e le azioni, l'ora in cui è stata eseguita più di recente e un'icona che indica se l'esecuzione più recente è riuscita.
   
    ![Elenco dei flussi](./media/mobile-manage-flows/flow-list.png)
2. Toccare un flusso per visualizzare le opzioni per la relativa gestione.
   
    ![Opzioni per la gestione di un flusso](./media/mobile-manage-flows/flow-details.png)
3. Toccare l'interruttore **Abilita flusso** per abilitare o disabilitare il flusso.
4. Toccare **See Flow** per visualizzare gli eventi e le azioni per quel flusso, toccare ogni evento o un'azione per espanderlo, quindi toccare **indietro**.
   
    ![Eventi e azioni per un flusso](./media/mobile-manage-flows/flow-event-action.png)
5. Toccare **cronologia di esecuzione** per visualizzare i successi, gli errori o entrambi i flussi.
   
    ![Elenco di esecuzioni](./media/mobile-manage-flows/history-mixed.png)
6. Toccare un'esecuzione per mostrare se ogni evento e azione ha avuto esito positivo e, in caso affermativo, il tempo richiesto (in secondi).
   
    ![Dettagli esecuzione](./media/mobile-manage-flows/flow-run.png)

