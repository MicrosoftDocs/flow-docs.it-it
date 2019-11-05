---
title: Monitorare l'attività dal telefono | Microsoft Docs
description: Visualizzare il numero di volte in cui ogni flusso ha avuto esito positivo o negativo, quando si è verificata ogni esecuzione e il tempo impiegato
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
ms.openlocfilehash: 9696ff09f41822b9daeb84b748f32e1babaf5af1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549014"
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>Monitorare l'attività in Microsoft Flow dal telefono
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Visualizzare un riepilogo del numero di volte in cui ogni flusso ha avuto esito positivo o negativo oggi, ieri e giorni precedenti. Esaminare i dettagli di ogni esecuzione, ad esempio quando è stata eseguita, il tempo impiegato per ogni passaggio e, in caso di errore, perché.

**Prerequisiti**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows) su un [dispositivo supportato](getting-started.md#use-the-mobile-app). Le immagini in questo argomento riflettono la versione dell'app per iPhone, ma la grafica in Android e Windows Phone sono simili.
* Se non si dispone già di un flusso, crearne uno nel [sito Web per Microsoft Flow](https://flow.microsoft.com/). Per un test più semplice, è possibile utilizzarne uno che si può attivare autonomamente anziché attendere un evento esterno.

Il flusso in questa esercitazione viene eseguito quando si riceve posta da un indirizzo specifico:

![Attivare il flusso alla ricezione della posta da un indirizzo specifico](./media/mobile-monitor-activity/create-trigger.png)

È possibile configurare un flusso di questo tipo con l'indirizzo di posta elettronica personale per il test e un indirizzo diverso (ad esempio, il Manager) quando il flusso è pronto per l'uso reale.

Quando il flusso viene eseguito, invia una notifica push personalizzata, con questa sintassi, al telefono:

![Invia notifica push](./media/mobile-monitor-activity/create-event.png)

**Nota:** È anche possibile [gestire i flussi](mobile-manage-flows.md) dall'app per dispositivi mobili.

## <a name="display-a-summary-of-activity"></a>Visualizza un riepilogo delle attività
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Se il flusso non è stato eseguito in precedenza, attivare un'esecuzione per generare i dati.
   
    La visualizzazione dei dati nell'app potrebbe richiedere del tempo.
2. Aprire l'app per dispositivi mobili, che mostra la scheda **attività** per impostazione predefinita.
   
    Questa scheda consente di organizzare i dati in base al giorno, con i dati odierni nella parte superiore.
   
    ![Attività organizzata per giorno](./media/mobile-monitor-activity/activity-day2.png)
   
    Ogni voce indica il nome di un flusso con icone che corrispondono agli eventi e alle azioni del trigger.
   
    ![Nome e icone per ogni flusso](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Se almeno un'esecuzione di un flusso ha avuto esito positivo in un giorno, una voce indica il numero di successi e l'ora in cui è stato completato più di recente. Una voce diversa Mostra informazioni simili se un flusso non è riuscito.
   
    ![Riepilogo delle operazioni riuscite o degli errori](./media/mobile-monitor-activity/activity-summary.png)
   
    Se un flusso invia una notifica push, il testo della notifica più recente viene visualizzato nella parte inferiore della voce per le esecuzioni riuscite.
   
    ![Esempio di notifica push](./media/mobile-monitor-activity/activity-notification.png)
3. Se sono state inviate più notifiche push in un giorno, scorrere rapidamente verso sinistra nella notifica per visualizzare le notifiche da un massimo di tre esecuzioni precedenti. Se sono state inviate più di quattro notifiche in un giorno, scorrere rapidamente verso sinistra fino a quando non viene visualizzato **altro** , quindi toccarlo per visualizzare un elenco di tutte le notifiche.
   
    ![Esempio di notifica push](./media/mobile-monitor-activity/activity-notification-list.png)
4. Toccare **indietro** per tornare al riepilogo delle attività.
5. Per filtrare il riepilogo delle attività, toccare l'icona nell'angolo in alto a destra.
   
    È possibile visualizzare tutte le voci, solo le voci di errore o solo le voci che includono le notifiche push.
   
    ![Mostra tutte le esecuzioni, solo gli errori o solo le notifiche](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Mostra i dettagli di un'esecuzione
1. Nel riepilogo attività, toccare una voce per visualizzare i dettagli per l'esecuzione più recente.
   
     Ogni evento e azione viene visualizzato con un'icona che indica se l'evento o l'azione ha avuto esito positivo o negativo. In caso di esito positivo, viene visualizzata anche la quantità di tempo impiegato (in secondi).
   
    ![Dettagli di un'esecuzione](./media/mobile-monitor-activity/activity-icons.png)
2. Nella parte inferiore della schermata toccare **Vedi esecuzioni precedenti** per elencare tutte le esecuzioni del flusso, quindi toccare un'esecuzione per visualizzarne i dettagli.
   
    ![Cronologia di esito positivo/negativo](./media/mobile-monitor-activity/history-mixed.png)

