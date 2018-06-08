---
title: Condividere i pulsanti con altri utenti. | Microsoft Docs
description: Condividere i pulsanti con altri utenti in modo che possano usarli per risparmiare tempo.
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
ms.date: 09/21/2017
ms.author: deonhe
ms.openlocfilehash: 2804c683defb94f87c40452a27382bc143c11f10
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "23442261"
---
# <a name="share-button-flows-in-microsoft-flow"></a>Condividere i flussi di un pulsante in Microsoft Flow
Nell'app Microsoft Flow per dispositivi mobili è possibile condividere i [flussi di un pulsante](introduction-to-button-flows.md) (pulsanti) con altri utenti o gruppi all'interno dell'organizzazione. Quando si condivide un pulsante, la persona o il gruppo con cui lo si condivide può eseguirlo allo stesso modo in cui esegue i propri pulsanti. È anche possibile [condividere un collegamento](share-buttons.md#re-share-a-button) a pulsanti che un altro utente ha condiviso. È possibile [interrompere la condivisione](share-buttons.md#stop-sharing-a-button) dei pulsanti in qualsiasi momento.

> Le schermate usate in questo documento provengono da un dispositivo Android. Se si usa un iPhone, le immagini potrebbero avere un aspetto diverso, ma la funzionalità è la stessa.
> 
> 

Seguire questa [procedura](share-buttons.md#use-shared-buttons) per usare un pulsante che qualcuno ha condiviso.

## <a name="prerequisites"></a>Prerequisiti
Per condividere i pulsanti, sono necessari:

* Un account con accesso a [Microsoft Flow](https://flow.microsoft.com).
* Un flusso da condividere.
* Un dispositivo mobile con l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
* Un gruppo o un utente all'interno dell'organizzazione con cui si vuole condividere il pulsante.

## <a name="share-a-button"></a>Condividere un pulsante
È possibile condividere un pulsante dalla scheda **Pulsanti** dell'app Microsoft Flow per dispositivi mobili.

1. Toccare la piccola icona accanto al pulsante che si vuole condividere.
   
    ![condividere pulsante](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Toccare **Invita altri** dalla pagina **Utenti pulsante**.
   
    ![condividere pulsante](./media/share-buttons/share-button-flows-button-users.png)
3. Cercare e quindi selezionare il gruppo o utente con cui si vuole condividere il pulsante.
   
    ![condividere pulsante](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Toccare **INVIA** nella pagina **Invita altri**.
   
    ![condividere pulsante](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Toccare **FINE** nella pagina che indica che l'operazione di condivisione del pulsante è stata completata correttamente.
   
    ![condividere pulsante](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Richiedere agli utenti di usare le loro connessioni
> [!NOTE]
> Quando si condivide un pulsante, è possibile consentire alle persone con cui è stato condiviso il pulsante di usare di tutte le connessioni usate dal pulsante. È anche possibile richiedere di usare le loro connessioni. Se si consente ad altri utenti di usare le proprie connessioni, non potranno accedere alle credenziali nella propria connessione o riutilizzarle in nessun altro flusso.
> 
> 

Seguire questi passaggi per chiedere alle persone con cui sono stati condivisi i pulsanti di usare le loro connessioni personali.

1. Selezionare **GESTISCI CONNESSIONI** sullo schermo che viene visualizzato immediatamente dopo aver condiviso un pulsante.
2. Selezionare **MODIFICA** sul pulsante che si vuole gestire.
3. Selezionare **Fornita dall'utente** o il proprio indirizzo di posta elettronica.
   
    La scelta indica quali connessioni devono essere usate nel pulsante condiviso.
   
    ![condividere pulsante](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    È possibile visualizzare o modificare la scelta in qualsiasi momento. A tale scopo, selezionare la scheda **Flussi** > il flusso condiviso > **Utenti e connessioni** > la scheda **CONNESSIONI** > **MODIFICA** sul pulsante che si vuole gestire.
   
    ![condividere pulsante](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Visualizzare l'elenco di utenti del pulsante
È possibile visualizzare tutti i gruppi o utenti con cui si condivide un pulsante seguendo i passaggi nella scheda **Pulsanti**:

1. Toccare la piccola icona accanto al pulsante a cui si è interessati.
2. Nella pagina **Utenti pulsante** visualizzare tutti i gruppi o gli utenti con cui è condiviso il pulsante.
   
    ![visualizzare utenti pulsante](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Interrompere la condivisione di un pulsante
È possibile interrompere la condivisione di un pulsante seguendo questi passaggi della scheda **Pulsanti**:

1. Toccare la piccola icona accanto al pulsante che non si vuole più condividere.
2. Nella pagina **Utenti pulsante** toccare l'utente o il gruppo con cui si vuole interrompere la condivisione del pulsante.
   
    ![interrompere la condivisione del pulsante](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Toccare **Rimuovi utente** quando viene visualizzata la pagina dell'utente.
   
    ![interrompere la condivisione del pulsante](./media/share-buttons/share-button-flows-remove-user.png)
4. Attendere il completamento dell'operazione di rimozione. Si noti che l'elenco **Utenti pulsante** viene aggiornato e che l'utente o il gruppo rimosso non è più visualizzato.
   
    ![interrompere la condivisione del pulsante](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Monitorare la cronologia di esecuzione
Tutta la cronologia di esecuzione, incluse le esecuzioni avviate da una persona con cui è stato condiviso un pulsante, viene visualizzata solo nella scheda **Attività** dell'app Microsoft Flow per dispositivi mobili dell'autore del pulsante.

## <a name="use-shared-buttons"></a>Usare i pulsanti condivisi
Per poter eseguire un pulsante che qualcuno ha condiviso è necessario aggiungerlo alla scheda **Pulsanti** della pagina **Aggiungi pulsanti**.

1. Toccare **VEDI ALTRI** (oppure il banner **Sono disponibili nuovi pulsanti**, se visualizzato) nella scheda **Pulsanti**.
   
    ![nuovo pulsante condiviso con me](./media/share-buttons/share-button-flows-banner.png)
2. Toccare il pulsante che si vuole usare.
   
    Il pulsante toccato viene immediatamente aggiunto alla scheda **Pulsanti** dell'app Microsoft Flow. È quindi possibile usare il pulsante dalla scheda **Pulsanti**, esattamente come qualsiasi altro pulsante qui elencato.
   
    ![nuovo pulsante condiviso con me](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Ricondividere un pulsante
È possibile condividere un collegamento a un pulsante che è stato condiviso con l'utente.

1. Selezionare **...** accanto al pulsante che si vuole condividere.
2. Selezionare **Condividi collegamento al pulsante**.
   
    ![ricondividere collegamento al pulsante](./media/share-buttons/re-share-button.png)
3. Selezionare l'app che si vuole usare per condividere il pulsante e quindi seguire i passaggi per inviare il pulsante all'utente con cui lo si vuole condividere.

## <a name="stop-using-a-shared-button"></a>Interrompere l'uso di un pulsante condiviso
Se non si vuole più usare un pulsante che è stato condiviso, rimuoverlo dalla scheda **Pulsanti** seguendo questi passaggi:

1. Nella scheda **Pulsanti** toccare **...** accanto al pulsante che non si vuole più usare.
   
    ![pulsante rimuovi](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Toccare **Rimuovi** dal menu visualizzato.

Questo è tutto. Il pulsante non appare più nella scheda **Pulsanti** dell'app Microsoft Flow.

> [!NOTE]
> Dopo aver rimosso un pulsante condiviso, è possibile aggiungerlo di nuovo selezionando **VEDI ALTRI** dalla scheda **Pulsanti**.
> 
> 

