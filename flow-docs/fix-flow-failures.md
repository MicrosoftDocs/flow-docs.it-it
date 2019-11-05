---
title: Risoluzione dei problemi relativi a un flusso | Microsoft Docs
description: Risolvere alcuni dei motivi più comuni per cui i flussi hanno esito negativo
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
ms.openlocfilehash: 2981c125d722cb766a1cc840f404d84dfa57ac96
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547868"
---
# <a name="troubleshooting-a-flow"></a>Risoluzione dei problemi relativi a un flusso
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="repair-tips-in-email"></a>Suggerimenti per la riparazione nel messaggio di posta elettronica

I suggerimenti per la riparazione vengono inviati ai proprietari dei flussi tramite posta elettronica ogni volta che un flusso non riesce. I messaggi di posta elettronica con suggerimenti per la riparazione contengono commenti specifici e utilizzabili per determinati errori. Ad esempio, un errore comune è la configurazione di un flusso che tenta di ottenere il responsabile di un utente in Office 365, ma non è configurato alcun gestore in Azure Active Directory (Azure AD). Se questa o più condizioni provocano un errore nel flusso, si riceve un messaggio di posta elettronica con suggerimenti di ripristino simile al seguente:

![Suggerimenti per la riparazione](media/fix-flow-failures/repair-tips-email.png)

Il messaggio di posta elettronica suggerimenti per la riparazione contiene le sezioni seguenti:

Nome|Descrizione
---|---
Tempo|Visualizza l'ora in cui il flusso non è riuscito.
Cos'è successo|Fornisce una descrizione del problema che ha causato l'errore nel flusso.
Correzione Ricerca per categorie|Fornisce suggerimenti per la risoluzione del problema che causa l'errore nel flusso.
Suggerimenti per la risoluzione dei problemi|Fornisce dettagli che includono il numero di volte in cui il flusso non è riuscito e un collegamento per ritentare il flusso con gli stessi dati di input.

Per correggere gli errori segnalati, selezionare **Correggi il flusso** e seguire i passaggi nel messaggio di posta elettronica suggerimenti per la riparazione.

I suggerimenti per la riparazione sono facoltativi. Se non si vuole riceverli, è sufficiente disattivarli dal menu proprietà per il flusso specifico.

Se il flusso ha esito negativo, è anche possibile risolverlo direttamente in Microsoft Flow.  Ecco alcuni scenari comuni di errore e suggerimenti su come risolverli.

## <a name="identify-the-error"></a>Identificare l'errore
Prima di poter correggere un flusso, è necessario identificare il motivo per cui non è riuscito. Toccare o fare clic sull'icona notifiche nella parte superiore del portale Web (oppure aprire la scheda **attività** nell'app per dispositivi mobili) e quindi toccare o fare clic sul flusso nell'elenco visualizzato.

![Notifiche](./media/fix-flow-failures/notifications-toolbar.png)

Vengono visualizzati i dettagli relativi al flusso e almeno un passaggio Mostra un'icona di punto esclamativo rosso. Aprire il passaggio ed esaminare il messaggio di errore.

![Messaggio di errore](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Errori di autenticazione
In molti casi, i flussi hanno esito negativo a causa di un errore di autenticazione. Se si dispone di questo tipo di errore, il messaggio di **errore contiene un** codice di errore **401** o **403** . È in genere possibile correggere un errore di autenticazione aggiornando la connessione:

1. Nella parte superiore del portale Web toccare o fare clic sull'icona a forma di ingranaggio per aprire il menu **Impostazioni** e quindi toccare o fare clic su **connessioni**.
2. Scorrere fino alla connessione per la quale è stato visualizzato il messaggio di errore **non autorizzato** .
3. Accanto alla connessione, toccare o fare clic sul collegamento **Verifica password** nel messaggio sulla connessione non autenticata.
4. Verificare le credenziali seguendo le istruzioni visualizzate, tornare all'errore di esecuzione del flusso e quindi fare clic o toccare **Invia**di più.
   
    Il flusso dovrebbe ora funzionare come previsto.

## <a name="action-configuration"></a>Configurazione dell'azione
I flussi hanno esito negativo anche se un'impostazione in un'azione del flusso non funziona come previsto. In questo caso, il messaggio di errore contiene una richiesta **non** **valida** o non è stato trovato oppure viene visualizzato un codice di errore **400** o **404** .

Il messaggio di errore deve specificare come correggere l'errore. È necessario toccare o fare clic sul pulsante **modifica** e quindi correggere il problema all'interno della definizione del flusso. Salvare il flusso aggiornato e quindi fare clic o toccare **Invia** di nuovo per provare a eseguire nuovamente con la configurazione aggiornata.

## <a name="other-failures"></a>Altri errori
Se viene visualizzato il codice di errore **500** o **502** , l'errore è temporaneo o temporaneo. Toccare o fare clic su **Invia** di nuovo per provare a eseguire nuovamente il flusso.

## <a name="getting-help-from-support-or-the-community"></a>Ottenere assistenza dal supporto tecnico o dalla community

Per ottenere assistenza, è possibile usare le opzioni di **supporto self-service** oppure è possibile **richiedere assistenza** ad altri utenti.

### <a name="self-help"></a>Guida automatica 

1. Visitare il [sito del supporto tecnico](https://flow.microsoft.com/support/).
1. Passare alla categoria **self help** e selezionare una delle opzioni self-help.

    ![Consultare la sezione della guida. Contattare il supporto tecnico.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Richiedi assistenza da altri utenti

1. Visitare il [sito del supporto tecnico](https://flow.microsoft.com/support/).
1. Selezionare **contattare il supporto tecnico** nella sezione **Richiedi assistenza** .
    
    ![Consultare la sezione della guida. Contattare il supporto tecnico.](media/fix-flow-failures/ask-for-help.png)

1. Completare il **tipo di problema**, la **categoria**e la pagina **indicare le informazioni necessarie per** i campi e quindi selezionare **Visualizza soluzioni**. 

1. Si noti che la sezione **Solutions** viene visualizzata dopo aver selezionato **Visualizza soluzioni**. Contiene un elenco di risultati che è possibile usare per risolvere il problema che si sta affrontando. 

    ![Dettagli Helper integrati](media/fix-flow-failures/integrated-helper-details.png)

Se è necessario assistenza per un problema, la guida è disponibile dalla nostra [community](https://go.microsoft.com/fwlink/?LinkID=787467) e da Microsoft. 

