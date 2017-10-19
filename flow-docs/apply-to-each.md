---
title: Usare l'azione Applica a ogni per riprodurre a ciclo una matrice di elementi. | Microsoft Docs
description: "Usare Microsoft Flow per riprodurre a ciclo una matrice di elementi con cui verificare più condizioni e intraprendere azioni in base alle stesse."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: deonhe
ms.openlocfilehash: 37f1ce939db23694bcd92e7f1af75bf6c474be91
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Usare l'azione Applica a ogni in Microsoft Flow per elaborare periodicamente un elenco di elementi
Molti trigger possono avviare immediatamente un flusso in base a un evento, ad esempio quando si riceve un nuovo messaggio di posta elettronica nella posta in arrivo. Questi trigger sono molto utili, ma a volte si vuole eseguire un flusso che interroghi un'origine dati secondo una pianificazione predefinita, eseguendo determinate azioni sulla base delle proprietà degli elementi nell'origine dati. A tale scopo, il flusso può essere avviato secondo una pianificazione (ad esempio, una volta al giorno) e si può usare un'azione di ciclo, ad esempio **Applica a ogni**, per elaborare un elenco di elementi. È possibile, ad esempio, usare **Applica a ogni** per aggiornare i record da un database o un elenco di elementi da Microsoft SharePoint.

In questa procedura dettagliata, verrà creato un flusso che viene eseguito ogni 15 minuti ed esegue le operazioni seguenti:

1. Ottiene gli ultimi 10 messaggi non letti nella posta in arrivo di Outlook Office 365.
2. Controlla ciascuno dei 10 messaggi per verificare se contengono **riunione immediata** nell'oggetto.
3. Controlla se il messaggio proviene dal proprio capo o se è stato inviato con priorità alta.
4. Invia una notifica push e contrassegna come letto qualsiasi messaggio di posta elettronica con **riunione immediata** nell'oggetto e che proviene dal proprio capo o è stato inviato con priorità alta.

Questo diagramma mostra i dettagli del flusso che si creerà in questa procedura dettagliata:

![panoramica del flusso in corso di creazione](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Prerequisiti
Ecco i requisiti per eseguire correttamente i passaggi in questa procedura dettagliata:

* Un account registrato per l'uso di [Microsoft Flow](https://flow.microsoft.com).
* Un account di Office 365 Outlook.
* L'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
* Connessioni a Office 365 Outlook e al servizio di notifica push.

## <a name="create-a-flow"></a>Creare un flusso
1. Accedere a [Microsoft Flow](https://flow.microsoft.com):
2. Selezionare la scheda **Flussi personali** e quindi creare un flusso da zero:
   
    ![crea da zero](./media/apply-to-each/foreach-1.png)
3. Immettere "pianificazione" nella casella di ricerca per cercare tutti i servizi e i trigger relativi alla pianificazione.
4. Selezionare il trigger **Pianificazione - Ricorrenza** per indicare che il flusso verrà eseguito secondo una pianificazione che si sceglierà in seguito:
   
    ![azione pianificazione ricorrenza](./media/apply-to-each/foreach-2.png)
5. Impostare la frequenza di esecuzione della pianificazione ogni 15 minuti:
   
    ![esecuzioni pianificazione](./media/apply-to-each/foreach-3.png)
6. Selezionare **+ Nuovo passaggio**, **Aggiungi un'azione** e quindi digitare **outlook** nella casella di ricerca per cercare tutte le azioni relative a Microsoft Outlook.
7. Selezionare l'azione **Office 365 Outlook - Ottieni messaggi di posta elettronica**:
   
    ![selezionare l'azione ottieni messaggi di posta elettronica](./media/apply-to-each/foreach-4.png)
8. Verrà aperta la scheda **Ottieni messaggi di posta elettronica**. Configurare la scheda **Ottieni messaggi di posta elettronica** selezionando i primi 10 messaggi non letti nella cartella Posta in arrivo. Non includere allegati perché non verranno usati nel flusso:
   
    ![configurare scheda messaggi di posta elettronica](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Finora è stato creato un flusso semplice che ottiene alcuni messaggi di posta elettronica dalla posta in arrivo. Questi messaggi verranno restituiti in una matrice, cioè esattamente l'obiettivo dell'azione **Applica a ogni**.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Aggiungere azioni e condizioni
1. Selezionare **+ Nuovo passaggio**, **Altro** e quindi l'azione **Aggiungi Apply to each**:
   
    ![selezionare applica a ogni](./media/apply-to-each/foreach-6.png)
2. Inserire il token **Corpo** nella casella **Selezionare un output dai passaggi precedenti** della scheda **Applica a ogni**. In tal modo, verrà estratto il corpo dei messaggi da usare nell'azione **Applica a ogni**:
   
    ![aggiungere token corpo](./media/apply-to-each/foreach-7.png)
3. Selezionare **Aggiungi una condizione**:
   
    ![aggiungi una condizione](./media/apply-to-each/foreach-8.png)
4. Configurare la scheda **Condizione** in modo da cercare nell'oggetto di ogni messaggio le parole "riunione immediata":
   
   * Inserire il token **Oggetto** nella casella **Nome oggetto**.
   * Selezionare **contiene** nell'elenco **Relazione**.
   * Immettere **riunione immediata** nella casella **Valore**.
     
     ![configurare condizione](./media/apply-to-each/foreach-subject-condition.png)
5. Selezionare **Altro**, quindi selezionare **Aggiungi una condizione** dal ramo **SE SÌ, NON FARE NULLA**. Verrà visualizzata la scheda **Condizione 2**, da configurare come segue:
   
   * Inserire il token **Priorità** nella casella **Nome oggetto**.
   * Selezionare **è uguale a** nell'elenco **Relazione**.
   * Immettere **Alta** nella casella **Valore**.
     
     ![aggiungi una condizione](./media/apply-to-each/foreach-importance-condition.png)
6. Selezionare **Aggiungi un'azione** nella sezione **SE SÌ, NON FARE NULLA**. Verrà aperta la scheda**Scegliere un'azione**, in cui definire cosa dovrebbe accadere se la condizione di ricerca (il messaggio **riunione immediata** è stato inviato con priorità elevata) è true:
   
    ![aggiungi un'azione](./media/apply-to-each/foreach-9.png)
7. Cercare **notifica**, quindi selezionare l'azione **Notifications - Send me a mobile notification** (Notifiche - Inviami una notifica mobile).
   
    ![cercare e selezionare notifica](./media/apply-to-each/foreach-10.png)
8. Nella scheda **Send me a mobile notification** inserire i dettagli per la notifica push che verrà inviata se l'oggetto del messaggio contiene "riunione immediata", quindi selezionare **Aggiungi un'azione**:
   
    ![configurare la notifica](./media/apply-to-each/foreach-11.png)
9. Immettere **letto** come termine di ricerca, quindi selezionare l'azione **Office 365 Outlook -Segna come già letto**. Ogni messaggio verrà in questo modo contrassegnato come letto dopo l'invio della notifica push:
   
    ![Aggiungere azione segna come già letto](./media/apply-to-each/foreach-12.png)
10. Aggiungere il token **ID messaggio** alla casella **ID messaggio** della scheda **Segna come già letto**. Potrebbe essere necessario selezionare **Vedi altri** per trovare il token **ID messaggio**. Ciò indica l'ID del messaggio che verrà contrassegnato come letto:
    
     ![aggiungere l'id del messaggio](./media/apply-to-each/foreach-13.png)
11. Tornando alla scheda **Condizione 2**, nel ramo **SE NO, NON FARE NULLA**:
    
    * Selezionare **Aggiungi un'azione**, quindi digitare **recupera il responsabile** nella casella di ricerca.
    * Selezionare l'azione **Utenti di Office 365 - Recupera il responsabile** dall'elenco dei risultati di ricerca.
    * Immettere l'indirizzo di posta elettronica *completo* nella casella **Utente** della scheda **Recupera il responsabile**.
      
      ![aggiungere e configurare l'azione recupera il responsabile](./media/apply-to-each/foreach-get-manager.png)
12. Selezionare **Altro**, quindi selezionare **Aggiungi una condizione** dal ramo **SE NO**. Verrà visualizzata la scheda **Condizione 3**. Configurarla in modo da verificare se l'indirizzo di posta elettronica del mittente del messaggio di posta elettronica (il token Da) sia lo stesso indirizzo di posta elettronica del proprio capo (token Posta elettronica):
    
    * Inserire il token **Da** nella casella **Nome oggetto**.
    * Selezionare **contiene** nell'elenco **Relazione**.
    * Immettere **Posta elettronica** nella casella **Valore**.
      
      ![configurare condizione di ricerca](./media/apply-to-each/foreach-condition3-card.png)
13. Selezionare **Aggiungi un'azione** nella sezione **SE SÌ, NON FARE NULLA** della scheda **Condizione 3**. Verrà aperta la scheda**SE SÌ**, in cui definire cosa dovrebbe accadere se la condizione di ricerca (il messaggio è stato inviato dal capo) è true:
    
     ![configurare condizione](./media/apply-to-each/foreah-condition3-add-action.png)
14. Cercare **notifica**, quindi selezionare l'azione **Notifications - Send me a mobile notification** (Notifiche - Inviami una notifica mobile).
    
     ![cercare l'azione di notifica](./media/apply-to-each/foreach-10.png)
15. Nella scheda **Send me a mobile notification 2** inserire i dettagli per la notifica push che verrà inviata se il messaggio è stato inviato dal capo, quindi selezionare **Aggiungi un'azione**:
    
     ![configurare la scheda di notifica](./media/apply-to-each/foreach-boss-notification.png)
16. Aggiungere l'azione **Office 365 Outlook - Segna come già letto**. Ogni messaggio verrà in questo modo contrassegnato come letto dopo l'invio della notifica push:
    
     ![Aggiungere azione segna come già letto](./media/apply-to-each/foreach-12.png)
17. Aggiungere il token **ID messaggio** alla scheda **Segna come già letto 2**. Potrebbe essere necessario selezionare **Vedi altri** per trovare il token **ID messaggio**. Ciò indica l'ID del messaggio che verrà contrassegnato come letto:
    
     ![configurazione azione segna come già letto](./media/apply-to-each/foreach-mark-as-read2.png)
18. Assegnare un nome al flusso, quindi crearlo:
    
     ![assegnare un nome al flusso e salvarlo](./media/apply-to-each/foreach-14.png)

Se la procedura è stata seguita correttamente, il flusso dovrebbe essere simile al seguente:

![panoramica del flusso creato](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Eseguire il flusso
1. Inviare a se stessi un messaggio di posta elettronica ad alta priorità che includa le parole **riunione immediata** nell'oggetto (o chiedere a un utente nell'organizzazione di inviarlo).
2. Verificare che il messaggio di posta elettronica sia nella posta in arrivo e che non sia letto.
3. Accedere a Microsoft Flow, selezionare **Flussi personali** e quindi **Esegui ora**:
   
    ![esegui ora](./media/apply-to-each/foreach-run-1.png)
4. Selezionare **Esegui ora** per confermare che si vuole eseguire il flusso:
   
    ![confermare esecuzione](./media/apply-to-each/foreach-run-2.png)
5. Dopo qualche istante verranno visualizzati i risultati dell'esecuzione:
   
    ![risultati dell'esecuzione](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Visualizzare i risultati dell'esecuzione
Ora che il flusso è stato eseguito correttamente, si dovrebbe ricevere la notifica push sul dispositivo mobile.

1. Aprire l'app Microsoft Flow sul proprio dispositivo mobile e quindi selezionare la scheda **Attività**. Verrà visualizzata la notifica push riguardante la riunione:
   
    ![selezionare la scheda attività](./media/apply-to-each/foreach-notification-1.png)
2. Per visualizzare l'intero contenuto della notifica, è necessario selezionarla. Verrà visualizzata la notifica completa, simile alla seguente:
   
    ![dettagli della notifica](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Se si non riceve la notifica push, verificare che il dispositivo mobile abbia una connessione dati funzionante.
   > 
   > 

