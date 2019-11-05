---
title: Informazioni su come automatizzare attività ripetitive con i flussi di un pulsante che accettano l'input dell'utente | Microsoft Docs
description: Microsoft Flow semplifica l'automazione delle attività ripetitive. I flussi possono anche richiedere l'input dell'utente durante l'esecuzione di un'attività ripetitiva.
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
ms.openlocfilehash: a1bc5161bdd0e6a098d57cefafba99d3c89e6c97
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546454"
---
# <a name="introducing-button-flows-with-user-input"></a>Introduzione ai flussi di un pulsante con l'input dell'utente
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Creare un flusso di un pulsante per eseguire attività di routine semplicemente toccando un pulsante. Personalizzare il flusso consentendo all'utente di fornire dettagli specifici che verranno usati durante l'esecuzione del flusso. Questo argomento illustra la creazione di un flusso di un pulsante che accetta l'input dell'utente e quindi l'esecuzione del flusso del pulsante, evidenziando come fornire l'input dell'utente.

È possibile creare un flusso di un pulsante nel sito Web Microsoft Flow o nell'app per dispositivi mobili per Microsoft Flow. Per questo argomento verrà usato il sito Web.

### <a name="prerequisites"></a>Prerequisiti
* Un account nel sito Web Microsoft Flow.

## <a name="open-the-template"></a>Aprire il modello
1. Accedere al [sito Web di Microsoft Flow](https://flow.microsoft.com), immettere **Visual Studio** nella casella di ricerca e quindi toccare o fare clic sull'icona di ricerca per trovare tutti i modelli correlati a Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Selezionare il modello **Apri un bug con priorità 2 in Visual Studio** :
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Selezionare **Usa il pulsante modello** :
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Questo modello usa il Visual Studio Team Services (VSTS) e i servizi di notifica push. È necessario accedere a questi servizi se non si ha una connessione a uno di essi. Il pulsante **Accedi** verrà visualizzato solo se è necessario accedere a un servizio.
4. Dopo aver eseguito l'accesso a tutti i servizi necessari, selezionare il pulsante **continua** :
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. opzionale Modificare il nome del flusso digitando il nome desiderato nella casella nella parte superiore del portale:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Personalizzare l'input dell'utente
1. Nella scheda Trigger selezionare **modifica**:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Selezionare l'icona **+** per espandere la pagina in modo da poter aggiungere campi di input personalizzati:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Immettere il **titolo di input** e la **Descrizione di input** per ogni campo personalizzato che si vuole rendere disponibile quando un utente esegue il flusso.  
   
    In questo esempio verranno creati due campi di input personalizzati (passaggi per la**ripetizione dei bug** e **gravità del bug**), in modo che chiunque usi questo flusso possa immettere i passaggi per riprodurre il bug e valutare la gravità del bug:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Personalizzare il bug
1. Toccare la barra del titolo **Crea una nuova scheda elemento di lavoro** :
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Effettuare le selezioni appropriate per l'ambiente VSTS, quindi selezionare **modifica**:
   
    Ad esempio, connettersi a myinstance.visualstudio.com digitando **istanza**.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Selezionare **Mostra opzioni avanzate** per visualizzare gli altri campi di questa scheda:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Posizionare il cursore prima del token del **titolo del bug** , quindi immettere "Severity:" nel campo di testo **titolo** .
5. Con il cursore ancora nel campo del testo del titolo, selezionare il token di **gravità del bug** , quindi immettere "--".  
6. Nel campo testo **Descrizione** posizionare il cursore subito dopo il token di **Descrizione del bug** , quindi premere INVIO per avviare una nuova riga.
7. Posizionare il cursore sulla nuova riga e quindi selezionare il token dei **passaggi di ripetizione bug** :
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Personalizzare la notifica push
1. Toccare la barra del titolo nella scheda **Invia una notifica push** per espanderla.
2. Nell'elenco dei token di contenuto dinamici Selezionare **altro**e quindi aggiungere il token **URL** nel campo del testo del **collegamento** .
3. Nel campo di testo **etichetta collegamento** aggiungere il token **ID** :
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Toccare **Crea flusso** nel menu per creare il flusso: ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Eseguire il flusso
In questa procedura dettagliata si userà l'app per dispositivi mobili per Microsoft Flow per eseguire il flusso del pulsante appena creato. Si fornirà tutto l'input dell'utente necessario per creare un bug con un titolo, una descrizione, i passaggi di ripetizione e un livello di gravità.  

1. Nell'app per dispositivi mobili per Microsoft Flow toccare la scheda **pulsanti** , quindi toccare il pulsante **Crea report sui bug con passaggi** .
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Immettere il titolo per il bug che si sta segnalando e quindi toccare **Avanti**. Per esempio:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Immettere la descrizione del bug che si sta segnalando e quindi toccare **Avanti**. Per esempio:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Immettere i passaggi per riprodurre il bug che si sta segnalando e quindi toccare **Avanti**. Per esempio:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Immettere la gravità del bug che si sta segnalando e quindi toccare **fine**:  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    Il flusso viene eseguito.
6. opzionale Toccare la scheda **attività** per visualizzare i risultati.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. opzionale Mostra i risultati dettagliati dell'esecuzione del flusso toccando il passaggio **Crea un nuovo elemento di lavoro** .
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Usare tipi di input diversi

I flussi di un pulsante possono anche accettare tipi di dati avanzati. Di seguito è riportato l'elenco dei tipi di input dei dati accettati dai flussi dei pulsanti: 

- Testo
- Elenchi a discesa (ad esempio, pulsanti di opzione)
- Indirizzo di posta elettronica
- File (ad esempio, una foto sul telefono)
- Casella di controllo Sì o no
- Numero
- Data (con selezione calendario)

Per usare questi tipi di input, aggiungere **manualmente un** trigger di flusso, quindi aggiungere uno di questi tipi al flusso:

![Opzioni di input](media/button-flow-with-user-input-tokens/input-options.png)

Inoltre, potrebbe essere necessario designare alcuni input come richiesto e altri come facoltativi. Usare il menu azione (... sul lato destro) in ogni campo di input. È previsto un limite di cinque input per pulsante.

![Seleziona token facoltativi](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Passaggi successivi
* [Condividere i flussi di un pulsante](share-buttons.md)
* [Informazioni sui flussi dei pulsanti](introduction-to-button-flows.md)  
* [Informazioni sui flussi dei pulsanti con token di trigger](introduction-to-button-trigger-tokens.md)  

