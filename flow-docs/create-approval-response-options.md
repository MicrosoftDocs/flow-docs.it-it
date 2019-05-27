---
title: Creare flussi di approvazione con risposte personalizzate | Microsoft Docs
description: Creare flussi di approvazione con risposte personalizzate
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
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: d1f4b6d6dad3138bf935947076be4fe75661e36e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061711"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Creare opzioni di risposta personalizzate per i flussi di approvazione

Si supponga di voler inviare una richiesta di approvazione ogni volta che un dipendente carica una nota spese in SharePoint e quindi consentire al responsabile approvazione di rispondere con una di queste tre opzioni: Accept (Accetta), Need more info (Richiesta di maggiori informazioni) o Reject (Rifiuta).


## <a name="prerequisites"></a>Prerequisiti

- Un account Microsoft Flow con una licenza Piano 2 (Piano 2 è necessario per usare le funzionalità Premium. Approvazioni è una funzionalità Premium).
- Un elenco di SharePoint per i dipendenti per immettere le note spese.

## <a name="create-approval-flow"></a>Creare un flusso di approvazione
1. Eseguire l'accesso a [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare **Flussi personali** nella barra di spostamento a sinistra.
1. Selezionare **Nuovo** > **Crea da zero**.

    ![Opzione Crea da zero](media/create-approval-response-options/create-approval-response-options.png)

1. Nella schermata che si apre selezionare **Crea da zero**. 

    ![Selezionare Crea da zero](media/create-approval-response-options/create-from-blank.png)

1. Cercare **sharepoint** e quindi selezionare **Quando viene creato un elemento** dall'elenco dei trigger. 

1. Specificare l'**Indirizzo del sito** e il **Nome lista** di SharePoint. 

1. Selezionare **Nuovo passaggio**, cercare **Approvazioni** e quindi selezionare **Avvio e attesa per l'approvazione (V2)**.

1. Nella scheda **Avvio e attesa per l'approvazione (V2)** selezionare l'elenco **Tipo di approvazione**.

    ![Tipo di approvazione](media/create-approval-response-options/select-approval-type.png)

1. Selezionare **Risposte personalizzate - Attendere una risposta (Premium)**.

    ![Risposte personalizzate](media/create-approval-response-options/select-custom-responses.png)

    Verranno quindi create le risposte personalizzate che i responsabili approvazione useranno quando rispondono a una richiesta di approvazione per la nota spese di un dipendente.


1. Nella casella **Opzioni di risposta Elemento - 1** immettere **Accept** (Accetta) e quindi selezionare **Aggiungi nuovo elemento**. 

    ![Risposta personalizzata 1](media/create-approval-response-options/enter-response-1.png)

1. Nella casella **Opzioni di risposta Elemento - 2** immettere **Reject** (Rifiuta) e quindi selezionare **Aggiungi nuovo elemento**.

    ![Risposta personalizzata 2](media/create-approval-response-options/enter-response-2.png)

1. Nella casella **Opzioni di risposta Elemento - 3** immettere **Need more info** (Richiesta di maggiori informazioni).

    ![Risposta personalizzata 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Immettere le informazioni richieste per **Titolo**, **Assegnata a** (indirizzo e-mail del responsabile approvazione) e **Dettagli** (dettagli da inserire nella richiesta di approvazione).

    Ecco un esempio di quello che si può includere per l'organizzazione.

    ![Dettagli delle risposte personalizzate](media/create-approval-response-options/enter-title-assigned-to-details.png)


Ora che sono state create le risposte personalizzate, è possibile eseguire operazioni diverse nel flusso, a seconda della risposta del responsabile approvazione.


## <a name="use-approval-responses"></a>Usare le risposte di approvazione 

Se la risposta alla richiesta è **Accept** (Accetta), si potrebbe voler inviare un messaggio e-mail al reparto contabilità per chiedere il rimborso delle spese per il dipendente. 

Se la risposta è **Reject** (Rifiuta), si potrebbe voler inviare un messaggio e-mail al dipendente per informarlo che la richiesta è stata rifiutata.

Se infine la risposta del responsabile approvazione è **Need more info** (Richiesta di maggiori informazioni), si potrebbe voler inviare un messaggio e-mail al dipendente per chiedere di fornire altre informazioni.

Per eseguire una di queste operazioni nel flusso, aggiungere una [**Condizione**](add-condition.md) o un'azione **Switch** al flusso e quindi selezionare il campo **Risultato** della richiesta di approvazione dalla selezione del contenuto dinamico. Assicurarsi di confermare se il valore è Accept (Accetta), Need more info (Richiesta di maggiori informazioni) o Reject (Rifiuta).

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Rispondere alle richieste di approvazione con una risposta personalizzata

I responsabili approvazione ricevono le richieste di approvazione tramite e-mail. Le richieste vengono visualizzate anche nel Centro approvazioni in Microsoft Flow. 

![Messaggio e-mail con una richiesta di approvazione](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Altre informazioni
- Creare [flussi di approvazioni singole](modern-approvals.md)
- Creare [flussi di approvazione sequenziali](sequential-modern-approvals.md)
