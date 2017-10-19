---
title: Pubblicare tweet da un flusso | Microsoft Docs
description: Informazioni su come pubblicare tweet basati sui dati in un elenco di SharePoint.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: y1iDal8XPAo
courseduration: 15m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 4015377204edfde289cf04835b2660288d0690e1
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="post-tweets-from-a-flow"></a>Pubblicare tweet da un flusso
Per questo flusso, sarà necessario creare un elenco di **SharePoint** in cui il team di marketing di **Contoso Flooring** archivia i **post di Twitter** e le date di pubblicazione. Da qui, si creerà un flusso che invierà automaticamente tweet basati sul contenuto di tali post. 

## <a name="connect-microsoft-flow-services"></a>Connettere i servizi di Microsoft Flow
In questo argomento, si useranno i servizi **SharePoint** e **Twitter**. Se si usa un servizio con cui non si ha familiarità, è prima di tutto necessario connettersi al nuovo servizio. 

1. In Microsoft Flow, selezionare l'**icona dell'ingranaggio**, quindi **Connessioni**.
   
    ![Ottenere la connessione](./media/learning-push-notifications/2-get-connection.png) 
2. Selezionare **+ Crea connessione**.
   
    ![Creare una connessione](./media/learning-push-notifications/3-create-connection.png) 
3. Scorrere verso il basso nell'elenco, trovare Twitter e selezionare **+**.
   
    ![Fare clic sul segno più](./media/learning-push-notifications/4-click-plus.png)
4. Per autorizzare un account di Twitter, immettere il nome utente o l'indirizzo di posta elettronica e la password, quindi selezionare **Autorizza app**.
   
    ![Creare ID e password](./media/learning-push-notifications/5-create-id-pswd.png)
5. Per verificare le connessioni, selezionare l'**icona dell'ingranaggio** e **Connessioni**.
   
    ![Connessioni personali.](./media/learning-push-notifications/6-my-connections.png)
   
    La nuova connessione a Twitter dovrebbe essere visibile assieme alle altre connessioni create 
   
    ![Connessione a Twitter](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>Creare un elenco di SharePoint
La prima cosa da fare è creare un nuovo elenco di SharePoint Online per Contoso Flooring. 

1. In SharePoint Online, selezionare **Nuovo** e quindi **Elenco**.
   
    ![Creare un nuovo elenco](./media/learning-push-notifications/1-new-list.png)
2. Denominare l'elenco **Tweet di Contoso**. 
3. Deselezionare la casella di controllo **Visualizza nella struttura del sito** e selezionare **Crea**.
   
    ![Creare l'elenco](./media/learning-push-notifications/2-name-create-list.png)
   
    Quando si seleziona **Crea**, SharePoint passa al nuovo elenco.
4. Per impostazione predefinita, l'elenco contiene una singola colonna, **Titolo**. Aggiungere un'altra colonna e denominarla **Contenuto Tweet**. Ciò che si scriverà nei tweet verrà archiviato in questa colonna. 
   
   1. Selezionare il segno più, quindi selezionare **Altro...**
      
       ![Creare l'elenco](./media/learning-push-notifications/3-add-more-column-types.png)
   2. Selezionare **Più righe di testo**, quindi selezionare **OK**.
      
       ![Creare l'elenco](./media/learning-push-notifications/4-add-column.png)
5. Aggiungere una colonna per la data e l'ora del tweet e denominarla **Data Tweet**.
   
   1. Come per **Contenuto Tweet**, selezionare il segno più, quindi selezionare **Altro...**
      
       ![Colonna Data e ora](./media/learning-push-notifications/5-date-time-col.png)
   2. Scorrere verso il basso **Formato data e ora**. Selezionare **Data e ora**, in modo da includerle entrambe.
      
       ![Data e ora](./media/learning-push-notifications/6-date-time-must-do.png)
   3. Selezionare **OK**. Nel sito di SharePoint verrà visualizzato l'elenco **Tweet di Contoso** a cui si potranno aggiungere nuovi elementi.

## <a name="build-the-flow"></a>Compilare il flusso
Una volta creato l'elenco, sarà possibile creare il flusso.

### <a name="choose-a-trigger"></a>Scegliere un trigger
1. In Microsoft Flow, passare a **Flussi personali**, quindi selezionare **Crea da zero**.
   
    ![Crea da zero](./media/learning-push-notifications/8-create-from-blank.png)
2. Selezionare **Quando viene creato un elemento**.
   
    ![Aggiungere trigger](./media/learning-push-notifications/9-add-trigger.png)
   
    Si vuole che il trigger venga attivato quando viene aggiunta una nuova riga con il contenuto di un tweet.
3. Selezionare il sito di SharePoint, quindi selezionare l'elenco che è impostato in precedenza, **Tweet di Contoso**.
   
    ![Nuovo elemento creato](./media/learning-push-notifications/11-set-trigger.png)

Per il trigger è tutto.

### <a name="add-an-action-to-delay-posting"></a>Aggiungere un'azione per ritardare la pubblicazione
1. Selezionare **+ Nuovo passaggio**, quindi scegliere **Aggiungi un'azione**. 
   
    ![Aggiungere un passaggio e un'azione](./media/learning-push-notifications/12-add-step-and-action.png)
2. Nel servizio **Pianificazione** selezionare **Ritarda fino a**. 
   
    ![Ritarda fino a](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. Impostare il valore di ritardo.
   
   1. Fare clic o toccare il campo **Timestamp**. 
   2. Quando si apre la casella del contenuto dinamico, scorrere fino alla fine per visualizzare le tre colonne dell'elenco di SharePoint: **Titolo**, **Data Tweet** e **Contenuto Tweet**.
   3. Selezionare **Data Tweet**. 
      
       ![Ritarda fino a timestamp](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       A questo punto, quando un utente aggiunge un elemento all'elenco di SharePoint, qualsiasi azione verrà ritardata fino alla data e all'ora impostate nella colonna **Data Tweet**.
      
       ![Timestamp dinamico](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>Aggiungere un'azione per pubblicare un Tweet
A questo punto si aggiungerà un'altra azione che il flusso eseguirà in corrispondenza della data e dell'ora specificate nella colonna **Data Tweet**.

1. Selezionare **+ Nuovo passaggio**, **Aggiungi un'azione** e infine cercare **Twitter**.
   
    ![Aggiungere tweet](./media/learning-push-notifications/16-add-tweet.png) 
2. Scegliere l'azione, **Twitter - Pubblica un tweet**.
   
    ![Pubblica un tweet](./media/learning-push-notifications/17-post-tweet.png) 
3. Fare clic o toccare il campo **Testo Tweet** e, nella casella del contenuto dinamico, selezionare **Contenuto Tweet**. Ecco la sequenza creata. 
   
    ![Contenuto data Tweet](./media/learning-push-notifications/18-tweet-date-content.png)
4. Selezionare **Crea flusso...**.
   
    ![Creare il flusso](./media/learning-push-notifications/19-tiny-create.png) 
5. Selezionare **Fine**.
   
    ![Fare clic su Fine](./media/learning-push-notifications/19-click-done.png)
   
    A questo punto il flusso è stato completato.
   
    ![Il flusso è completo](./media/learning-push-notifications/20-flow-is-done.png)
   
    Quando viene creato un nuovo elemento nell'elenco di SharePoint, la pubblicazione del tweet verrà ritardata fino alla data preimpostata. Quando giunge tale data, il flusso pubblicherà su Twitter il testo incluso nella colonna **Contenuto Tweet** nell'elenco.

## <a name="next-lesson"></a>Lezione successiva
Nella lezione successiva si apprenderà come **eseguire i flussi in una pianificazione** usando un trigger chiamato **Ricorrenza**.

