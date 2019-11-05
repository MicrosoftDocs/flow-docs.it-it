---
title: Avviare i flussi con BTTN | Microsoft Docs
description: Informazioni su come avviare i flussi con un BTTN
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
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5835593c7bd020cdfce5f463a7fc198907c4ba6c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545683"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Eseguire i flussi con i pulsanti fisici (BTTN) di Button Corporation (anteprima)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Attivare i flussi premendo un BTTN (un pulsante fisico creato da [Button Corporation](https://my.bt.tn/)). Ad esempio, è possibile premere un BTTN che attiva un flusso per eseguire queste attività:

* Contatta il supporto tecnico con le informazioni sulla posizione
* Invia un messaggio di posta elettronica al team
* blocca il calendario
* Riordina gli approvvigionamenti

> [!IMPORTANT]
> È necessario [registrare](https://my.bt.tn/) il BTTN prima di poterlo usare in un flusso.
> 
> [!TIP]
> Configurare tutte le proprietà di BTTN, ad esempio nome, posizione e indirizzo di posta elettronica nel [sito Web BTTN](https://my.bt.tn/) prima di creare il flusso.
> 
> 

È anche possibile attivare un flusso usando un [pulsante fisico Flic](flic-button-flows.md).

## <a name="prerequisites"></a>Prerequisiti
* Accesso a [Microsoft Flow](https://flow.microsoft.com).
* Almeno un [BTTN registrato](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Creare un flusso che viene attivato da un BTTN
In questa procedura dettagliata viene usato un modello helpdesk per creare un flusso che è possibile attivare con una singola pressione di un [BTTN](https://my.bt.tn/). Quando il flusso viene eseguito, viene generata una richiesta di supporto e quindi inviato al supporto tecnico. La richiesta di supporto fornisce il supporto tecnico con la posizione in cui è necessaria la guida. Questa procedura dettagliata illustra come creare questo flusso da un modello, ma è possibile usare il modello vuoto, che offre il controllo completo su tutti gli aspetti del flusso.

È possibile usare uno di questi modelli per creare rapidamente i flussi per la BTTN e connettersi a Zendesk, Google e SharePoint, tra gli altri:

![modelli BTTN](./media/bttn-button-flows/bttn-templates.png)

Suggerimento: ai fini di questa procedura dettagliata, assegnare al BTTN un nome che rappresenti una sala riunioni in un tipico edificio di Office.

Le impostazioni per BTTN dovrebbero essere simili a questo esempio (dal sito Web BTTN):

![modelli BTTN](./media/bttn-button-flows/bttn-config.png)

Ora che è stato registrato e configurato il BTTN, è possibile iniziare a creare il flusso.

### <a name="sign-in-and-select-a-template"></a>Accedere e selezionare un modello
1. Accedere [Microsoft Flow](https://flow.microsoft.com).
   
    ![Accedi](./media/bttn-button-flows/sign-into-flow.png)
   
    Nota: in alternativa, è possibile creare flussi nell'app Microsoft Flow per dispositivi mobili per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).
2. Immettere **BTTN** nella casella di ricerca e quindi selezionare l'icona di ricerca.
   
    ![Ricerca](./media/bttn-button-flows/bttn-search-template.png)
   
    Dopo aver selezionato l'icona di ricerca, vengono visualizzati tutti i modelli che è possibile usare con BTTN.
3. Selezionare il modello **USA BTTN per chiamare il supporto tecnico per la sala riunioni** .
   
    ![modello di supporto](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Autorizzare Microsoft Flow a connettersi alla BTTN
1. Se richiesto, accedere ai servizi BTTN e Office 365 Outlook, che abilitano il pulsante **continua** .
   
    ![credenziali](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Quando si accede al servizio BTTN, autorizzare Microsoft Flow a usare BTTN.
   
    **Importante**: se non si autorizza Microsoft Flow a usare la BTTN, non è possibile visualizzarli o connettersi da Microsoft Flow.
   
    ![autorizzare](./media/bttn-button-flows/authorize-bttn.png)
3. Dopo aver eseguito l'accesso a entrambi i servizi, selezionare **continua**.
   
    ![Continuare](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Selezionare il BTTN che attiva il flusso
1. Nella scheda **quando si preme un BTTN** , aprire l'elenco di ID BTTN e quindi selezionare il BTTN che si vuole usare.
   
    ![Seleziona BTTN](./media/bttn-button-flows/bttn-id.png)
   
    Il flusso dovrebbe ora essere simile a questo esempio.
   
    ![Panoramica di Flow](./media/bttn-button-flows/bttn-done.png)
2. Assegnare un nome al flusso e quindi selezionare **Crea flusso** per salvarlo.
   
    ![Salva flusso](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Testare il flusso e confermare i risultati
1. Premere il pulsante del BTTN.
2. Visualizzare la cronologia di esecuzione del flusso per verificare che sia stata eseguita correttamente.
   
    È possibile controllare la cronologia di esecuzione nel sito Web Microsoft Flow o nel dispositivo mobile.
   
    Nota: lo stato dell'esecuzione è impostato su in **esecuzione** fino a quando un utente non seleziona **riconoscimento** nel messaggio di richiesta di supporto.
3. È anche possibile verificare che il messaggio di posta elettronica sia stato inviato al team di supporto.
   
    Se è stato seguito, il messaggio di posta elettronica di supporto è simile a questo esempio:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Risoluzione dei problemi
* Se il flusso non è stato attivato, accedere al sito di Button Corporation e verificare che l'attività del pulsante (premere) venga registrata.
* È anche possibile analizzare l'attività di esecuzione nel sito Microsoft Flow e verificare la presenza di messaggi di errore.

## <a name="more-information"></a>Ulteriori informazioni
* [Condividere i flussi](share-buttons.md)di un pulsante.
* Informazioni su come usare i [token per attivare i pulsanti](introduction-to-button-trigger-tokens.md) per inviare dati correnti quando vengono eseguiti i flussi dei pulsanti.
* [Installare l'app Microsoft Flow per Android](https://aka.ms/flowmobiledocsandroid).
* [Installare l'app Microsoft Flow per iOS](https://aka.ms/flowmobiledocsios).

