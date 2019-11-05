---
title: Usare l'azione applica a ogni per eseguire il ciclo di una matrice di elementi. | Microsoft Docs
description: Usare Microsoft Flow per eseguire il ciclo di una matrice di elementi per verificare più condizioni ed eseguire azioni in base a tali condizioni.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e2852de959f62d5c0ee76fabc9841e3fc9663f73
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545989"
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Usare l'azione applica a ogni in Microsoft Flow per elaborare periodicamente un elenco di elementi
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Molti trigger possono avviare immediatamente un flusso in base a un evento, ad esempio quando arriva un nuovo messaggio di posta elettronica nella posta in arrivo. Questi trigger sono molto interessanti, ma a volte si vuole eseguire un flusso che esegue una query su un'origine dati in base a una pianificazione predefinita, eseguendo determinate azioni in base alle proprietà degli elementi nell'origine dati. A tale scopo, il flusso può essere avviato in base a una pianificazione (ad esempio una volta al giorno) e usare un'azione di ciclo, ad esempio **applica a ogni** per elaborare un elenco di elementi. È ad esempio possibile utilizzare **applica a ogni** per aggiornare record da un database o da un elenco di elementi di Microsoft SharePoint.

In questa procedura dettagliata verrà creato un flusso che viene eseguito ogni 15 minuti ed esegue le operazioni seguenti:

1. Ottiene gli ultimi 10 messaggi non letti nella posta in arrivo di Office 365 Outlook.
2. Verifica ognuno dei 10 messaggi per verificare se un oggetto è **ora** presente nell'oggetto.
3. Controlla se il messaggio di posta elettronica viene inviato dal responsabile o è stato inviato con priorità alta.
4. Invia una notifica push e contrassegna come letto tutti i messaggi di posta elettronica che hanno **subito il contatto** nell'oggetto ed è stato inviato con priorità alta.

Questo diagramma mostra i dettagli del flusso che verrà creato in questa procedura dettagliata:

![Panoramica del flusso in fase di compilazione](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Prerequisiti
Ecco i requisiti per eseguire correttamente i passaggi in questa procedura dettagliata:

* Un account registrato per utilizzare [Microsoft Flow](https://flow.microsoft.com).
* Un account Office 365 Outlook.
* App per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).
* Connessioni a Office 365 Outlook e al servizio di notifica push.

## <a name="create-a-flow"></a>Creare un flusso
1. Accedi [Microsoft Flow](https://flow.microsoft.com):
2. Selezionare la scheda **flussi personali** e quindi creare un flusso da uno spazio vuoto:
   
    ![Crea da zero](./media/apply-to-each/foreach-1.png)
3. Immettere "Schedule" nella casella di ricerca per cercare tutti i servizi e i trigger correlati alla pianificazione.
4. Selezionare il trigger **pianificazione-ricorrenza** per indicare che il flusso verrà eseguito in base a una pianificazione da fornire successivamente:
   
    ![azione di ricorrenza pianificata](./media/apply-to-each/foreach-2.png)
5. Impostare la pianificazione per l'esecuzione ogni 15 minuti:
   
    ![Pianifica esecuzioni](./media/apply-to-each/foreach-3.png)
6. Selezionare **+ nuovo passaggio**, **Aggiungi un'azione**e quindi digitare **Outlook** nella casella di ricerca per cercare tutte le azioni correlate a Microsoft Outlook.
7. Selezionare l'azione **Office 365 Outlook-ricevi messaggi di posta elettronica** :
   
    ![Selezionare l'azione Ricevi messaggi di posta elettronica](./media/apply-to-each/foreach-4.png)
8. Verrà visualizzata la scheda **Ottieni messaggi di posta elettronica** . Configurare la scheda **Ottieni messaggi di posta elettronica** per selezionare i primi 10 messaggi di posta elettronica non letti dalla cartella della posta in arrivo. Non includere allegati perché non verranno usati nel flusso:
   
    ![Configura scheda e-mail](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Fino a questo punto, è stato creato un flusso semplice che riceve alcuni messaggi di posta elettronica dalla posta in arrivo. Questi messaggi di posta elettronica verranno restituiti in una matrice; **per ogni** azione è necessaria una matrice, quindi questo è esattamente ciò che è necessario.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Aggiungere azioni e condizioni
1. Selezionare **+ nuovo passaggio**e **quindi** **Aggiungi un'azione applica a ogni** :
   
    ![Selezionare applica a ogni](./media/apply-to-each/foreach-6.png)
2. Inserire il token del **corpo** nella casella **selezionare un output dai passaggi precedenti** nella casella **applica a ogni** scheda. Questa operazione estrae il corpo dei messaggi di posta elettronica da usare nell'azione **applica a ogni** :
   
    ![Aggiungi token corpo](./media/apply-to-each/foreach-7.png)
3. Selezionare **Aggiungi una condizione**:
   
    ![Aggiungi condizione](./media/apply-to-each/foreach-8.png)
4. Configurare la scheda **condizione** per cercare le parole "Meet Now" nel soggetto di ogni messaggio di posta elettronica:
   
   * Inserire il **token dell'oggetto nella** casella **nome oggetto** .
   * Selezionare **Contains** nell'elenco **relazione** .
   * Immettere **Meet Now** nella casella **valore** .
     
     ![Configura condizione](./media/apply-to-each/foreach-subject-condition.png)
5. Selezionare **altro**e quindi selezionare **Aggiungi una condizione** dal ramo **se sì, non fare nulla** . Verrà visualizzata la scheda **condizione 2** ; configurare la scheda come segue:
   
   * Inserire il token di **importanza** nella casella **nome oggetto** .
   * Select **è uguale a** nell'elenco **relazione** .
   * Immettere **High** nella casella **valore** .
     
     ![Aggiungi condizione](./media/apply-to-each/foreach-importance-condition.png)
6. Selezionare **Aggiungi un'azione** nella sezione **se sì, non fare nulla** . Verrà visualizzata la scheda **scegliere un'azione** , in cui è possibile definire cosa dovrebbe accadere se la condizione di ricerca (l'indirizzo di posta elettronica **Meet Now** è stata inviata con priorità alta) è true:
   
    ![Aggiungi azione](./media/apply-to-each/foreach-9.png)
7. Cercare **notifica**, quindi selezionare l'azione **notifiche-invia una notifica per dispositivi mobili** :
   
    ![Cerca e Seleziona notifica](./media/apply-to-each/foreach-10.png)
8. Nella scheda **Invia una notifica per dispositivi mobili** specificare i dettagli per la notifica push che verrà inviata se l'oggetto di un messaggio di posta elettronica contiene "Meet Now" e quindi selezionare **Aggiungi un'azione**:
   
    ![Configura notifica](./media/apply-to-each/foreach-11.png)
9. Immettere **Read** come termine di ricerca, quindi selezionare l'azione **Office 365 Outlook-Mark as Read** . Ogni messaggio di posta elettronica verrà contrassegnato come letto dopo l'invio della notifica push:
   
    ![Aggiungi Contrassegno come azione di lettura](./media/apply-to-each/foreach-12.png)
10. Aggiungere il token **ID messaggio** alla casella **ID messaggio** della scheda **Contrassegna come letto** . Potrebbe essere necessario selezionare **Visualizza altro** per trovare il token **ID del messaggio** . Indica l'ID del messaggio che verrà contrassegnato come letto:
    
     ![Aggiungi ID messaggio](./media/apply-to-each/foreach-13.png)
11. Tornando alla scheda **condizione 2** , sul ramo **if no, non eseguire alcuna operazione** :
    
    * Selezionare **Aggiungi un'azione**, quindi digitare **Get Manager** nella casella di ricerca.
    * Selezionare l'azione **Office 365 users-get Manager** dall'elenco dei risultati della ricerca.
    * Immettere l'indirizzo di posta elettronica *completo* nella casella **utente** della scheda **Ottieni responsabile** .
      
      ![aggiungere e configurare l'azione Ottieni gestione](./media/apply-to-each/foreach-get-manager.png)
12. Selezionare **altro**e quindi selezionare **Aggiungi una condizione** dal ramo **if no** . Verrà visualizzata la scheda **condizione 3** . configurare la scheda per verificare se l'indirizzo di posta elettronica del mittente del messaggio di posta elettronica (il token da) è lo stesso dell'indirizzo di posta elettronica del Capo (il token di posta elettronica):
    
    * Inserire il token **from** nella casella **nome oggetto** .
    * Selezionare **Contains** nell'elenco **relazione** .
    * Immettere il token di **posta elettronica** nella casella **valore** .
      
      ![configurare la condizione di ricerca](./media/apply-to-each/foreach-condition3-card.png)
13. Selezionare **Aggiungi un'azione** nella sezione **se sì, non fare nulla** della scheda **condizione 3** . Verrà visualizzata la scheda **If Yes (se sì** ), in cui verrà definito cosa dovrebbe accadere se la condizione di ricerca (il messaggio di posta elettronica inviato dal capo) è true:
    
     ![Configura condizione](./media/apply-to-each/foreah-condition3-add-action.png)
14. Cercare **notifica**, quindi selezionare l'azione **notifiche-invia una notifica per dispositivi mobili** :
    
     ![Cerca azione di notifica](./media/apply-to-each/foreach-10.png)
15. Nella scheda **Invia una notifica per dispositivi mobili 2** specificare i dettagli per la notifica push che verrà inviata se il messaggio di posta elettronica viene inviato dal responsabile e quindi selezionare **Aggiungi un'azione**:
    
     ![Configura scheda di notifica](./media/apply-to-each/foreach-boss-notification.png)
16. Aggiungere l'azione **Office 365 Outlook-Mark come Read** . Ogni messaggio di posta elettronica verrà contrassegnato come letto dopo l'invio della notifica push:
    
     ![Aggiungi Contrassegno come azione di lettura](./media/apply-to-each/foreach-12.png)
17. Aggiungere il token **ID messaggio** alla scheda **Contrassegno come letto 2** . Potrebbe essere necessario selezionare **Visualizza altro** per trovare il token **ID del messaggio** . Indica l'ID del messaggio che verrà contrassegnato come letto:
    
     ![Configura Contrassegno come azione di lettura](./media/apply-to-each/foreach-mark-as-read2.png)
18. Assegnare un nome al flusso e quindi crearlo:
    
     ![assegnare un nome al flusso e salvarlo](./media/apply-to-each/foreach-14.png)

Se è stata seguita, il flusso dovrebbe essere simile al diagramma seguente:

![Panoramica del flusso creato](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Eseguire il flusso
1. Inviare a se stessi un messaggio di posta elettronica di importanza elevata che includa **ora** in oggetto (o che un utente dell'organizzazione invii un messaggio di posta elettronica di questo tipo).
2. Confermare che il messaggio di posta elettronica si trova nella posta in arrivo e non è stato letto.
3. Accedere Microsoft Flow, selezionare **flussi personali**e quindi selezionare **Esegui ora**:
   
    ![Esegui adesso](./media/apply-to-each/foreach-run-1.png)
4. Selezionare **Esegui flusso** per confermare che si vuole effettivamente eseguire il flusso:
   
    ![conferma esecuzione](./media/apply-to-each/foreach-run-2.png)
5. Dopo alcuni istanti verranno visualizzati i risultati dell'esecuzione riuscita:
   
    ![Risultati esecuzione](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Visualizzare i risultati dell'esecuzione
Ora che il flusso è stato eseguito correttamente, è necessario ricevere la notifica push nel dispositivo mobile.

1. Aprire l'app Microsoft Flow nel dispositivo mobile, quindi selezionare la scheda **attività** . Verrà visualizzata la notifica push relativa alla riunione:
   
    ![Selezionare la scheda attività](./media/apply-to-each/foreach-notification-1.png)
2. Per visualizzare il contenuto completo della notifica, potrebbe essere necessario selezionare la notifica. Verrà visualizzata la notifica completa, simile alla seguente:
   
    ![Dettagli notifica](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Se non si riceve la notifica push, verificare che il dispositivo mobile disponga di una connessione dati funzionante.
   > 
   > 

