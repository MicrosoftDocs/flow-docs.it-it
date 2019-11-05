---
title: Avviare i flussi con i pulsanti Flic | Microsoft Docs
description: È possibile avviare facilmente i flussi dei pulsanti con i pulsanti fisici da Flic per i Lab di collegamento.
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
ms.date: 05/19/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e6430f78ad2eccecc5af7f6606bb56e1a7eb4599
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544800"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Eseguire i flussi premendo un pulsante Smart Flic (anteprima)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Attivare i flussi premendo un pulsante fisico, noto come Flic, da Shortcut Labs. Ad esempio, premere un Flic per tenere traccia delle ore lavorative, bloccare il calendario, contare i visitatori a un evento o salvare le località geografiche.

> [!IMPORTANT]
> Configurare tutte le proprietà Flic usando l'app per dispositivi mobili di Flic per [Android](https://play.google.com/store/apps/details?id=io.flic.app) o [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) prima di creare il flusso.
> 
> 

## <a name="prerequisites"></a>Prerequisiti
Per usare flics con Microsoft Flow, è necessario disporre di:

* Accesso a [Microsoft Flow](https://flow.microsoft.com).
* È stata scaricata l'app per dispositivi mobili [Android](https://play.google.com/store/apps/details?id=io.flic.app) o [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) di Flic, che è stata usata per associare uno o più Flic.

## <a name="configure-flic-properties"></a>Configurare le proprietà di Flic
Usare l'app per dispositivi mobili di Flic per programmare gli eventi di Flic. Gli eventi sono:

* clic (una pressione rapida)
* doppio clic (due presse rapide)
* tenere premuto (premere uno lungo)

Questo screenshot mostra un esempio di come potrebbe essere il processo di configurazione di Flic:

![configurare flics](./media/flic-button-flows/configure-flic-actions.png)

Dopo aver collegato un evento Flic a Microsoft Flow, è possibile selezionare Flic come trigger per i flussi. I trigger vengono selezionati più avanti in questa procedura dettagliata.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Creare un flusso che viene attivato da un Flic
In questa procedura dettagliata viene usato un Flic per eseguire un flusso che registra il tempo impiegato da un consulente in ogni client. Il consulente preme il Flic una volta all'arrivo e quindi lo preme nuovamente, immediatamente prima della partenza dal client. Ogni pressione di Flic avvia un'esecuzione del flusso a cui è connessa. Il flusso Salva l'ora corrente nei fogli Google e invia una notifica tramite posta elettronica. Il messaggio di posta elettronica contiene i dettagli sull'esecuzione del flusso.

Nota: assicurarsi di aver usato l'app Flic per dispositivi mobili per la coppia e configurare almeno un'azione di **clic** per attivare Microsoft Flow. In questa schermata, ho configurato l'azione **Click** per attivare Microsoft Flow. Più avanti in questa procedura dettagliata verrà configurato il flusso per l'attivazione quando il Flic viene premuto una volta (clic).

   ![configurazione Flic](./media/flic-button-flows/flic-configured-for-flow.png)

Si inizia a creare il flusso.

### <a name="start-with-a-template"></a>Iniziare con un modello
1. Accedere [Microsoft Flow](https://flow.microsoft.com).
   
    ![Accedi](./media/flic-button-flows/sign-into-flow.png)
2. Immettere **Flic** nella casella di ricerca e quindi selezionare l'icona di ricerca.
   
    ![Cerca Flic](./media/flic-button-flows/search-flic.png)
3. Selezionare il modello **Tieni traccia delle ore di lavoro con il pulsante Smart Flic** .
   
    ![Seleziona modello](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Creare un foglio di calcolo in fogli Google
1. Esaminare i dettagli del modello. si noti che questo modello richiede un foglio di calcolo in fogli Google.
   
   ![esaminare i dettagli del modello](./media/flic-button-flows/flic-template-details.png)
2. In fogli Google creare un foglio di calcolo contenente un foglio con le colonne denominate **ClickType** e **timestamp**.
   
      Suggerimento: per assegnare un nome alle colonne in fogli Google, immettere il nome della colonna nella parte superiore della colonna. Quindi, il foglio dovrebbe apparire come lo screenshot seguente:
   
   ![Foglio Google](./media/flic-button-flows/flic-google-sheet.png)
   
   Nota: questo foglio verrà usato più avanti in questa procedura dettagliata.

### <a name="add-the-flic-trigger-to-your-flow"></a>Aggiungere il trigger Flic al flusso
1. Accedere ai servizi del modello e quindi selezionare **continue (continua**).
   
     **Continua** è abilitato dopo l'accesso a tutti i servizi necessari per il modello.
   
    ![fornire le credenziali](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Immettere **Flic** nella casella di ricerca e quindi selezionare il trigger **Flic-when a Flic is pressed** .
   
    ![Cerca trigger Flic](./media/flic-button-flows/flic-search-trigger.png)
3. Selezionare il Flic che si vuole usare dall'elenco dei **pulsanti Flic** nella scheda **Flic-when a Flic is pressed** .
4. Selezionare **fare clic** nell'elenco **eventi** per indicare che si vuole attivare il flusso quando il Flic viene premuto una volta.
   
    ![Selezionare l'azione Flic](./media/flic-button-flows/select-flic.png)
   
   Facoltativamente, è possibile selezionare **any** per indicare che ogni evento Flic (clic, doppio clic o in attesa) attiva il flusso.
   
   **Doppio clic** indica che il flusso viene attivato quando il Flic viene premuto rapidamente due volte. **Tenere premuto** indica che una pressione propagata sul Flic attiva il flusso.
   
   È possibile creare altri flussi e attivarli usando gli altri eventi nell'elenco **degli eventi** . Ad esempio, è possibile utilizzare l'evento **doppio clic** per registrare l'ora in cui si lascia un client.

### <a name="configure-the-sheet"></a>Configurare il foglio
   Nella scheda **Inserisci riga** :

1. Selezionare il foglio di calcolo creato in precedenza dall'elenco **file** .
2. Selezionare il foglio dall'elenco dei **fogli** di dati.
   
   Nota: dopo aver selezionato il foglio, nella scheda **Inserisci riga** vengono visualizzate due caselle aggiuntive. Queste caselle rappresentano le due colonne nel foglio creato in precedenza.
3. Selezionare la casella **ClickType** , quindi selezionare il token di **tipo fare clic su** .
4. Selezionare la casella **timestamp** , quindi selezionare il token **Click time** .
   
    ![configurare i dati dei fogli Google](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Verificare che le impostazioni di posta elettronica siano corrette
1. Verificare che la scheda **Invia una notifica di posta elettronica abbia un** aspetto simile a questa schermata.
   
    ![conferma notifica posta elettronica](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Salvare il flusso e testarlo
1. Assegnare un nome al flusso e quindi salvarlo.
   
    ![salvare il flusso](./media/flic-button-flows/save.png)

Se è stata eseguita la continuazione, premendo il pulsante Flic una volta attiva il flusso. Il flusso registra quindi il tipo di clic e l'ora corrente nel foglio, quindi Invia un messaggio di posta elettronica all'utente.

1. Premere il Flic una sola volta.
2. Aprire il foglio di lavoro in fogli Google. Verranno visualizzate le colonne **ClickType** e **timestamp** popolate rispettivamente con "click" e con l'ora.
   
    ![Vedi risultati esecuzione](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. È anche possibile visualizzare i risultati dell'esecuzione dal sito Web Microsoft Flow o dall'app Microsoft Flow per dispositivi mobili. Ecco una schermata dell'esecuzione dei test.
   
    ![salvare il flusso](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Ecco il corpo del messaggio di posta elettronica di notifica ricevuto dall'esecuzione del flusso.
   
    ![salvare il flusso](./media/flic-button-flows/flic-email-body.png)

Per un credito aggiuntivo, provare a estendere il flusso per registrare automaticamente il percorso (Latitudine e longitudine) quando si preme il Flic.

## <a name="more-information"></a>Ulteriori informazioni
* [Condividere i flussi](share-buttons.md)di un pulsante.
* Informazioni su come usare i [token per attivare i pulsanti](introduction-to-button-trigger-tokens.md) per inviare dati correnti quando vengono eseguiti i flussi dei pulsanti.
* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).

