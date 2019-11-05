---
title: Creare flussi di approvazione con risposte personalizzate | Microsoft Docs
description: Creare flussi di approvazione con risposte personalizzate.
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
ms.openlocfilehash: eaaa87f9213c5ed04aee65e37ee642436e49dfca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547216"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Creare opzioni di risposta personalizzate per i flussi di approvazione
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Si vuole inviare una richiesta di approvazione ogni volta che un dipendente carica una nota spese in SharePoint e quindi consente al responsabile approvazione di rispondere con una delle tre opzioni seguenti: Accept, Need more info o Reject.


## <a name="prerequisites"></a>Prerequisiti

- Un account Microsoft Flow.
- Elenco di SharePoint che consente ai dipendenti di immettere le note spese.

## <a name="create-approval-flow"></a>Crea flusso di approvazione
1. Accedere a [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare **flussi personali** nella barra di spostamento a sinistra.
1. Selezionare **nuovo** > **Crea da zero**.

    ![Crea da opzione vuota](media/create-approval-response-options/create-approval-response-options.png)

1. Nella schermata visualizzata selezionare **Crea da zero**. 

    ![Selezionare Crea da zero](media/create-approval-response-options/create-from-blank.png)

1. Cercare **SharePoint** e quindi selezionare **quando viene creato un elemento** dall'elenco dei trigger. 

1. Specificare l' **indirizzo del sito** di SharePoint e il **nome dell'elenco**. 

1. Selezionare **nuovo passaggio**, cercare **approvazione**, quindi selezionare **Avvia e attendere un'approvazione (v2)** .

1. Nella scheda **Avvia e attendi un'approvazione (v2)** selezionare l'elenco **tipo di approvazione** .

    ![Tipo di approvazione](media/create-approval-response-options/select-approval-type.png)

1. Selezionare **risposte personalizzate: attendere una risposta (Premium)** .

    ![Risposte personalizzate](media/create-approval-response-options/select-custom-responses.png)

    Si creeranno quindi le risposte personalizzate che i responsabili approvazione utilizzeranno per rispondere a una richiesta di approvazione per la spesa di un dipendente.


1. Nella casella **elemento Opzioni di risposta-1** immettere **Accept** , quindi selezionare **Aggiungi nuovo elemento**. 

    ![Risposta personalizzata 1](media/create-approval-response-options/enter-response-1.png)

1. Nella casella **Opzioni di risposta-2** immettere **Reject** , quindi selezionare **Aggiungi nuovo elemento**.

    ![Risposta personalizzata 2](media/create-approval-response-options/enter-response-2.png)

1. Nella casella **Opzioni di risposta-3** immettere **need more info (altre informazioni**).

    ![Risposta personalizzata 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Immettere un **titolo**, **assegnato a** (messaggio di posta elettronica per il responsabile approvazione) e **Dettagli** (i dettagli da contenere nella richiesta di approvazione).

    Di seguito è riportato un esempio di ciò che è possibile includere per la propria organizzazione.

    ![Dettagli risposte personalizzate](media/create-approval-response-options/enter-title-assigned-to-details.png)


Ora che sono state create le risposte personalizzate, potrebbe essere necessario eseguire diverse operazioni nel flusso, a seconda della risposta del responsabile approvazione.


## <a name="use-approval-responses"></a>USA risposte di approvazione 

Se la risposta alla richiesta è **Accept**, potrebbe essere necessario inviare un messaggio di posta elettronica al reparto contabilità, chiedendo loro di rimborsare il dipendente per la spesa. 

Se la risposta è **rifiutata**, potrebbe essere necessario inviare un messaggio di posta elettronica al dipendente, per informare che la richiesta è stata rifiutata.

Infine, se per la risposta del responsabile approvazione sono **necessarie altre informazioni**, è possibile inviare un messaggio di posta elettronica al dipendente, richiedendo al dipendente di fornire ulteriori informazioni.

Per eseguire una di queste operazioni nel flusso, aggiungere una [**condizione**](add-condition.md) o un'azione di **commutazione** al flusso, quindi selezionare il campo **risultato** della richiesta di approvazione dalla selezione contenuto dinamico. Verificare che il valore sia Accept, Need more info o Reject.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Rispondere alle richieste di approvazione con una risposta personalizzata

Gli approvatori ricevono richieste di approvazione tramite posta elettronica. Le richieste vengono visualizzate anche nel centro approvazioni in Microsoft Flow. 

![Messaggio di richiesta di approvazione](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Ulteriori informazioni
- Creare [flussi di approvazione singoli](modern-approvals.md)
- Creare [flussi di approvazione sequenziale](sequential-modern-approvals.md)
