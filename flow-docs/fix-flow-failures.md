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
ms.date: 01/17/2017
ms.author: stepsic
ms.openlocfilehash: 7f4e41437fa19f58c08e2ecd1fb65a3a30092ef8
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439543"
---
# <a name="troubleshooting-a-flow"></a>Risoluzione dei problemi relativi a un flusso
## <a name="identify-the-error"></a>Identificare l'errore
Prima di poter risolvere un flusso, è necessario identificare il motivo per cui non è riuscito. fare clic su o toccare l'icona delle notifiche nella parte superiore del portale Web (oppure aprire la scheda **Attività** nell'app per dispositivi mobili) e quindi fare clic su o toccare il flusso nell'elenco visualizzato.

![Notifiche](./media/fix-flow-failures/notifications-toolbar.png)

Vengono visualizzate informazioni relative al flusso e almeno un passaggio mostra un'icona di punto esclamativo rosso. Aprire tale passaggio ed esaminare il messaggio di errore.

![Messaggio di errore](./media/fix-flow-failures/flow-run-failure.png)

## <a name="authentication-failures"></a>Errori di autenticazione
In molti casi, i flussi non riescono a causa di un errore di autenticazione. Se si riscontra questo tipo di errore, il messaggio di errore contiene **Non autorizzato** o viene visualizzato un codice di errore **401** o **403**. In genere, è possibile risolvere un errore di autenticazione aggiornando la connessione:

1. Nella parte superiore del portale Web, fare clic su o toccare l'icona dell'ingranaggio per aprire il menu **Impostazioni**, quindi fare clic su o toccare **Connessioni**.
2. Scorrere fino alla connessione a cui si riferisce il messaggio di errore **Non autorizzato**.
3. Accanto alla connessione, fare clic su o toccare il collegamento **Verifica password** nel messaggio sulla connessione non autenticata.
4. Verificare le credenziali seguendo le istruzioni visualizzate, tornare all'errore di esecuzione del flusso, quindi fare clic su o toccare **Invia di nuovo**.
   
    A questo punto il flusso dovrebbe essere eseguito come previsto.

## <a name="action-configuration"></a>Configurazione dell'azione
Flussi non riescono neanche se un'impostazione in un'azione del flusso non funziona come previsto. In questo caso, il messaggio di errore contiene **Richiesta non valida** o **Non trovato** oppure viene visualizzato un codice di errore **400** o **404**.

Il messaggio di errore deve specificare come correggere l'errore. Sarà necessario fare clic su o toccare il pulsante **Modifica** e quindi correggere il problema all'interno della definizione di flusso. Salvare il flusso aggiornato, e quindi fare clic su o toccare **Invia di nuovo** per ripetere l'esecuzione con la configurazione aggiornata.

## <a name="other-failures"></a>Altri errori
Se viene visualizzato il codice di errore **500** o **502**, l'errore è temporaneo. Fare clic su o toccare **Invia di nuovo** per ripetere l'esecuzione del flusso.

Se si riscontrano altri problemi, [chiedere alla community](https://go.microsoft.com/fwlink/?LinkID=787467) perché altri utenti potrebbero aver riscontrato problemi simili.

