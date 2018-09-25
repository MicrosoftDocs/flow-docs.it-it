---
title: Informazioni su come automatizzare attività ripetitive con i flussi attivati da un pulsante che accettano input dell'utente| Microsoft Docs
description: Microsoft Flow rende più semplice automatizzare attività ripetitive. I flussi possono anche accettare l'input dell'utente durante l'esecuzione di un'attività ripetitiva.
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
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f87b0d93b912799a4977f347d89b12421cf42e70
ms.sourcegitcommit: ffed9f02092fbd19fc4108aee05dd40d1a2a3755
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711566"
---
# <a name="introducing-button-flows-with-user-input"></a>Introduzione ai flussi di un pulsante con input dell'utente
Creare un flusso di un pulsante per eseguire attività di routine semplicemente toccando un pulsante. Personalizzare il flusso consentendo all'utente di fornire dettagli specifici che verranno usati quando viene eseguito il flusso. Questo argomento illustra come creare un flusso di un pulsante che accetta l'input dell'utente e quindi eseguire il flusso di un pulsante, evidenziando come fornire l'input dell'utente.

È possibile creare il flusso di un pulsante nel sito Web di Microsoft Flow o nell'app per dispositivi mobili per Microsoft Flow. In questo argomento, si userà il sito Web.

### <a name="prerequisites"></a>Prerequisiti
* Un account nel sito Web di Microsoft Flow.

## <a name="open-the-template"></a>Aprire il modello
1. Accedere al [sito Web di Microsoft Flow](https://flow.microsoft.com), immettere **Visual Studio** nella casella di ricerca e quindi scegliere o toccare l'icona di ricerca per trovare tutti i modelli relativi a Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Selezionare il modello **Open a Priority 2 Bug in Visual Studio** (Apri un bug con priorità 2 in Visual Studio):
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Selezionare il pulsante **Usa questo modello**:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Questo modello usa Visual Studio Team Services (VSTS) e i servizi di notifica Push. È necessario effettuare l'accesso a questi servizi se non si ha una connessione a nessuno di essi. Il pulsante **Accedi** verrà visualizzato solo se è necessario effettuare l'accesso a un servizio.
4. Dopo aver effettuato l'accesso ai servizi necessari, selezionare il pulsante **Continua**:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (facoltativo) Modificare il nome del flusso digitando un nome a scelta nella casella nella parte superiore del portale:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Personalizzare l'input dell'utente
1. Nella scheda di attivazione, selezionare **Modifica**:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Selezionare l'icona **+** per espandere la pagina per poter aggiungere campi di input personalizzati:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Immettere il **titolo** e la **descrizione** dell'input per ogni campo personalizzato da rendere disponibile quando qualcuno esegue il flusso.  
   
    In questo esempio, si creeranno due campi di input personalizzati (**Bug Repro steps** e **Bug severity**, ossia Passaggi per riprodurre il bug e Gravità del bug) in modo che chiunque usi questo flusso possa immettere i passaggi per riprodurre il bug e valutarne la gravità:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Personalizzare il bug
1. Toccare la barra del titolo della scheda **Create a new work item** (Crea un nuovo elemento di lavoro):
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Effettuare le selezioni appropriate per l'ambiente VSTS e quindi selezionare **Modifica**:
   
    Ad esempio, connettersi a myinstance.visualstudio.com digitando **myinstance**.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Selezionare **Mostra le opzioni avanzate** per visualizzare gli altri campi di questa scheda:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Posizionare il cursore prima del token **Bug title** token e quindi immettere "Severity:" nel campo di testo **Title**.
5. Con il cursore ancora nel campo di testo del titolo, selezionare il token **Bug severity** token e quindi immettere "--".  
6. Nel campo di testo **Description** posizionare il cursore subito dopo il token **Bug description** e quindi premere INVIO per iniziare una nuova riga.
7. Posizionare il cursore nella nuova riga e quindi selezionare il token **Bug Repro steps**:
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Personalizzare la notifica push
1. Toccare la barra del titolo della scheda **Send a push notification** (Invia una notifica push) per espanderla.
2. Nell'elenco dei token del contenuto dinamico, selezionare **Vedi altro**e quindi aggiungere il token **URL** nel campo di testo**Collegamento**.
3. Nel campo di testo **Etichetta di collegamento** aggiungere il token **Id**:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Toccare **Crea flusso** nel menu per creare il flusso: ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Eseguire il flusso
In questa procedura dettagliata, si userà l'app per dispositivi mobili per Microsoft Flow per eseguire il flusso del pulsante appena creato. Si forniranno tutti gli input utente necessari a creare un bug con un titolo, una descrizione, i passaggi per riprodurlo e un livello di gravità.  

1. Nell'app per dispositivi mobili per Microsoft Flow, toccare la scheda **Pulsanti** e quindi toccare il pulsante **Creare report sui bug con passaggi**.
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Immettere il titolo per il bug che si sta segnalando e quindi toccare **Avanti**. Ad esempio:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Immettere la descrizione del bug che si sta segnalando e quindi toccare **Avanti**. Ad esempio:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Immettere i passaggi per riprodurre il bug che si sta segnalando e quindi toccare **Avanti**. Ad esempio:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Immettere la gravità del bug che si sta segnalando e quindi toccare **Fine**:  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    Viene eseguito il flusso.
6. (facoltativo) Toccare la scheda **Attività** per visualizzare i risultati.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (facoltativo) Visualizzare i risultati dettagliati dell'esecuzione toccando il passaggio **Create a new work item** (Crea un nuovo elemento di lavoro).
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)  

## <a name="next-steps"></a>Passaggi successivi
* [Condividere i flussi dei pulsanti](share-buttons.md)
* [Informazioni sui flussi dei pulsanti](introduction-to-button-flows.md)  
* [Informazioni sui flussi dei pulsanti con token di trigger](introduction-to-button-trigger-tokens.md)  

