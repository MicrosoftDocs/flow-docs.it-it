---
title: Creare un flusso attivato da un pulsante | Microsoft Docs
description: Informazioni su come creare un flusso che viene attivato da un pulsante.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: s8ozmlVRV-Q
courseduration: 11m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: e72013611d6dbd21c06716805d42fbdd4eff7cfc
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-button-flow"></a>Creare un flusso del pulsante
In questo argomento si apprenderà come **creare un flusso del pulsante** per la società Contoso Flooring Company. 

I flussi del pulsante servono a **inviare posta elettronica** a un team e **avvisarli delle attività** da eseguire. La **proprietà** dei flussi **può essere assegnata a un** solo operatore o **condivisa tra più** membri di un team.  

1. Prima di tutto, accedere al [sito Web di Microsoft Flow](https://ms.flow.microsoft.com).
2. Selezionare **Flussi personali** e quindi **Crea da zero**.
   
    ![Crea da zero](./media/learning-create-button-flow/2-create-from-blank.png)
   
    La prima cosa che serve è un trigger. Il flusso del pulsante è pratico da usare. 
3. Se non è presente nell'elenco, selezionare **Cerca tra centinaia di connettori e trigger** nella parte inferiore della pagina e immettere **pulsante** per visualizzarlo automaticamente. 
4. Selezionare **Pulsante Microsoft Flow per dispositivi mobili**.
   
    ![Cercare pulsante](./media/learning-create-button-flow/3-button-flow.png) 
5. Selezionare **Pulsante Microsoft Flow per dispositivi mobili - Attiva un flusso manualmente**.
   
    ![Selezionare trigger manuale](./media/learning-create-button-flow/4-press-it.png)
6. Nella schermata di input, selezionare **Aggiungi input di testo**.
   
    ![Aggiungi input](./media/learning-create-button-flow/5-add-input.png)
7. Immettere **Contoso Flooring** nella prima casella di testo e **Email di consegna magazzino** nella seconda casella di testo.
   
    ![Aggiungi input](./media/learning-create-button-flow/6-text-for-flow.png)
8. Selezionare **Nuovo passaggio**. 
   
    ![Testo di input](./media/learning-create-button-flow/7-input-description.png)
9. Selezionare **Aggiungi un'azione**. 
   
    ![Aggiungere un'azione](./media/learning-create-button-flow/8-add-an-action.png)
10. Selezionare il connettore **Office 365 Outlook**. Se non è presente, cercare **outlook**.
    
     ![Cercare outlook](./media/learning-create-button-flow/9-search-outlook.png)
11. Selezionare **Office 365 Outlook - Invia un messaggio di posta elettronica**.
    
     ![Invia un messaggio di posta elettronica](./media/learning-create-button-flow/10-send-email.png)
    
     Quando viene premuto il pulsante, viene inviato un messaggio all'intero team del magazzino di Contoso, indipendentemente da dove si trova nell'edificio, per informarlo che è arrivata la consegna.
12. Espandere i campi e personalizzare il messaggio di posta elettronica per Contoso Flooring.
    
    1. Nel campo **A** immettere un indirizzo di posta elettronica valido all'interno dell'organizzazione.
    2. Nel campo **Oggetto** immettere **Consegna arrivata**. 
    3. A destra viene visualizzata la casella **Contenuto dinamico**. Per mostrare nella riga dell'oggetto la data e l'ora in cui è stato premuto il pulsante, selezionare **Data** e **Timestamp**. 
       
        ![Data e ora e-mail](./media/learning-create-button-flow/11-email-date-time.png)
13. A questo punto, immettere un semplice **Corpo** per l'e-mail, ad esempio **Al team del magazzino: si prega di scaricare la piattaforma perché è arrivata la consegna odierna**.
14. Selezionare **Crea flusso** per salvare il flusso.
    
     ![Creare il flusso](./media/learning-create-button-flow/12-create-flow.png)

## <a name="create-a-team-flow"></a>Creare un flusso del team
È possibile usare questo flusso del pulsante come esempio di come creare un flusso del team. Cosa accade se l'autore di questo flusso è in congedo malattia? Cosa succede se lascia la società? Ci si vorrà assicurare della continua esecuzione di questo flusso. A tale scopo, aggiungere dei comproprietari.

1. Selezionare l'**icona del team** nel flusso per aggiungere un comproprietario.
   
    ![Creare il flusso del team](./media/learning-create-button-flow/13-create-team-flow.png) 
2. Immettere nomi, indirizzi di posta elettronica o gruppi utenti per aggiungere i comproprietari.
   
    ![Aggiungere i comproprietari](./media/learning-create-button-flow/14-add-co-owners.png)
3. Per rimuovere i comproprietari, selezionare il Cestino a destra del relativo nome.
   
    ![Rimuovere i comproprietari](./media/learning-create-button-flow/15-remove-co-owners.png)
4. Selezionare **Rimuovi questo proprietario** per completare la rimozione.
   
    ![Rimuovere i comproprietari](./media/learning-create-button-flow/16-agree-to-remove.png)

## <a name="summary"></a>Riepilogo
In questa lezione, si è visto come **creare un flusso del pulsante**. 

In pochi minuti, il flusso ha permesso a un operatore del magazzino di **avvertire il team** dell'**arrivo di una consegna**, in modo che il team non dovesse attendere invano, sprecando tempo prezioso che avrebbe potuto impiegare in altre attività. 

L'operatore ha quindi condiviso il pulsante con il suo team, in modo che altri potessero attivare lo stesso flusso in sua assenza.

## <a name="next-lesson"></a>Lezione successiva
La lezione successiva illustrerà come creare un flusso che usa le **notifiche push**.
