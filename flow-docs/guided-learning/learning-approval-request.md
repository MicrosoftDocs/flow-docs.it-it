---
title: Elaborare una richiesta di approvazione | Microsoft Docs
description: Informazioni su come approvare o rifiutare una richiesta di approvazione.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: -0r5ZKVEIS4
courseduration: 7m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 6ba7a2cf0fae481457f965627ebf523f063af50d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="process-an-approval-request"></a>Elaborare una richiesta di approvazione
In un argomento precedente, è stato illustrato come creare un processo di approvazione intorno ai tweet archiviati in un elenco SharePoint.  In questo argomento successivo, si vedrà cosa succede quando un responsabile approvazione riceve una nuova richiesta di approvazione. 

## <a name="create-and-process-a-request"></a>Creare ed elaborare una richiesta
Prima di tutto è necessario aggiungere un elemento all'elenco di SharePoint, quindi è possibile elaborare una richiesta di approvazione per quell'elemento.

1. Aprire l'elenco di SharePoint **TweetDiContoso**, che è stato configurato in un argomento precedente.  Selezionare **Nuovo** per creare un nuovo tweet. 
   
    ![Elenco di SharePoint](./media/learning-approval-request/sharepoint-list-home.png)
2. Aggiungere i seguenti valori ai campi e selezionare **Salva**.
   
   * **Titolo** – Promozioni
   * **ContenutoTweet**: Date un'occhiata alla nuova linea di Contoso Flooring #ohsocontoso
   * **DataTweet**: la data di oggi
     
     ![Nuovo elemento di SharePoint](./media/learning-approval-request/sharepoint-new-tweet.png)
3. In **Microsoft Flow**, selezionare **Flussi personali**. 
4. Selezionare il flusso **Pubblica gli elementi elenco in Twitter dopo l'approvazione** che è stato configurato nell'argomento precedente, quindi selezionare il flusso in esecuzione nella sezione **CRONOLOGIA DI ESECUZIONE**.
   
    ![Cronologia di esecuzione](./media/learning-approval-request/run-history.png)
5. Selezionare il trigger **Quando viene creato un nuovo elemento**. Verificare che le informazioni per l'elemento di elenco appena creato siano visualizzate.
   
    ![Trigger di flusso](./media/learning-approval-request/approval-flow.png)
6. In **Outlook**, aprire il messaggio di approvazione automatica nella posta in arrivo e quindi selezionare **Approva**. 
   
    ![Richiesta di Outlook](./media/learning-approval-request/outlook-mail.png)
7. Nel **Centro approvazioni**, visualizzare i dettagli della richiesta, aggiungere un commento e selezionare **Conferma**. 
   
    ![Centro approvazioni](./media/learning-approval-request/approval-center.png)
8. In **SharePoint**, aggiornare l'elenco **TweetDiContoso** e verificare che **StatoApprovazione** sia **Sì**e che il commento immesso sia visualizzato. 
   
    ![Aggiornare elenco di SharePoint](./media/learning-approval-request/sharepoint-list-approved.png)

In questo argomento si è analizzata l'esperienza dal punto di vista del responsabile approvazione, dalla ricezione di un messaggio di richiesta di approvazione all'elaborazione della richiesta nel Centro approvazioni.

