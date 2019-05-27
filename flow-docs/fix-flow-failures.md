---
title: Risoluzione dei problemi relativi a un flusso | Microsoft Docs
description: Risolvere alcuni dei motivi più comuni per cui i flussi non riescono
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0e151f3c5cd69fe07263e5fa36d46eb3b8be19f5
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992651"
---
# <a name="troubleshooting-a-flow"></a>Risoluzione dei problemi relativi a un flusso

## <a name="repair-tips-in-email"></a>Suggerimenti di correzione nel messaggio di posta elettronica

Suggerimenti di correzione vengono inviate ai proprietari del flusso tramite posta elettronica ogni volta che un flusso ha esito negativo. Questi messaggi di posta elettronica suggerimenti di correzione contengono commenti e suggerimenti specifici e pratici su determinati errori. Ad esempio, un errore comune è la configurazione di un flusso che tenta di ottenere un responsabile di Office 365, ma non esiste alcun gestore configurato in Azure Active Directory (Azure AD). Se questo o altre condizioni che il flusso esito negativo, si riceve un messaggio di suggerimenti di riparazione simile al seguente:

![Suggerimenti di correzione](media/fix-flow-failures/repair-tips-email.png)

Il messaggio di posta elettronica di riparazione suggerimenti contiene le sezioni seguenti:

Nome|Descrizione
---|---
Ora|Visualizza il tempo prima di tutto il flusso non è riuscito.
Cos'è successo|Fornisce una descrizione del problema che ha causato l'errore nel flusso.
Come risolvere|Vengono forniti suggerimenti per la risoluzione del problema che causa l'errore nel flusso.
Risoluzione dei problemi di suggerimenti|Fornisce informazioni dettagliate, incluso il numero di volte in cui il flusso non è riuscito e un collegamento per ripetere il flusso con gli stessi dati di input.

Per correggere gli errori segnalati, selezionare **Correggi il flusso** e seguire le istruzioni nel messaggio di suggerimenti di correzione.

Messaggi di posta elettronica di riparazione suggerimenti sono facoltativi. Se non si desidera riceverli, disattivarli semplicemente dal menu di proprietà per il flusso specifico.

Se il flusso non riesce, è possibile anche correggere tale errore direttamente in Microsoft Flow.  Ecco alcuni scenari di errore comuni e suggerimenti su come risolverli.

## <a name="identify-the-error"></a>Identificare l'errore
Prima di poter risolvere un flusso, è necessario identificare il motivo per cui non è riuscito. fare clic su o toccare l'icona delle notifiche nella parte superiore del portale Web (oppure aprire la scheda **Attività** nell'app per dispositivi mobili) e quindi fare clic su o toccare il flusso nell'elenco visualizzato.

![Notifiche](./media/fix-flow-failures/notifications-toolbar.png)

Vengono visualizzate informazioni relative al flusso e almeno un passaggio mostra un'icona di punto esclamativo rosso. Aprire tale passaggio ed esaminare il messaggio di errore.

![Messaggio di errore](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Errori di autenticazione
In molti casi, i flussi non riescono a causa di un errore di autenticazione. Se si riscontra questo tipo di errore, il messaggio di errore contiene **Non autorizzato** o viene visualizzato un codice di errore **401** o **403**. In genere, è possibile risolvere un errore di autenticazione aggiornando la connessione:

1. Nella parte superiore del portale web, fare clic o toccare l'icona a forma di ingranaggio per aprire la **le impostazioni** menu, quindi fare clic o toccare **connessioni**.
2. Scorrere fino alla connessione a cui si riferisce il messaggio di errore **Non autorizzato**.
3. Accanto alla connessione, fare clic su o toccare il collegamento **Verifica password** nel messaggio sulla connessione non autenticata.
4. Verificare le credenziali seguendo le istruzioni visualizzate, tornare all'errore di esecuzione del flusso, quindi fare clic su o toccare **Invia di nuovo**.
   
    A questo punto il flusso dovrebbe essere eseguito come previsto.

## <a name="action-configuration"></a>Configurazione dell'azione
Flussi non riescono neanche se un'impostazione in un'azione del flusso non funziona come previsto. In questo caso, il messaggio di errore contiene **Richiesta non valida** o **Non trovato** oppure viene visualizzato un codice di errore **400** o **404**.

Il messaggio di errore deve specificare come correggere l'errore. Sarà necessario fare clic su o toccare il pulsante **Modifica** e quindi correggere il problema all'interno della definizione di flusso. Salvare il flusso aggiornato, e quindi fare clic su o toccare **Invia di nuovo** per ripetere l'esecuzione con la configurazione aggiornata.

## <a name="other-failures"></a>Altri errori
Se viene visualizzato il codice di errore **500** o **502**, l'errore è temporaneo. Fare clic su o toccare **Invia di nuovo** per ripetere l'esecuzione del flusso.

## <a name="getting-help-from-support-or-the-community"></a>Ottenere assistenza dal supporto tecnico o dalla community

Quando è necessaria assistenza, è possibile usare la **aiutare Self** opzioni oppure è possibile **chiedere aiuto** dagli altri.

### <a name="self-help"></a>Supporto Self-help 

1. Andare alla [sito del supporto tecnico](https://flow.microsoft.com/support/).
1. Andare alla **Self Guida** categoria e selezionare una delle opzioni di supporto autonomo.

    ![Richiedere la sezione della Guida. Contattare il supporto tecnico.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Chiedi aiuto da altri utenti

1. Andare alla [sito del supporto tecnico](https://flow.microsoft.com/support/).
1. Selezionare **contattare il supporto tecnico** nel **chiedere aiuto** sezione.
    
    ![Richiedere la sezione della Guida. Contattare il supporto tecnico.](media/fix-flow-failures/ask-for-help.png)

1. Completare la **tipo di problema**, **categoria**e il **Comunicaci cosa occorre assistenza** campi e quindi selezionare **soluzioni**. 

1. Si noti che il **Solutions** sezione sono visualizzate dopo aver selezionato **soluzioni**. Contiene un elenco di risultati che è possibile usare per risolvere il problema che specifico da risolvere. 

    ![Dettagli di supporto integrata](media/fix-flow-failures/integrated-helper-details.png)

Se occorre assistenza con il problema, la Guida è disponibile dal nostro [community](https://go.microsoft.com/fwlink/?LinkID=787467) e Microsoft. 

