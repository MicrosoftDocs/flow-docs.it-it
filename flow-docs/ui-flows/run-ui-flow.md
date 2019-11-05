---
title: Eseguire flussi dell'interfaccia utente da altri flussi | Microsoft Docs
description: Eseguire flussi dell'interfaccia utente da altri flussi
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
ms.openlocfilehash: 275ef331d37ff83d8890b4b6ddd750dc038dd099
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589760"
---
# <a name="run-ui-flows"></a>Esegui flussi dell'interfaccia utente

[Questo argomento è una versione preliminare della documentazione ed è soggetto a modifiche.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Dopo aver creato e testato un flusso dell'interfaccia utente, è possibile eseguirlo da un evento, una pianificazione o un pulsante. Per rendere possibile questa operazione, aggiungere il flusso dell'interfaccia utente a un flusso [automatizzato](../get-started-logic-flow.md), un flusso di un [pulsante](../introduction-to-button-flows.md), un [flusso pianificato](../run-scheduled-tasks.md)o un [flusso del processo di business](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Prerequisiti

- È necessario che il [gateway dati locale](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) per il dispositivo abbia attivato il flusso dell'interfaccia utente da Power automatici.
   
   Il gateway è una connessione sicura di livello aziendale tra l'automazione automatica e il dispositivo (in cui viene eseguito il flusso dell'interfaccia utente). Power automatizzate usa il gateway per accedere al dispositivo locale in modo da poter attivare i flussi dell'interfaccia utente da un evento, una pianificazione o un pulsante.
- Un account aziendale o dell'Istituto di istruzione. 

   >[!IMPORTANT]
   >Per configurare il gateway, è necessario usare lo stesso account aziendale o dell'Istituto di istruzione per l'accesso a Power automatici e per accedere al dispositivo Windows.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Eseguire il flusso dell'interfaccia utente da un evento, un pulsante, una pianificazione o un flusso del processo di business

In questo esempio verrà usato un flusso automatico per attivare un flusso dell'interfaccia utente all'arrivo di un nuovo messaggio di posta elettronica.

1. Passare a [Power automatizzate](https://flow.microsoft.com/).
1. Selezionare **flussi personali** nella barra di spostamento a sinistra.
1. Selezionare **nuovo**e quindi selezionare **automatico-da zero**.

   >[!TIP]
   >È possibile scegliere qualsiasi altro tipo di flusso per soddisfare le proprie esigenze.

1. Assegnare un nome al flusso nella casella **Nome flusso** .
1. Cercare "nuovo messaggio di posta elettronica" e quindi selezionare **quando arriva un nuovo messaggio di posta elettronica (v3)** nell'elenco dei trigger. 
    
   ![Selezionare un trigger](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Selezionare un trigger")

1. Selezionare **Crea**e quindi fare clic su **nuovo passaggio**.

1. Cercare i **flussi dell'interfaccia utente**e quindi selezionare **Esegui un flusso dell'interfaccia utente per il desktop** dall'elenco di **azioni**. 

   ![Azione di ricerca](../media/run-ui-flow/search-action.png "Azione di ricerca")

1. Fornire le informazioni sul gateway e le credenziali del dispositivo. 

   È necessario eseguire questa operazione una volta per ogni dispositivo:

    - **Nome connessione**: scegliere un nome per il dispositivo a cui si desidera eseguire il flusso di connessione. Può essere diverso dal nome del gateway.
    - **Nome utente**: fornire l'account aziendale o dell'Istituto di istruzione del dispositivo.
    - **Tipo di autenticazione**: selezionare Windows.
    - **Password**: la password dell'account aziendale o dell'Istituto di istruzione.
    - **Gateway**: selezionare il gateway creato durante l'installazione.

      ![Impostazioni di connessione](../media/run-ui-flow/connection-settings.png "Impostazioni di connessione")

      >[!TIP]
      >Se il gateway non viene visualizzato, potrebbe essere necessario selezionare una connessione diversa. A tale scopo, selezionare **...** dal lato superiore destro della scheda **Esegui un flusso dell'interfaccia utente per desktop (anteprima)** , quindi selezionare la connessione che si desidera utilizzare dalle **connessioni personali**.

      ![Selezionare una nuova connessione](../media/run-ui-flow/select-new-connection.png "Selezionare una nuova connessione")

1. Selezionare il flusso dell'interfaccia utente creato in precedenza.

   ![Selezionare il flusso dell'interfaccia utente](../media/run-ui-flow/select-ui-flow.png "Selezionare il flusso dell'interfaccia utente")

1. Selezionare **Save (Salva** ) per salvare il flusso automatizzato.

1. Testare il flusso inviando un messaggio di posta elettronica per attivarlo. Si noterà che il flusso dell'interfaccia utente riproduce i passaggi registrati. 

![Esecuzione riuscita che chiama un flusso dell'interfaccia utente](../media/run-ui-flow/successful-run.png "Esecuzione riuscita che chiama un flusso dell'interfaccia utente")

>[!TIP]
>Non interagire con il dispositivo durante l'esecuzione del flusso.

## <a name="use-inputs-and-outputs"></a>Usare input e output

Quando si definiscono input e output all'interno di un flusso dell'interfaccia utente, è possibile passare informazioni da e a tali input.

1. Quando si aggiunge un flusso dell'interfaccia utente a un flusso, è possibile visualizzare l'elenco degli input definiti nel flusso dell'interfaccia utente.

   ![Input flusso dell'interfaccia utente](../media/run-ui-flow/inputs.png "Input flusso dell'interfaccia utente")

1. È possibile popolare ogni campo di input nel flusso dell'interfaccia utente con i valori dei passaggi precedenti nel flusso. A tale scopo, selezionare il campo di input e quindi selezionare un input dal selettore del token.


1. È anche possibile usare gli output del flusso dell'interfaccia utente come input per le azioni visualizzate più avanti nel flusso. A tale scopo, selezionare il campo di input e quindi selezionare un input dal selettore del token.

## <a name="limitations-and-known-issues"></a>Limitazioni e problemi noti

- I cluster di gateway non sono supportati.
- Poiché le tastiere non-US (QWERTY) non sono supportate in questa procedura, la riproduzione di un passaggio di input in cui la sequenza di chiavi è stata registrata da una tastiera non-US (QWERTY) comporterà l'esecuzione di tratti chiave negli Stati Uniti (QWERTY).

## <a name="learn-more"></a>Ulteriori informazioni

 - Installare il [gateway dati locale](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - [Usare la documentazione dell'app gateway dati locale](https://docs.microsoft.com/flow/gateway-manage) .
 - [Risolvere i problemi](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) del gateway dati locale.
