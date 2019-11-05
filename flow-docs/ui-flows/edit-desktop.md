---
title: Informazioni su come modificare i flussi dell'interfaccia utente desktop | Microsoft Docs
description: Informazioni su come modificare i flussi dell'interfaccia utente desktop.
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
ms.openlocfilehash: d5b7e186ae5c644f00f57946fff5ef3e946ba2ba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589824"
---
# <a name="edit-desktop-ui-flows"></a>Modificare i flussi dell'interfaccia utente desktop

[Questo argomento è una versione preliminare della documentazione ed è soggetto a modifiche.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

I flussi dell'interfaccia utente desktop automatizzano le applicazioni desktop di Windows. Per ulteriori informazioni sui problemi che si potrebbero verificare, le soluzioni alternative per tali problemi e gli scenari non supportati in questa versione di anteprima, vedere i [problemi noti](create-desktop.md#known-issues-and-solutions) .

## <a name="prerequisites"></a>Prerequisiti
Flusso dell'interfaccia utente desktop. [Creare un flusso dell'interfaccia utente desktop ora](create-desktop.md#create-and-test-desktop-ui-flows) se non si ha una modifica.

## <a name="edit-actions"></a>Modifica azioni

![Modifica azioni](../media/edit-desktop/edit-actions.png "Modifica azioni")

È possibile modificare la registrazione in:

-   Modificare il valore per le azioni che la supportano.
-   Eliminare un passaggio.
-   Eliminare l'intera registrazione.
-   Modificare l'ordine delle azioni con trascinamento della selezione. Prestare attenzione a questo perché potrebbe interrompere la coerenza della registrazione.

I parametri avanzati consentono di modificare:

-  Ritardo dopo l'esecuzione dell'azione. Ad esempio, è possibile aggiungere un ritardo di un secondo modificando PT0S in PT1S. Questa operazione può essere utile quando l'applicazione di destinazione ha un tempo di risposta lento che non viene completata prima del passaggio successivo del flusso dell'interfaccia utente.
-   [Selettore](edit-desktop.md#set-the-selector) per l'elemento dell'interfaccia utente di destinazione.

## <a name="add-a-recording"></a>Aggiungere una registrazione

Potrebbe essere necessario registrare il flusso dell'interfaccia utente in più sessioni. Dopo aver completato la prima registrazione, è possibile procedere come segue:

1. Accedere a [Power automatizzate](https://flow.microsoft.com).
1. Selezionare **flussi personali** > **flussi dell'interfaccia utente (anteprima)** .
1. Selezionare il flusso dell'interfaccia utente che si desidera modificare.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selezionare **modifica**. 
1. Selezionare **nuovo passaggio**.

   ![Nuovo passaggio](../media/edit-desktop/new-step.png "Nuovo passaggio")

1. Selezionare **Registra app** dall'elenco di azioni.

   ![Registra app](../media/edit-desktop/select-record-ui-actions.png "Registra app")

1. Selezionare **avvia registratore**.

   ![Selezionare avvia registratore](../media/create-windows-ui-flow/select-launch-recorder.png "Selezionare avvia registratore")

   Il controllo registratore viene visualizzato nella parte superiore dello schermo.

   ![Controllo registratore](../media/create-windows-ui-flow/recorder-control.png "Controllo registratore")

1. Avviare l'app che si vuole registrare.

     >[!TIP]
     >Quando il mouse passa sopra i controlli nell'app, si noterà che un contorno blu evidenzia ogni controllo. Prima di selezionare un controllo, attendere sempre l'evidenziazione blu.
     >
     >Se l'evidenziazione blu non viene visualizzata intorno all'elemento, è possibile che non sia registrata correttamente.

1. Selezionare **record** dal controllo registratore.

1. Eseguire i passaggi nell'interfaccia utente dell'app che si sta registrando e quindi selezionare **done** nel controllo registratore.
1. Selezionare **Save (Salva**) e quindi testare il flusso dell'interfaccia utente.

## <a name="add-a-manual-action"></a>Aggiungere un'azione manuale

Dopo aver registrato un'applicazione con almeno un'azione, è possibile aggiungere manualmente una delle azioni seguenti per l'applicazione.

| **Azione**          | **Commento**                                                       |
|---------------------|-------------------------------------------------------------------|
| Chiudi applicazione   |                                                                   |
| Clic con il pulsante destro del mouse         |                                                                   |
| Chiavi di invio           | Chiavi di invio e combinazioni di chiavi, ad esempio CTRL + C.                             |
| Clic con pulsante sinistro          |                                                                   |
| Ottieni testo            | Leggere il testo da un elemento dell'interfaccia utente e quindi usarlo come output. |
| Immettere il testo          |                                                                   |
| Elemento Get abilitato | Controllare se un elemento dell'interfaccia utente è abilitato o disabilitato.         |
| Elemento clear       | Cancellare il valore in un elemento dell'interfaccia utente modificabile.             |
| Attendi secondi    | Attendere prima di continuare con il passaggio successivo.                           |

Per aggiungere un'azione manuale, attenersi alla procedura seguente:

1. Accedere a [Power automatizzate](https://flow.microsoft.com).
1. Selezionare **flussi personali** > **flussi dell'interfaccia utente (anteprima)** .
1. Selezionare il flusso dell'interfaccia utente che si desidera modificare.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selezionare **modifica**. 
1. Selezionare la scheda di registrazione che contiene i passaggi a cui si desidera aggiungere un nuovo passaggio.
   La scheda si espande e Visualizza i passaggi registrati.

   ![Seleziona scheda di registrazione](../media/edit-desktop/manual-select-recording-card.png)

1. Selezionare **Aggiungi un'azione** nella scheda di registrazione, subito dopo l'ultimo passaggio registrato.
   Verrà visualizzato l'elenco delle azioni manuali elencate in precedenza nella procedura dettagliata. 

1. Selezionare l'azione che si desidera aggiungere. Qui è stata selezionata l'opzione **Get element Enabled**, ma è possibile selezionare qualsiasi azione che abbia senso per lo scenario.

   ![Selezionare l'azione per aggiungere. png](../media/edit-desktop/select-action-to-add.png)

Una volta aggiunta l'azione, sarà necessario impostare il **selettore** nelle opzioni avanzate dell'azione.

![Opzioni avanzate azione](../media/edit-desktop/action-advanced-options.png "Opzioni avanzate azione")

### <a name="set-the-selector"></a>Imposta il selettore

Il selettore identifica l'elemento dell'interfaccia utente sul quale viene eseguita l'azione durante la riproduzione. Si consiglia di copiare e incollare queste informazioni da un passaggio separato destinato allo stesso elemento dell'interfaccia utente, se possibile.

Il formato del selettore è:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

È necessario fornire i dati per i campi **elemementStack** e **elementXPath** dell'elemento selector.

Di seguito è riportato un esempio di come potrebbe apparire **elemementStack** .

![Stack di elementi](../media/edit-desktop/elementstack.png "Stack di elementi")

È possibile acquisire il **elementXPath** usando il [registratore dell'interfaccia utente di WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Strumento WAD](../media/edit-desktop/wad-tool.png "Strumento WAD")

Rimuovere il primo elemento (tutti gli elementi prima di/Window) prima di usare il risultato in **elementXPath** del selettore.

Testare il flusso dell'interfaccia utente per verificare che il selettore funzioni correttamente.

## <a name="next-steps"></a>Passaggi successivi

- Informazioni su come [eseguire il flusso dell'interfaccia utente](run-ui-flow.md) appena modificato.

- Se si desidera eseguire altre operazioni con i flussi dell'interfaccia utente, è anche possibile provare i flussi dell'interfaccia utente con parametri di [input e output](inputs-outputs-web.md) .

