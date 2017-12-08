---
title: Creare un flusso da un modello | Microsoft Docs
description: Informazioni su come creare e gestire un flusso basato su un modello.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: D46qE7FuShM
courseduration: 9m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/15/2017
ms.author: deonhe
ms.openlocfilehash: a6ef80f4d20b88ef3b3a5193048209f924c9860a
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-from-a-template"></a>Creare un flusso da un modello
Bentornato nella Formazione interattiva su Microsoft Flow. In questa lezione, si scopriranno altre informazioni sull'ambiente di Microsoft Flow e si potrà **compilare il primo flusso**.

Iniziare a usare Microsoft Flow è facile, perché ci sono tantissimi **modelli tra cui scegliere**, che aiuteranno a connettere i servizi che si usano già in maniera più significativa.  

## <a name="microsoft-flow-templates"></a>Modelli di Microsoft Flow
Esaminare il [sito Web di Microsoft Flow](https://ms.flow.microsoft.com) e aprire il menu **Modelli**. Scorrendo l'elenco, si osserverà che Microsoft Flow permette di connettersi a molti servizi.

![Sito Web di Flow -> Elenco Modelli](./media/learning-create-a-flow/template-list.png)

## <a name="choose-a-template"></a>Scegliere un modello
La **ricerca degli allegati** nella posta elettronica può essere un'attività onerosa e questo flusso consente di risparmiare tempo **archiviando tutti gli allegati di posta elettronica** in una cartella su OneDrive.

Selezionare il modello **Salva i nuovi allegati di posta elettronica di Office 365 in OneDrive for Business**.

![Posta elettronica di Office 365](./media/learning-create-a-flow/office-365-email.png)

## <a name="create-and-administer-a-flow"></a>Creare e amministrare un flusso
Questo è uno dei modelli con **un singolo clic**, in cui si risponde solo alle domande pertinenti, **necessarie per creare il flusso**.

Nella grafica del modello, c'è una **descrizione** delle operazioni **eseguite o necessarie** per la buona riuscita del modello.

Viene richiesto di **fornire le credenziali** per i servizi **Office 365 Outlook** e **SharePoint**. Se si usano regolarmente entrambi i servizi, si è già connessi.

![Salvare la posta elettronica di Office 365](./media/learning-create-a-flow/save-flow-office-description.png)

1. Selezionare **Crea flusso**.
   
    ![Fare clic su Crea flusso](./media/learning-create-a-flow/click-create-flow.png)
   
    Verranno quindi visualizzati i risultati. 
   
    ![Creazione riuscita](./media/learning-create-a-flow/create-successful.png)
   
    Flow ha **creato una cartella** in OneDrive, in cui ora verrà automaticamente inserito **ogni allegato** che si riceve via posta elettronica al lavoro.
2. Aprire **Flussi personali**.
   
    ![Aprire Flussi personali](./media/learning-create-a-flow/click-my-flows.png)
3. Selezionare il **flusso appena creato** per verificarne il funzionamento.
   
    ![Selezionare il flusso](./media/learning-create-a-flow/click-the-flow.png)
4. Viene visualizzato un **segno di spunta verde**, a indicare che il **flusso ha avuto esito positivo**. Selezionare **Completato** per visualizzare la cronologia di esecuzione e i risultati.
   
    ![Flusso completato](./media/learning-create-a-flow/flow-successful.png)
   
    **Tutte le parti del flusso di** hanno avuto esito positivo. 
   
    ![Cronologia di esecuzione](./media/learning-create-a-flow/run-history.png)

## <a name="important-concepts-in-microsoft-flow"></a>Concetti importanti in Microsoft Flow
Alcuni aspetti da considerare durante la compilazione di flussi. Ogni flusso è costituito da due parti principali: un **trigger** e **una o più azioni**. 

È possibile considerare il **trigger** come l'azione che avvia il flusso, ad esempio **All'arrivo di nuovo messaggio di posta elettronica** oppure **Quando viene aggiunto un nuovo elemento**, se si stava usando SharePoint. Può anche trattarsi di una pianificazione fissa, se si usa un trigger denominato **Ricorrenza**, che verrà illustrato più avanti.

**Le azioni sono le attività** che devono essere eseguite quando **viene richiamato un trigger**. Ad esempio, **Crea file** ricrea il file in OneDrive.

![Azioni all'arrivo di nuovo messaggio di posta elettronica](./media/learning-create-a-flow/trigger-or-action.png)

Altre azioni potrebbero essere l'invio di un'**e-mail**, la pubblicazione di un **tweet**, l'avvio di un'**approvazione** o molte altre ancora.
Queste azioni entreranno in gioco in un secondo momento, durante la compilazione dei flussi personalizzati da zero. 

## <a name="next-lesson"></a>Lezione successiva
Nella lezione successiva, si parlerà dell'app Microsoft Flow per dispositivi mobili e delle relative funzionalità. 
