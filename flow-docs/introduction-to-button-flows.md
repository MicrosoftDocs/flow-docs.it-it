---
title: Informazioni su come automatizzare ed eseguire attività ripetitive con i flussi attivati da un pulsante | Microsoft Docs
description: Introduzione ai flussi di un pulsante.
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
ms.date: 01/30/2017
ms.author: deonhe
ms.openlocfilehash: 558570733819e1fde6c1845ed5ca9debe9232c88
ms.sourcegitcommit: f0202f74ba9a2282a670a1751462f598a5ea0ce5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="introducing-button-flows"></a>Introduzione ai flussi di un pulsante
## <a name="what-are-button-flows"></a>Cosa sono i flussi di un pulsante?
Esistono molte attività ripetitive che a tutti piacerebbe poter eseguire con il semplice tocco di un pulsante. Ad esempio, potrebbe essere necessario inviare rapidamente un'e-mail al team per ricordare ai componenti di partecipare alla riunione giornaliera, oppure avviare una nuova compilazione di Visual Studio Online della base del codice dopo aver ricevuto la notifica che non ci sono archiviazioni pianificate per la giornata. I flussi di un pulsante consentono di eseguire queste e molte altre attività con il semplice tocco di un pulsante sul dispositivo mobile.

**Nota** I flussi di un pulsante possono essere creati da dispositivo mobile o dal portale di Flow.  
  ![Immagine panoramica](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Perché creare pulsanti?
È possibile creare pulsanti per eseguire attività ripetitive in qualsiasi luogo e in qualsiasi momento tramite il dispositivo mobile. Questo consente di risparmiare tempo e, dal momento che le attività sono automatizzate, riduce la quantità di errori rispetto all'esecuzione manuale.  

## <a name="create-a-button"></a>Creare un pulsante
### <a name="prerequisites"></a>Prerequisiti
* Accedere a Flow. L'amministratore può fornire l'accesso,
* cioè un account con le autorizzazioni per usare i connettori per creare il pulsante. Ad esempio, per creare un pulsante per accedere a Dropbox è necessario un account Dropbox.

### <a name="from-the-portal"></a>Dal portale
In questa procedura dettagliata viene creato un pulsante per avviare una compilazione di Visual Studio Online (VSO) e inviare notifiche per informare l'utente all'avvio:  

1. Selezionare l'elenco a discesa **Visualizzazione** e scegliere la categoria **Pulsante**. In questo modo l'elenco dei modelli viene filtrato escludendo quelli che non possono essere usati nei flussi di un pulsante.  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-1.png)   
2. Selezionare il modello **Trigger a new build in VSO** (Attivazione nuova compilazione in VSO) dall'elenco di modelli.  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-2.png)  
3. Selezionare il pulsante **Use this template** (Usa questo modello) alla pagina **Trigger a new build in VSO** (Attivazione nuova compilazione in VSO).   
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-3.png)  
4. Se non è stato effettuato l'accesso, verrà chiesto di farlo a questo punto:  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-4.png)  
5. Dopo aver effettuato l'accesso a Flow, verrà chiesto di accedere ai connettori usati nel modello selezionato. Nel passaggio 2 dell'esempio sopra è stato selezionato il modello **Trigger a new build in VSO** (Attivazione nuova compilazione in VSO), quindi, se non è ancora stato fatto, è necessario effettuare l'accesso a VSO e agli eventuali altri connettori in uso:  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Per autorizzare Flow ad accedere al proprio account VSO, selezionare il pulsante **Accetta**.  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-5.png)   
   **Note** Ogni connettore dovrà essere autorizzato allo stesso modo. Quando è possibile procedere con il passaggio successivo, la finestra di progettazione avrà un aspetto simile al seguente. Per andare avanti, selezionare il pulsante **Continua**:  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-6.png)   
7. A questo punto è possibile configurare le proprietà per la compilazione da avviare:    
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-7.png)  
8. Selezionare o immettere **Nome account**, **Nome progetto**, **ID definizione di compilazione**, **Ramo di origine** e, facoltativamente, **Parametri** nella scheda **Accoda nuova compilazione**:    
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-8.png)  
9. Successivamente, configurare le proprietà della notifica push nella scheda **Send a push notification** (Invia notifica push). Per impostazione predefinita, questa notifica push è configurata in modo da inviare un collegamento HTML a una pagina Web che visualizza lo stato della compilazione:  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-9.png)  
10. Selezionare il pulsante **Crea flusso** per salvare il flusso di un pulsante: ![Immagine panoramica](./media/introduction-to-button-flows/create-button-10.png)  
11. Dopo alcuni secondi dovrebbe essere visualizzato questo messaggio per confermare l'esito positivo:  
    ![Immagine panoramica](./media/introduction-to-button-flows/create-button-11.png)  

È stato creato così un flusso di un pulsante. È ora possibile eseguire il flusso in qualsiasi momento e in qualsiasi luogo, nella scheda **Pulsanti** dell'app Flow. Basta premere il pulsante. L'app per dispositivi mobili Microsoft Flow è disponibile per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Da dispositivo mobile
**Nota**: anche se in questa procedura dettagliata vengono visualizzate le schermate relative a un dispositivo Android, l'esperienza e le schermate sono simili anche su dispositivi iOS.

Nell'app Flow:

1. Selezionare la scheda **Sfoglia** e scorrere fino alla categoria **Pulsanti**.  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Selezionare il collegamento **See all** (Vedi tutti). Vengono visualizzati tutti i modelli di pulsanti esistenti.     
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Selezionare il modello **Send an email to remind your team to join a meeting** (Invio e-mail di promemoria sul meeting al team)    
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Selezionare il collegamento **USE THIS TEMPLATE** (USA QUESTO MODELLO) nella parte inferiore della pagina.    
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. È necessario effettuare l'accesso a tutti i servizi usati dal modello:    
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Al termine, selezionare **Avanti**.      
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Selezionare **Crea**. Qui è anche possibile esaminare il flusso e apportare eventuali modifiche necessarie, ad esempio per personalizzare l'e-mail.        
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Dopo alcuni istanti, viene creato il flusso di un pulsante. Selezionare **SEE MY FLOW** (VEDI FLUSSO):   
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Visualizzare tutti i flussi nella scheda **Flussi personali**  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

È stato creato così un flusso di un pulsante. È ora possibile eseguire il flusso in qualsiasi momento e in qualsiasi luogo, nella scheda **Pulsanti** dell'app Flow. Basta premere il pulsante. L'app Flow è attualmente disponibile per dispositivi mobili iOS e Android.  

![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Attivare un flusso di un pulsante
Una volta creato un flusso di un pulsante, è necessario eseguirlo. Dato che i flussi di un pulsante possono essere eseguiti solo dall'app Flow, è necessario aver installato Flow sui dispositivi mobili Android o iOS.  

1. A questo punto, avviare l'app Flow, toccare la scheda **Pulsanti** nella parte inferiore della pagina e toccare il *pulsante* che rappresenta il flusso di un pulsante da attivare:  
   ![Immagine panoramica](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Vedere l'avanzamento durante l'esecuzione del flusso:  
   ![Immagine panoramica](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Infine, la pagina si aggiorna per indicare che il flusso di un pulsante è stato completato:  
   ![Immagine panoramica](./media/introduction-to-button-flows/trigger-button-3.png)   

Questo è tutto ciò che serve sapere sull'esecuzione di un flusso. 

A questo punto si riceverà la notifica push che informa dell'invio dell'e-mail.  

## <a name="monitor-your-button-flow-runs"></a>Monitorare l'esecuzione dei flussi di un pulsante
È possibile monitorare i flussi di un pulsante dalla scheda **Attività** dell'app Flow:   
![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Nota**: toccare qualsiasi attività per approfondire i risultati e scoprire altre informazioni sull'esecuzione.  

![Immagine panoramica](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Gestire i flussi di un pulsante
L'utente ha il totale controllo sui flussi di un pulsante, di conseguenza può abilitarli o disabilitarli, modificarli oppure eliminarli in qualsiasi momento e in qualsiasi luogo. Dall'app per dispositivi mobili o dal portale di Flow selezionare **Flussi personali** per iniziare a gestire i flussi.    

Nella scheda **Flussi personali** dell'app Flow:

1. Selezionare il flusso da gestire:    
   ![Immagine panoramica](./media/introduction-to-button-flows/trigger-button-4.png)   
2. È possibile toccare una delle opzioni seguenti in base all'operazione che si desidera compiere:    
   ![Immagine panoramica](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Toccare **Delete flow** (Elimina flusso) per eliminare un flusso.  

**Note** Quando si elimina un flusso, viene eliminata l'intera cronologia dei flussi:   
![Immagine panoramica](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Al termine delle modifiche al flusso di un pulsante, toccare **Aggiorna** per salvare le modifiche:   
   ![Immagine panoramica](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Toccare **Run history** (Cronologia esecuzioni) per visualizzare i risultati di un particolare flusso di un pulsante:    
   ![Immagine panoramica](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Se si disabilita un flusso, non sarà più disponibile nella scheda **Pulsanti**:    
   ![Immagine panoramica](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Passaggi successivi
* [Condividere i flussi dei pulsanti](share-buttons.md).
* Viene illustrato come usare i [token per attivare i pulsanti](introduction-to-button-trigger-tokens.md) per inviare dati in tempo reale quando vengono eseguiti i flussi dei pulsanti.
* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

