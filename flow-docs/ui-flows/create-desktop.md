---
title: Informazioni su come creare flussi dell'interfaccia utente desktop | Microsoft Docs
description: Informazioni su come creare flussi dell'interfaccia utente desktop per le applicazioni Windows.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e03b23387f5c3837b9b3f7e9ce023f8c31ce79a3
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589793"
---
# <a name="create-and-test-desktop-ui-flows"></a>Creare e testare i flussi dell'interfaccia utente desktop

[Questo argomento è una versione preliminare della documentazione ed è soggetto a modifiche.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]


Creare flussi dell'interfaccia utente desktop per automatizzare le applicazioni desktop di Windows. 

Vedere i [problemi noti](create-desktop.md#known-issues-and-solutions) più avanti in questo argomento per altre informazioni sui problemi che si potrebbero verificare, sulle soluzioni alternative per tali problemi e sugli scenari non supportati in questa versione di anteprima.


> [!TIP]
> È possibile automatizzare altre app desktop di Windows seguendo un modello simile.

## <a name="create-a-desktop-ui-flow"></a>Creare un flusso dell'interfaccia utente desktop

Nei passaggi seguenti verrà illustrato come automatizzare l'app Calculator per sommare due numeri e quindi archiviare il risultato per un uso successivo. 

1. Verificare che il [dispositivo sia pronto](setup.md) per la creazione di flussi dell'interfaccia utente. <!--Todo: link to the prereqs section-->

1. Usare la [versione Chromium di Microsoft Edge](https://www.microsoftedgeinsider.com) o Google Chrome per aprire [Power automatizzate](https://flow.microsoft.com)e quindi accedere con un account di posta elettronica aziendale o dell'Istituto di istruzione.

1. Selezionare **flussi personali** > **flussi dell'interfaccia utente (anteprima)**  > **nuova**.

   ![Crea nuovo flusso dell'interfaccia utente](../media/create-windows-ui-flow/create-new.png "Crea nuovo flusso dell'interfaccia utente")

1. Scegliere **app desktop** e quindi fare clic su **Avanti**.

   ![Seleziona desktop](../media/create-windows-ui-flow/select-desktop.png "Seleziona desktop") 

1. Immettere un nome per il flusso dell'interfaccia utente nel campo **Nome flusso** , quindi fare clic su **Avanti**.

   ![Seleziona desktop](../media/create-windows-ui-flow/give-a-name.png "Seleziona desktop") 

1. Selezionare **Avanti** nella parte inferiore per ignorare la schermata di **impostazione degli input** facoltativi perché in questa procedura dettagliata non vengono usati gli input.

1. Selezionare la scheda **Registra app** per espanderla.

   ![Selezionare Registra app](../media/create-windows-ui-flow/select-record-app.png "Selezionare Registra app")

1. Selezionare **avvia registratore**.

   ![Selezionare avvia registratore](../media/create-windows-ui-flow/select-launch-recorder.png "Selezionare avvia registratore")

   Il controllo registratore viene visualizzato nella parte superiore dello schermo.

   ![Controllo registratore](../media/create-windows-ui-flow/recorder-control.png "Controllo registratore")

1. Avviare l'app Calculator.

     >[!TIP]
     >Quando il mouse passa sopra i controlli nell'app, si noterà che un contorno blu evidenzia ogni controllo. Prima di selezionare un controllo, attendere sempre l'evidenziazione blu.
     >
     >Se l'evidenziazione blu non viene visualizzata intorno all'elemento, è possibile che non sia registrata correttamente.

1. Selezionare **record** dal controllo registratore.
1. Selezionare il primo numero, selezionare **+** , selezionare il secondo numero e quindi selezionare **=** .

    ![App Calculator](../media/create-windows-ui-flow/app-to-record.png "App Calculator")

1. Selezionare **fatto** sul controllo registratore dopo aver completato le azioni che si desidera registrare.

1. Chiudere l'app registrata.

1. Selezionare la scheda che inizia con "Esegui <app name> script" per visualizzare gli screenshot dei passaggi registrati.

     >[!TIP]
     >Selezionare **...**  > **Elimina** per rimuovere eventuali passaggi aggiuntivi che si desidera rimuovere.

    ![Mostra i passaggi registrati](../media/create-windows-ui-flow/show-recorded-steps.png "Mostra i passaggi registrati")

1. Selezionare **Avanti**. 

1. Fare clic su **Avanti** per ignorare il passaggio facoltativo **Imposta output** perché non vengono usati output in questa procedura dettagliata.

## <a name="test-your-ui-flow"></a>Testare il flusso dell'interfaccia utente

È sempre un'ottima idea testare il flusso dell'interfaccia utente. A tale scopo, selezionare il pulsante **test adesso** , quindi controllare l'esecuzione del flusso dell'interfaccia utente.
    
 >[!IMPORTANT]
 >Per ottenere risultati ottimali, non interagire con il dispositivo per la durata della riproduzione.

1. Selezionare **Salva e Chiudi** per salvare il flusso e chiudere la funzionalità flussi dell'interfaccia utente.


## <a name="known-issues-and-solutions"></a>Problemi noti e soluzioni

- Aprire e ingrandire le app *che si vuole registrare prima di* iniziare la registrazione.

- Potrebbe essere necessario aggiungere un'azione di [ **chiusura** ](edit-desktop.md#add-a-manual-action) alla fine del flusso dell'interfaccia utente perché i flussi dell'interfaccia utente avviano una nuova istanza delle applicazioni a ogni test o esecuzione.

- Selezionare **...**  > **Elimina** nella scheda azioni registrate per rimuovere eventuali azioni non necessarie o duplicate. È possibile creare azioni duplicate a seconda del tipo e della velocità di registrazione. 

- I clic destro potrebbero non essere riprodotti correttamente. In tal caso, durante la registrazione fare clic su a sinistra per concentrare l'interfaccia utente sui flussi dell'interfaccia utente di destinazione, quindi fare clic con il pulsante destro del mouse.

- Se l'interfaccia utente non registra più o riproduce le applicazioni Windows dopo l'installazione di una nuova versione, disinstallare la versione precedente e quindi installare una nuova versione.


### <a name="unsupported-application-types"></a>Tipi di applicazioni non supportati

-   Interazioni in Windows (Esplora file, menu di avvio, barra delle applicazioni e così via).

-   Web browser (Chrome, IE, Edge, cromo perimetrale, Firefox, Mozilla e così via).
    Per automatizzare i siti Web, vedere invece [creare un flusso dell'interfaccia utente Web](edit-web.md) .

-   Applicazioni Java.

-   Fare clic su once Applications.

-   Applicazioni con una visualizzazione Web, ad esempio applicazioni Electron.

-   Microsoft Office 2016 e versioni precedenti. 

-   Microsoft Office Online.

### <a name="unsupported-configurations"></a>Configurazioni non supportate

-   Più schermate.

-   Registrazione tramite un client di macchina virtuale (Desktop remoto, Citrix e così via), con l'app flussi dell'interfaccia utente in esecuzione nel dispositivo host o nella macchina virtuale. Nessuno è supportato.

-   Più istanze di un'applicazione in cui i titoli delle finestre principali sono identici.

-   Le finestre dell'applicazione con titoli identici, ad esempio, Microsoft Outlook con più finestre di posta elettronica non **intitolate-Message (HTML)** attive nello stesso momento.

-   Sessioni di registrazione simultanee in un determinato dispositivo.

-   Sessioni di riproduzione simultanee in un determinato dispositivo. In caso di esecuzioni simultanee del flusso dell'interfaccia utente, il primo ha la precedenza e le successive avranno esito negativo fino al completamento della prima.

-   Riproduzione in un dispositivo con un layout di tastiera diverso rispetto al dispositivo in cui è stato registrato.

-   Registrazione in un dispositivo o in una sessione di Windows mentre il browser con Microsoft Flow si trova in un dispositivo diverso o in una sessione di Windows.

### <a name="unsupported-action-types-and-behaviors"></a>Tipi di azione e comportamenti non supportati

Le azioni seguenti non verranno registrate:

-   Fare doppio clic su.

-   Spostamento del mouse.

-   Passaggio del mouse.

-   Fare clic e trascinare.

-   Input tocco o penna.

-   Aprire l'app prima della registrazione.

-   App chiusa prima dell'avvio della riproduzione.

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Comportamenti inaffidabili e soluzioni alternative per Microsoft Office (desktop)
- Aggiungere la barra multifunzione prima di iniziare la riproduzione per evitare problemi che possono verificarsi se la barra multifunzione è impostata su Nascondi automaticamente durante la riproduzione.
- Non selezionare elementi facendo clic e trascinando. Ad esempio, non usare Maiusc + clic per selezionare le celle in Microsoft Excel e non selezionare testo in Microsoft Word o Microsoft PowerPoint trascinando il mouse.
- Alcuni elementi potrebbero non funzionare correttamente nei flussi dell'interfaccia utente (anteprima) per le applicazioni desktop di Microsoft Word e Microsoft PowerPoint. Ad esempio, le opzioni nel menu file, ad esempio a partire da BLANK, o facendo clic con il pulsante destro del mouse su controlli come l'aggiunta di un paragrafo in Microsoft Word o la modifica del layout delle diapositive in Microsoft PowerPoint potrebbero non funzionare.

## <a name="next-steps"></a>Passaggi successivi

- Informazioni su come [attivare il flusso dell'interfaccia utente](run-ui-flow.md) appena creato.

- Se si desidera eseguire altre operazioni con i flussi dell'interfaccia utente, è anche possibile provare i flussi dell'interfaccia utente con parametri di [input e output](inputs-outputs-web.md) .

