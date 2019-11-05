---
title: Informazioni su come creare flussi dell'interfaccia utente per siti Web | Microsoft Docs
description: Informazioni su come automatizzare le app Web con i flussi dell'interfaccia utente.
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
ms.openlocfilehash: 010b6632a60f2c81c138fa98d850df79be814f68
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589876"
---
# <a name="create-and-test-your-web-ui-flows"></a>Creare e testare i flussi dell'interfaccia utente Web

[Questo argomento è una versione preliminare della documentazione ed è soggetto a modifiche.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Per creare un semplice flusso dell'interfaccia utente Web, attenersi alla procedura seguente:

## <a name="create-a-web-ui-flow"></a>Creare un flusso dell'interfaccia utente Web

1. Aprire la [versione successiva di Microsoft Edge](https://www.microsoftedgeinsider.com/) o Google Chrome, quindi passare a [Power automatizzate](https://flow.microsoft.com/).

1. Accedi con il tuo account aziendale o dell'istituto di istruzione se necessario.

1. Selezionare **flussi personali** > **flussi dell'interfaccia utente (anteprima)**  > **nuova**.

   ![Crea nuovo flusso dell'interfaccia utente](../media/create-windows-ui-flow/create-new.png "Crea nuovo flusso dell'interfaccia utente")

1. Selezionare l' **app Web** > **Avanti**
    
   ![Selezionare l'app Web](../media/create-web-ui-flow/select-web-app.png "Selezionare l'app Web")

1. Immettere un nome per il flusso dell'interfaccia utente nel campo del **nome del flusso** .

1. Immettere l'URL per il sito Web che si vuole automatizzare nel campo **URL di base** e quindi selezionare **avvia registratore**.

   ![Assegnare un nome e un URL](../media/create-web-ui-flow/give-a-name.png "Assegnare un nome e un URL") 

   Viene avviato il selenio IDE.

   >[!TIP] 
   >Suggerimento: è possibile registrare le azioni tra più siti Web HTTP o HTTPS all'interno della stessa scheda.  

1. In ambiente IDE Selenio selezionare il pulsante rosso **REC** sul lato superiore destro della schermata per avviare il registratore.

   Viene aperto l'URL scelto nel passaggio precedente.

   ![Selezionare REC](../media/create-web-ui-flow/select-rec.png "Selezionare REC")

1.  Eseguire le azioni che si desidera registrare nel sito Web. 
    
    >[!TIP]
    >In basso a destra è possibile visualizzare lo stato della registrazione.

    ![Stato della registrazione](../media/create-web-ui-flow/recording-status.png "Stato della registrazione")

1.  Al termine della registrazione, selezionare il pulsante di **arresto** rosso nell'angolo superiore destro dell'IDE selenio.

    ![Pulsante Arresta](../media/create-web-ui-flow/stop-button.png "Pulsante Arresta" )

1. Selezionare il pulsante **Esegui test corrente** dal lato superiore sinistro della schermata per visualizzare il flusso dell'interfaccia utente appena creato.

    ![Esegui test corrente](../media/create-web-ui-flow/run-test.png "Esegui test corrente")

   >[!TIP]
   >È possibile impostare il tempo di attesa tra i passaggi per rallentare la riproduzione locale per i test. Questa impostazione è solo a scopo di test e non ha alcun effetto quando viene distribuito il flusso dell'interfaccia utente.  
  
1. Selezionare il pulsante **Salva progetto** nella parte superiore destra dell'IDE selenio. Questa operazione chiude e quindi carica il progetto.

Ora che è stato creato un flusso dell'interfaccia utente Web, usarlo in altri flussi.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Limitazioni e problemi noti per i flussi dell'interfaccia utente Web

>[!WARNING]
>**Le password nell'IDE Selenium vengono archiviate in testo normale.**  


**Il flusso dell'interfaccia utente non registra più o riproduce le applicazioni Windows dopo l'installazione di una nuova versione.**

È necessario disinstallare la versione precedente prima di installarne una nuova.

A tale proposito, aprire il menu Start, passare a **impostazioni** > **app**, cercare i **flussi dell'interfaccia utente** nell'elenco di app > **flussi dell'interfaccia utente (anteprima)** e quindi selezionare "Disinstalla". La procedura guidata consente di eseguire il processo.

**Profilo utente temporaneo per la riproduzione**

Le registrazioni dell'IDE Selenio vengono eseguite con il profilo dell'utente corrente, ma la riproduzione viene eseguita usando un profilo utente temporaneo. Ciò significa che i siti Web che richiedono l'autenticazione potrebbero non richiedere le credenziali durante una sessione di registrazione, ma i passaggi di autenticazione saranno necessari durante la riproduzione. 

Per risolvere questo problema, l'utente deve modificare manualmente lo script per inserire i comandi necessari per il processo di accesso.

**Altre limitazioni**

-   Registrazione di applicazioni desktop durante una sessione di registrazione Web. Se è necessario automatizzare applicazioni Web e desktop, è possibile creare flussi dell'interfaccia utente distinti per ogni tipo e quindi combinarli in un flusso.

-   Multi-Factor Authentication (autenticazione a più fattori) non è supportato, usare un tenant che non richiede l'autenticazione a più fattori.

-   Questi comandi dell'IDE selenio non sono supportati: Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, debugger, ClickAt, DoubleClickAt, Echo, mouse out, MouseUpAt e MouseDownAt.

-   Il clic con il pulsante destro del mouse non è supportato. 

-   Quando si usano i comandi foreach, viene generato un ulteriore input del flusso dell'interfaccia utente Web. Per risolvere questo problema, inserire qualsiasi valore nei campi aggiuntivi. Non ha alcun effetto sulla riproduzione.

-   Se il file con estensione side contiene più progetti di test, viene eseguita solo la prima creazione. 

     >[!TIP]
     >Si noti che l'IDE Selenio Ordina i test in base al nome, non alla data di creazione, quindi il primo test creato potrebbe non essere il primo nell'elenco.

-   La riproduzione diretta nell'IDE selenio potrebbe non comportarsi come previsto. Tuttavia, la riproduzione in fase di esecuzione tramite l'infrastruttura del flusso dell'interfaccia utente si comporta correttamente.

## <a name="next-steps"></a>Passaggi successivi

- Informazioni su come [eseguire i flussi dell'interfaccia utente](run-ui-flow.md).

- Se si desidera eseguire altre operazioni con i flussi dell'interfaccia utente, è anche possibile provare i flussi dell'interfaccia utente con parametri di [input e output](inputs-outputs-web.md) .

