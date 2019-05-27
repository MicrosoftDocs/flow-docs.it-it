---
title: Avviare i flussi con i pulsanti Flic | Microsoft Docs
description: Avviare facilmente i flussi dei pulsanti con i pulsanti fisici Flic di Shortcut Labs.
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
ms.openlocfilehash: bbcb6c8950e8ac5959880727604e0355b3150c6f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64455629"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Eseguire i flussi premendo uno smart button Flic (anteprima)
Attivare i flussi premendo un pulsante fisico, noto come Flic, di Shortcut Labs. Ad esempio, premere un pulsante Flic per tenere traccia delle ore lavorative, bloccare il calendario, conteggiare i visitatori di un evento o salvare le posizioni geografiche.

> [!IMPORTANT]
> Configurare tutte le proprietà di Flic usando le app Flic per dispositivi mobili per [Android](https://play.google.com/store/apps/details?id=io.flic.app) o [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) prima di creare il flusso.
> 
> 

## <a name="prerequisites"></a>Prerequisiti
Per usare i pulsanti Flic con Microsoft Flow, è necessario:

* Avere accesso a [Microsoft Flow](https://flow.microsoft.com).
* Aver scaricato l'app Flic per dispositivi mobili per [Android](https://play.google.com/store/apps/details?id=io.flic.app) o [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) e quindi averla usata per associare uno o più pulsanti Flic.

## <a name="configure-flic-properties"></a>Configurare le proprietà di Flic
Usare l'app Flic per dispositivi mobili per programmare gli eventi di Flic. Gli eventi sono:

* clic (una pressione rapida)
* doppio clic (due pressioni rapide)
* pressione prolungata

Questa schermata mostra un possibile esempio del processo di configurazione di Flic:

![configurare Flic](./media/flic-button-flows/configure-flic-actions.png)

Dopo aver collegato un evento Flic a Microsoft Flow, è quindi possibile selezionare tale pulsante Flic come trigger per i flussi. I trigger verranno selezionati più avanti in questa procedura dettagliata.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Creare un flusso che viene attivato da un pulsante Flic
In questa procedura dettagliata, verrà usato un pulsante Flic per eseguire un flusso che registra il tempo impiegato da un consulente presso ogni cliente. Il consulente preme il pulsante Flic una sola volta all'arrivo, premendolo di nuovo poco prima di andar via. Ciascuna pressione del pulsante Flic avvia un'esecuzione del flusso a cui è connesso. Il flusso salva l'ora corrente in un foglio Google e quindi invia una notifica di posta elettronica. Il messaggio contiene i dettagli sull'esecuzione del flusso.

Nota: Assicurarsi di aver usato l'app per dispositivi mobili Flic-to-pair e configurare almeno un **fare clic su** azione per attivare Microsoft Flow. In questa schermata, è stata configurata l'azione di **clic** in modo da attivare Microsoft Flow. Più avanti in questa procedura dettagliata verrà configurata l'attivazione del flusso quando si preme il pulsante Flic una sola volta (cioè si fa clic su di esso).

   ![configurazione flic](./media/flic-button-flows/flic-configured-for-flow.png)

Iniziamo a creare il flusso.

### <a name="start-with-a-template"></a>Iniziare con un modello
1. Accedere a [Microsoft Flow](https://flow.microsoft.com).
   
    ![accedere](./media/flic-button-flows/sign-into-flow.png)
2. Immettere **flic** nella casella di ricerca, quindi selezionare l'icona di ricerca.
   
    ![cercare flic](./media/flic-button-flows/search-flic.png)
3. Selezionare il modello **Track your working hours with Flic smart button** (Tieni traccia delle ore lavorative con lo smart button Flic).
   
    ![selezionare il modello](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Creare un foglio di calcolo in Fogli Google
1. Esaminando i dettagli del modello si noterà che richiede un foglio di calcolo in Fogli Google.
   
   ![esaminare i dettagli del modello](./media/flic-button-flows/flic-template-details.png)
2. In Fogli Google, creare un foglio di calcolo che contenga un foglio con colonne denominate **ClickType** e **TimeStamp**.
   
      Suggerimento: Assegnare un nome le colonne in fogli Google immettendo il nome della colonna nella parte superiore della colonna. In questo modo, il foglio sarà simile a questa schermata:
   
   ![Foglio di Google](./media/flic-button-flows/flic-google-sheet.png)
   
   Nota: Questo foglio verrà usato più avanti in questa procedura dettagliata.

### <a name="add-the-flic-trigger-to-your-flow"></a>Aggiungere il trigger Flic al flusso
1. Accedere ai servizi del modello e quindi selezionare **Continua**.
   
     L'opzione **Continua** viene abilitata dopo aver eseguito l'accesso a tutti i servizi necessari per il modello.
   
    ![fornire le credenziali](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Immettere **flic** nella casella di ricerca, quindi selezionare il trigger **Flic - When a Flic is pressed** (Flic - Quando viene premuto un Flic).
   
    ![cercare il trigger di flic](./media/flic-button-flows/flic-search-trigger.png)
3. Selezionare il pulsante Flic che si vuole usare dall'elenco **Flic button** nella scheda **Flic - When a Flic is pressed**.
4. Selezionare **click** dall'elenco **Events** per indicare che si vuole attivare il flusso quando si preme il pulsante Flic una sola volta.
   
    ![selezionare azione flic](./media/flic-button-flows/select-flic.png)
   
   Facoltativamente, è possibile selezionare **any** per indicare che ogni evento Flic (clic, doppio clic o pressione prolungata) attiva il flusso.
   
   **Double-click** indica che il flusso viene attivato quando il pulsante Flic viene premuto rapidamente due volte. **Hold** indica che una pressione prolungata sul pulsante Flic attiva il flusso.
   
   È possibile creare altri flussi e attivarli usando altri eventi nell'elenco **Events**. Ad esempio, è possibile usare l'evento **double-click** per registrare l'ora in cui si esce dalla sede del cliente.

### <a name="configure-the-sheet"></a>Configurare il foglio
   Nella scheda **Inserisci riga**:

1. Selezionare il foglio di calcolo creato in precedenza dall'elenco **File**.
2. Selezionare il foglio dall'elenco **Foglio di lavoro**.
   
   Nota: Vengono visualizzate due caselle aggiuntive nella **Inserisci riga** dopo aver selezionato il foglio. che rappresentano le due colonne nel foglio creato in precedenza.
3. Selezionare la casella **ClickType** e quindi selezionare il token **Click type**.
4. Selezionare la casella **Timestamp** e quindi selezionare il token **Click time**.
   
    ![configurare dati Fogli Google](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Verificare la correttezza delle impostazioni di posta elettronica
1. Verificare che la scheda **Invia una notifica di posta elettronica** abbia lo stesso aspetto di questa schermata.
   
    ![confermare notifica di posta elettronica](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Salvare il flusso e testarlo
1. Assegnare un nome al flusso e quindi salvarlo.
   
    ![salvare il flusso](./media/flic-button-flows/save.png)

Se tutti i passaggi sono stati eseguiti correttamente, una sola pressione del pulsante Flic attiva il flusso. Il flusso registra quindi il tipo di clic e l'ora corrente nel foglio e quindi invia un messaggio di posta elettronica all'utente.

1. Premere il pulsante Flic una sola volta.
2. Aprire un foglio di lavoro in Fogli Google. Le colonne **ClickType** e **Timestamp** dovrebbero essere popolate rispettivamente con il tipo di clic e con l'ora.
   
    ![vedere i risultati dell'esecuzione](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. È anche possibile visualizzare i risultati dell'esecuzione dal sito Web di Microsoft Flow o dall'app Microsoft Flow per dispositivi mobili. Di seguito viene mostrata una schermata dell'esecuzione dei test.
   
    ![salvare il flusso](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Ecco come appare il corpo del messaggio di posta elettronica di notifica ricevuto dall'esecuzione del flusso.
   
    ![salvare il flusso](./media/flic-button-flows/flic-email-body.png)

Per risultati ottimali, provare a estendere il flusso in modo da registrare automaticamente la propria posizione (latitudine e longitudine) quando si preme il pulsante Flic.

## <a name="more-information"></a>Altre informazioni
* [Condividere i flussi dei pulsanti](share-buttons.md).
* Informazioni su come usare i [token per attivare i pulsanti](introduction-to-button-trigger-tokens.md) per inviare dati correnti quando vengono eseguiti i flussi dei pulsanti.
* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

