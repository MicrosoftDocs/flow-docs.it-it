---
title: Eseguire i flussi in base a una pianificazione | Microsoft Docs
description: "Automatizzare le attività ricorrenti eseguendo flussi in una pianificazione, ad esempio ogni ora oppure ogni giorno."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: stepsic
ms.openlocfilehash: eaeaf62da694daf7f8e6d876c3d225337fdbe592
ms.sourcegitcommit: 01325305b9d2cf964acac9feb6cca0af66db7440
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2017
---
# <a name="run-flows-on-a-schedule"></a>Eseguire i flussi in una pianificazione
Creare un flusso che esegue una o più attività, ad esempio l'invio di un report tramite posta elettronica:

* Una volta al giorno, all'ora o al minuto
* In corrispondenza di una data specificata
* Dopo il numero di giorni, ore o minuti specificato

## <a name="create-a-recurring-flow"></a>Creare un flusso ricorrente
1. Accedere a [Microsoft Flow](https://flow.microsoft.com), quindi selezionare **Flussi personali** nella barra di spostamento in alto.
   
    ![Opzione Flussi personali](./media/run-scheduled-tasks/create-flow.png)
2. Selezionare **Crea da zero**.
   
    ![Creare un flusso da zero](./media/run-scheduled-tasks/create-from-blank.png)
3. Nella casella **Cerca tutti i connettori e i trigger** digitare **Ricorrenza**, quindi selezionare **Pianificazione - Ricorrenza**.
   
    ![Trigger per l'individuazione della ricorrenza](./media/run-scheduled-tasks/select-recurrence.png)
4. Nella finestra di dialogo **Ricorrenza** specificare la frequenza con cui si vuole eseguire il flusso.
   
    Specificare ad esempio **2** in **Intervallo** e **Settimana** in **Frequenza**, se si vuole che il flusso venga eseguito ogni due settimane.
   
    ![Specificare la ricorrenza](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Specificare le opzioni avanzate
1. Seguire la procedura illustrata nella sezione precedente, quindi selezionare **Mostra le opzioni avanzate**.
   
    **Nota**: queste opzioni dipendono dai valori specificati per **Intervallo** e **Frequenza**. Se la schermata non corrisponde al grafico seguente, assicurarsi che **Intervallo** e **Frequenza** siano impostati sugli stessi valori mostrati nel grafico.
2. Selezionare un **Fuso orario** per specificare se **Ora di inizio** rispecchia l'ora locale, l'ora UTC (Universal Coordinated Time) e così via.
3. Specificare un'**Ora di inizio** con il formato seguente:
   <br>AAAA-MM-GG:MM:SSZ
4. Se è stata specificata l'opzione **Giorno** in **Frequenza**, specificare l'ora del giorno in cui deve essere eseguito il flusso.
5. Se è stata specificata l'opzione **Settimana** in **Frequenza**, specificare il giorno o i giorni della settimana in cui deve essere eseguito il flusso e l'ora o le ore del giorno in cui deve essere eseguito il flusso.
   
    Configurare, ad esempio, le opzioni come indicato per avviare un flusso non prima di mezzogiorno (fuso costa pacifica) nel giorno lunedì 1 gennaio 2018 ed eseguirlo ogni due settimane alle ore 17:30 (fuso costa pacifica) al martedì.
   
    ![Specificare le opzioni avanzate](./media/run-scheduled-tasks/advanced-options.png)
6. Aggiungere l'azione o le azioni che il flusso dovrà eseguire, come descritto in [Creare un flusso da zero](get-started-logic-flow.md).

## <a name="delay-a-flow"></a>Ritardare un flusso
1. Accedere a [Microsoft Flow](https://flow.microsoft.com), quindi selezionare **Flussi personali** nella barra di spostamento in alto.
   
    ![Creare un flusso da zero](./media/run-scheduled-tasks/create-flow.png)
2. Selezionare **Crea da zero**.
   
    ![Creare un flusso da zero](./media/run-scheduled-tasks/create-from-blank.png)
3. Specificare un evento come descritto in [Creare un flusso da zero](get-started-logic-flow.md).
4. Selezionare **Nuovo passaggio**, quindi scegliere **Aggiungi un'azione**.
   
    ![Opzione per aggiungere un'azione a un flusso](./media/run-scheduled-tasks/add-action.png)
5. Nell'elenco delle azioni, effettuare una delle operazioni seguenti:
   
   * Selezionare **Ritardo**, specificare un **Conteggio**, quindi selezionare un'**Unità** di tempo, ad esempio secondo, minuto oppure ora.
   * Selezionare **Ritarda fino a**, quindi specificare una data nel formato seguente.<br>AAAA-MM-GG:MM:SSZ
     
     ![Aggiungere un ritardo](./media/run-scheduled-tasks/add-delay.png)
     ![Specificare il ritardo in unità di tempo](./media/run-scheduled-tasks/delay.png)
     ![Specificare la data di fine del ritardo](./media/run-scheduled-tasks/delay-until.png)

