---
title: Eseguire i flussi in base a una pianificazione | Microsoft Docs
description: Automatizzare le attività ricorrenti eseguendo i flussi in base a una pianificazione, ad esempio ogni giorno o ogni ora.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b737f416c927e7d7d8a7ea28ec81e268aa59b51d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548835"
---
# <a name="run-flows-on-a-schedule"></a>Eseguire i flussi in base a una pianificazione
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Creare un flusso che esegua una o più attività, ad esempio l'invio di un report tramite posta elettronica:

* una volta al giorno, un'ora o un minuto
* in una data specificata
* Dopo un numero di giorni, ore o minuti specificato

## <a name="create-a-recurring-flow"></a>Creare un flusso ricorrente
1. Accedere a [Microsoft Flow](https://flow.microsoft.com)e quindi selezionare **flussi personali** nella barra di spostamento superiore.
   
    ![Opzione flussi personali](./media/run-scheduled-tasks/create-flow.png)
2. Selezionare **Crea da zero**.
   
    ![Creare un flusso da zero](./media/run-scheduled-tasks/create-from-blank.png)
3. Nella casella **Cerca tutti i connettori e i trigger** Digitare **ricorrenza**, quindi selezionare **pianificazione-ricorrenza**.
   
    ![Trova trigger ricorrenza](./media/run-scheduled-tasks/select-recurrence.png)
4. Nella finestra di dialogo **ricorrenza** specificare la frequenza con cui si vuole eseguire il flusso.
   
    Se ad esempio si vuole che il flusso venga eseguito ogni due settimane, specificare **2** in **intervallo** e **settimana** in **frequenza** .
   
    ![Specifica ricorrenza](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Specificare le opzioni avanzate
1. Seguire i passaggi descritti nella sezione precedente e quindi selezionare **Mostra opzioni avanzate**.
   
    **Nota**: queste opzioni cambiano in base ai valori impostati per l' **intervallo** e la **frequenza** . Se la schermata non corrisponde al grafico seguente, verificare che l' **intervallo** e la **frequenza** siano impostati sugli stessi valori visualizzati nel grafico.
2. Selezionare un **fuso orario** per specificare se l' **ora di inizio** riflette il fuso orario locale, l'ora UTC (Universal Coordinated Time) e così via.
3. Specificare un' **ora di inizio** nel formato seguente:
   <br>AAAA-MM-GGTHH: MM: SSZ
4. Se è stato specificato il **giorno** in **frequenza**, specificare l'ora del giorno in cui deve essere eseguito il flusso.
5. Se è stata specificata la **settimana** in **frequenza**, specificare il giorno o i giorni della settimana in cui deve essere eseguito il flusso e l'ora o le ore del giorno in cui deve essere eseguito il flusso.
   
    Ad esempio, configurare le opzioni come illustrato per avviare un flusso non prima di mezzogiorno (fuso orario del Pacifico) il lunedì 1 gennaio 2018 ed eseguirlo ogni due settimane il martedì alle 5:30p (fuso orario del Pacifico).
   
    ![Specificare le opzioni avanzate](./media/run-scheduled-tasks/advanced-options.png)
6. Aggiungere l'azione o le azioni che si desidera venga eseguita dal flusso, come descritto in [creare un flusso da zero](get-started-logic-flow.md) .

## <a name="delay-a-flow"></a>Ritardare un flusso
1. Accedere a [Microsoft Flow](https://flow.microsoft.com)e quindi selezionare **flussi personali** nella barra di spostamento superiore.
   
    ![Creare un flusso da zero](./media/run-scheduled-tasks/create-flow.png)
2. Selezionare **Crea da zero**.
   
    ![Creare un flusso da zero](./media/run-scheduled-tasks/create-from-blank.png)
3. Specificare un evento come descritto in [creare un flusso da zero](get-started-logic-flow.md) .
4. Selezionare **nuovo passaggio**, quindi selezionare **Aggiungi un'azione**.
   
    ![Opzione per aggiungere un'azione a un flusso](./media/run-scheduled-tasks/add-action.png)
5. Nell'elenco delle azioni eseguire una delle operazioni seguenti:
   
   * Selezionare **ritardo**, specificare un **conteggio**e specificare un' **unità** di tempo, ad esempio secondo, minuto o ora.
   * Selezionare **ritardo fino a**, quindi specificare una data in questo formato.<br>AAAA-MM-GGTHH: MM: SSZ
     
     ![aggiungere un ritardo](./media/run-scheduled-tasks/add-delay.png)
     ![specificare un ritardo in unità di tempo](./media/run-scheduled-tasks/delay.png)
     ![specificare un ritardo fino a](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Ulteriori informazioni

Altre informazioni sulle [Opzioni avanzate](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) e su come configurarle.

