---
title: Informazioni su come automatizzare ed eseguire attività ripetitive con i flussi di un pulsante | Microsoft Docs
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 403c3d7cc116555ab26d5e4168587de5e5a6720f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547526"
---
# <a name="introducing-button-flows"></a>Introduzione ai flussi di un pulsante
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>Che cosa sono i flussi di un pulsante?
Ci sono molte attività ripetitive che si desidera eseguire con un semplice tocco di un pulsante. Ad esempio, potrebbe essere necessario inviare rapidamente un messaggio di posta elettronica al team per ricordare di partecipare alla sincronizzazione del team giornaliera oppure è possibile avviare una nuova build di Visual Studio online della codebase dopo aver ricevuto una notifica che non ci sono più archiviazioni pianificati per la giornata. I flussi dei pulsanti consentono di eseguire queste e molte altre attività semplicemente toccando un pulsante del dispositivo mobile.

**Nota** È possibile creare flussi di pulsanti dal dispositivo mobile o dal portale di Flow.  
  ![immagine panoramica](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Perché creare i pulsanti?
È possibile creare pulsanti che consentono di eseguire facilmente attività ripetitive da qualsiasi luogo, in qualsiasi momento tramite il dispositivo mobile. L'esecuzione dei pulsanti consente di risparmiare tempo e, dal momento che le attività eseguite vengono automatizzate, saranno presenti meno errori rispetto a quelle eseguite manualmente.  

## <a name="create-a-button"></a>Creare un pulsante
### <a name="prerequisites"></a>Prerequisiti
* Accesso a Flow. L'amministratore può fornire l'accesso.
* Un account con le autorizzazioni per usare i connettori per creare il pulsante. Ad esempio, è necessario un account Dropbox per poter creare un pulsante che accede a Dropbox.

### <a name="from-the-portal"></a>Dal portale
In questa procedura dettagliata verrà creato un pulsante che avvia una compilazione di Visual Studio online (VSO) e invia notifiche per informare l'utente all'avvio della compilazione:  

1. Selezionare l'elenco a discesa **Mostra** e scegliere la categoria **pulsante** . In questo modo l'elenco dei modelli viene filtrato solo in quelli che possono essere usati nei flussi di un pulsante.  
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-1.png)   
2. Selezionare il modello **trigger a New Build in VSO** dall'elenco di modelli.  
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-2.png)  
3. Selezionare il pulsante **Usa questo modello** nella pagina **attiva una nuova compilazione in VSO** .   
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-3.png)  
4. Se non è stato eseguito l'accesso, verrà richiesto di farlo a questo punto:  
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-4.png)  
5. Dopo aver effettuato l'accesso a Flow, verrà richiesto di accedere ai connettori usati nel modello selezionato. In questo esempio, nel passaggio 2 precedente è stato selezionato il modello **trigger a New Build in VSO** , quindi è necessario accedere a VSO (e a qualsiasi altro connettore che si sta usando), se non è già stato effettuato l'accesso:  
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Selezionare il pulsante **Accept (Accetto** ) per autorizzare Flow ad accedere all'account VSO.  
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-5.png)   
   **Nota** È necessario autorizzare ogni connettore in modo analogo. La finestra di progettazione dovrebbe apparire come questa quando si è pronti per passare al passaggio successivo. Selezionare il pulsante **continua** per procedere:  
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-6.png)   
7. A questo punto è possibile configurare le proprietà per la compilazione che si desidera avviare:    
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-7.png)  
8. Selezionare o immettere il **nome dell'account**, il **nome del progetto**, l'ID della definizione di **compilazione**, il **ramo di origine** e, facoltativamente, i **parametri**nella **coda di una nuova** scheda di compilazione:    
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-8.png)  
9. Configurare quindi le proprietà della notifica push nella scheda **Invia una notifica push** . Per impostazione predefinita, questa notifica push è configurata per l'invio di un collegamento HTML a una pagina Web che visualizza lo stato della compilazione:  
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-9.png)  
10. Selezionare il pulsante **Crea flusso** per salvare il flusso del pulsante: ![immagine panoramica](./media/introduction-to-button-flows/create-button-10.png)  
11. Questo messaggio di esito positivo dovrebbe essere visualizzato entro pochi istanti:  
    ![Immagine panoramica](./media/introduction-to-button-flows/create-button-11.png)  

Congratulazioni, è stato creato un flusso di un pulsante. È ora possibile eseguire il flusso di questo pulsante in qualsiasi momento, dalla scheda **pulsanti** dell'app Microsoft Flow. È sufficiente premere il pulsante che verrà eseguito. L'app per dispositivi mobili Microsoft Flow è disponibile per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Dal dispositivo mobile
**Nota**: mentre in questa procedura dettagliata vengono visualizzate le schermate di un dispositivo Android, le schermate e l'esperienza in un dispositivo iOS sono simili.

Nell'app Microsoft Flow:

1. Selezionare la scheda **Sfoglia** e scorrere fino alla categoria **pulsante** .  
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Selezionare il collegamento **Visualizza tutto** . Verranno visualizzati tutti i modelli di pulsante pronti per l'uso.     
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Selezionare **Invia un messaggio di posta elettronica per ricordare al team di partecipare a un modello di riunione**    
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Selezionare il collegamento **utilizza questo modello** nella parte inferiore della pagina.    
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. È necessario accedere a tutti i servizi usati da questo modello:    
   ![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Dopo aver effettuato l'accesso a tutti i servizi, selezionare il collegamento **successivo** .      
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Selezionare il collegamento **Crea** . Qui è anche possibile esaminare il flusso e apportare le modifiche necessarie per personalizzare il messaggio di posta elettronica, ad esempio.        
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Dopo alcuni istanti, viene creato il flusso del pulsante. Selezionare **vedere il flusso**:   
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Visualizzare tutti i flussi nella scheda **flussi personali**  
   ![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Congratulazioni, è stato creato un flusso di un pulsante. È ora possibile eseguire il flusso di questo pulsante in qualsiasi momento, dalla scheda **pulsanti** dell'app Microsoft Flow. È sufficiente premere il pulsante che verrà eseguito. L'app Microsoft Flow è attualmente disponibile nei dispositivi mobili Android e iOS.  

![Immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Attivare un flusso di un pulsante
Ora che è stato creato il flusso di un pulsante, è possibile eseguirlo. Poiché è possibile eseguire solo i flussi dei pulsanti dall'app Microsoft Flow, assicurarsi di avere installato Flow sul dispositivo mobile Android o iOS.  

1. A questo punto, avviare l'app Flow, toccare la scheda **pulsanti** che si trova nella parte inferiore della pagina e toccare il *pulsante* che rappresenta il flusso del pulsante che si vuole attivare:  
   ![immagine panoramica](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Vedere lo stato di avanzamento durante l'esecuzione del flusso:  
   ![Immagine panoramica](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Infine, la pagina viene aggiornata, a indicare che il flusso del pulsante è stato completato:  
   ![Immagine panoramica](./media/introduction-to-button-flows/trigger-button-3.png)   

Per eseguire un flusso, 

A questo punto si riceverà la notifica push, che indica che il messaggio di posta elettronica è stato inviato.  

## <a name="monitor-your-button-flow-runs"></a>Monitorare le esecuzioni del flusso dei pulsanti
È possibile monitorare i flussi dei pulsanti dalla scheda **attività** dell'app Flow:   
![immagine panoramica](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Nota**: toccare qualsiasi attività per esaminare i risultati dell'esecuzione per informazioni sull'esecuzione.  

![Immagine panoramica](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Gestisci flussi di pulsanti
Si ha il controllo completo sui flussi dei pulsanti in modo da poter abilitare o disabilitare, modificare o eliminare un pulsante in qualsiasi momento, ovunque. Dall'app per dispositivi mobili o dal portale di Flow selezionare **flussi personali** per iniziare a gestire i flussi.    

Nella scheda **flussi personali** dell'app Microsoft Flow:

1. Selezionare il flusso che si desidera gestire:    
   ![Immagine panoramica](./media/introduction-to-button-flows/trigger-button-4.png)   
2. È possibile toccare una qualsiasi di queste opzioni, in base a ciò che si desidera eseguire:    
   ![Immagine panoramica](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Toccare **Delete Flow** per eliminare un flusso.  

**Nota** Tutta la cronologia di esecuzione viene eliminata quando si elimina un flusso:   
![immagine panoramica](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Toccare **Aggiorna** dopo aver completato la modifica del flusso di un pulsante per salvare le modifiche:   
   ![immagine panoramica](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Toccare **cronologia di esecuzione** per visualizzare i risultati di tutte le esecuzioni di un determinato flusso di un pulsante:    
   ![immagine panoramica](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Se si disabilita un flusso, non sarà più disponibile nella scheda **pulsanti** :    
   ![immagine panoramica](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Passaggi successivi
* [Condividere i flussi](share-buttons.md)di un pulsante.
* Informazioni su come usare i [token per attivare i pulsanti](introduction-to-button-trigger-tokens.md) per inviare dati in tempo reale quando vengono eseguiti i flussi dei pulsanti.
* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).

