---
title: Avviare i flussi con i pulsanti Bttn | Microsoft Docs
description: Informazioni su come avviare i flussi con un pulsante Bttn
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2017
ms.author: deonhe
ms.openlocfilehash: c4010f95ad2db3c4f3b97b39f0b45934c7b69c48
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Eseguire i flussi con i pulsanti fisici (bttn) di The Button Corporation (anteprima)
Attivare i flussi premendo un bttn (un pulsante fisico creato da [The Button Corporation](https://my.bt.tn/)). Ad esempio, è possibile premere un bttn che attiva un flusso per eseguire queste attività:

* contattare il supporto tecnico con informazioni sul percorso
* inviare un messaggio di posta elettronica al team
* bloccare il calendario
* riordinare forniture

> [!IMPORTANT]
> È necessario [registrare](https://my.bt.tn/) il bttn per poterlo usare in un flusso.
> 
> [!TIP]
> Configurare tutte le proprietà bttn, ad esempio nome, posizione e indirizzo e-mail, sul [sito Web bttn](https://my.bt.tn/) prima di creare il flusso.
> 
> 

È anche possibile attivare un flusso usando un [pulsante fisico Flic](flic-button-flows.md).

## <a name="prerequisites"></a>Prerequisiti
* Avere accesso a [Microsoft Flow](https://flow.microsoft.com).
* Almeno un [bttn registrato](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Creare un flusso che viene attivato da un bttn
In questa procedura dettagliata, verrà usato un modello del supporto tecnico per creare un flusso che sia possibile attivare con la semplice pressione di un [bttn](https://my.bt.tn/). Quando viene eseguito il flusso, genera una richiesta di supporto e la invia quindi al supporto tecnico. La richiesta di supporto fornisce al supporto tecnico la posizione della sala in cui è necessaria assistenza. Questa procedura dettagliata illustra come creare questo flusso a partire da un modello, ma è possibile usare il modello vuoto, che assegna il controllo completo su tutti gli aspetti del flusso.

È possibile usare uno di questi modelli per creare rapidamente flussi per il bttn e connettersi a Zendesk, Google e SharePoint, tra gli altri:

![modelli bttn](./media/bttn-button-flows/bttn-templates.png)

Suggerimento: ai fini di questa procedura dettagliata, assegnare al bttn un nome che rappresenti una sala riunioni in un edificio tipico.

Le impostazioni per il bttn dovrebbero essere simili a questo esempio (dal sito Web bttn):

![modelli bttn](./media/bttn-button-flows/bttn-config.png)

Ora che è stato registrato e configurato il bttn, si inizierà a creare il flusso.

### <a name="sign-in-and-select-a-template"></a>Accedi e selezionare un modello
1. Accedere a [Microsoft Flow](https://flow.microsoft.com).
   
    ![accedere](./media/bttn-button-flows/sign-into-flow.png)
   
    Nota: in alternativa, è possibile creare flussi nell'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
2. Immettere **bttn** nella casella di ricerca, quindi selezionare l'icona di ricerca.
   
    ![ricerca](./media/bttn-button-flows/bttn-search-template.png)
   
    Dopo aver selezionato l'icona di ricerca, vengono visualizzati tutti i modelli che è possibile usare con i bttn.
3. Selezionare il modello **Use Bttn to call technical support for meeting room** (Usa Bttn per chiamare il supporto tecnico per la sala riunioni).
   
    ![modello di supporto](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Autorizzare Microsoft Flow a connettersi al bttn
1. Se richiesto, accedere ai servizi bttn e Office 365 Outlook, in modo da abilitare il pulsante **Continua**.
   
    ![credenziali](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Quando si accede al servizio bttn, autorizzare Microsoft Flow a usare i bttn.
   
    **Importante**: se si non autorizza Microsoft Flow a usare i bttn, non è possibile visualizzarli o connettersi a essi da Microsoft Flow.
   
    ![autorizzare](./media/bttn-button-flows/authorize-bttn.png)
3. Dopo aver effettuato l'accesso a entrambi i servizi, selezionare **Continua**.
   
    ![Continua](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Selezionare il bttn che attiva il flusso
1. Nella scheda **When a bttn is pressed** (Quando si preme un bttn), aprire l'elenco di ID bttn e quindi selezionare il bttn da usare.
   
    ![selezionare bttn](./media/bttn-button-flows/bttn-id.png)
   
    Il flusso dovrebbe ora essere simile a questo esempio.
   
    ![panoramica del flusso](./media/bttn-button-flows/bttn-done.png)
2. Assegnare un nome al flusso e quindi selezionare **Crea flusso** per salvarlo.
   
    ![salvare flusso](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Testare il flusso e confermare i risultati
1. Premere il pulsante sul bttn.
2. Visualizzare la cronologia di esecuzione del flusso per confermare che sia stata eseguita correttamente.
   
    È possibile controllare la cronologia di esecuzione nel sito Web Microsoft Flow o nel dispositivo mobile.
   
    Nota: lo stato dell'esecuzione è impostato su **in esecuzione** fino a quando un utente seleziona **Riconoscimento** nel messaggio di richiesta di supporto.
3. È anche possibile confermare che il messaggio di posta elettronica sia stato inviato al team di supporto.
   
    Se la procedura è stata seguita correttamente, il messaggio di posta elettronica di supporto sarà simile a questo esempio:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Risoluzione dei problemi
* Se il flusso non è stato attivato, accedere al sito di The Button Corporation e verificare se le attività del pulsante (pressioni) vengono registrate.
* È anche possibile analizzare l'attività di esecuzione nel sito Microsoft Flow e verificare la presenza di messaggi di errore.

## <a name="more-information"></a>Altre informazioni
* [Condividere i flussi dei pulsanti](share-buttons.md).
* Informazioni su come usare i [token per attivare i pulsanti](introduction-to-button-trigger-tokens.md) per inviare dati correnti quando vengono eseguiti i flussi dei pulsanti.
* [Installare l'app Microsoft Flow per Android](https://aka.ms/flowmobiledocsandroid).
* [Installare l'app Microsoft Flow per iOS](https://aka.ms/flowmobiledocsios).

