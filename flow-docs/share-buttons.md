---
title: Condividi i tuoi pulsanti con altri utenti. | Microsoft Docs
description: Condividi i tuoi pulsanti con altri utenti in modo che possano usare i tuoi pulsanti e risparmiare tempo.
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 098ebf9d8e02ede22a7914a2458375eb3641544a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548424"
---
# <a name="share-button-flows-in-microsoft-flow"></a>Condividere i flussi di un pulsante in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Nell'app Microsoft Flow per dispositivi mobili è possibile condividere i flussi di un [pulsante](introduction-to-button-flows.md) (pulsanti) con altri utenti o gruppi all'interno dell'organizzazione. Quando si condivide un pulsante, la persona o il gruppo con cui si condivide può eseguire il pulsante, nello stesso modo in cui eseguono i propri pulsanti. È anche possibile [condividere un collegamento](share-buttons.md#re-share-a-button) ai pulsanti condivisi da un altro utente. È possibile [interrompere la condivisione](share-buttons.md#stop-sharing-a-button) dei pulsanti in qualsiasi momento.

> Le schermate usate in questo documento sono state ricavate da un dispositivo Android. Se si usa un iPhone, le immagini possono essere visualizzate in modo diverso, ma la funzionalità è la stessa.
> 
> 

Seguire [questa procedura](share-buttons.md#use-shared-buttons) per usare un pulsante che qualcuno ha condiviso con l'utente.

## <a name="prerequisites"></a>Prerequisiti
Per condividere i pulsanti è necessario:

* Un account con accesso a [Microsoft Flow](https://flow.microsoft.com).
* Flusso da condividere.
* Un dispositivo mobile con l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).
* Un gruppo o un utente all'interno dell'organizzazione con cui condividere il pulsante.

## <a name="share-a-button"></a>Condividere un pulsante
È possibile condividere un pulsante dalla scheda **pulsanti** dell'app per dispositivi mobili Microsoft Flow.

1. Toccare l'icona piccola accanto al pulsante che si vuole condividere.
   
    ![pulsante Condividi](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Toccare **invita altri** dalla pagina **utenti pulsante** .
   
    ![pulsante Condividi](./media/share-buttons/share-button-flows-button-users.png)
3. Cercare e quindi selezionare il gruppo o la persona con cui si vuole condividere il pulsante.
   
    ![pulsante Condividi](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Toccare **Send (Invia** ) nella pagina **invite other (invita altri** ).
   
    ![pulsante Condividi](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Toccare **fine** nella pagina che indica che l'operazione di condivisione del pulsante è stata completata correttamente.
   
    ![pulsante Condividi](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Richiedi agli utenti di usare le proprie connessioni
> [!NOTE]
> Quando si condivide un pulsante, è possibile consentire alle persone con cui è stato condiviso il pulsante di utilizzare tutte le connessioni utilizzate dal pulsante. È anche possibile richiedere loro di usare le proprie connessioni. Se si consente ad altri utenti di usare le connessioni, non possono accedere alle credenziali nella connessione o riutilizzarle in qualsiasi altro flusso.
> 
> 

Seguire questa procedura per richiedere alle persone con cui sono stati condivisi i pulsanti di usare le proprie connessioni.

1. Selezionare **Gestisci connessioni** sullo schermo che verrà visualizzato immediatamente dopo la condivisione di un pulsante.
2. Selezionare **modifica** sul pulsante che si vuole gestire.
3. Selezionare **fornito dall'utente** o l'indirizzo di posta elettronica.
   
    La scelta indica le connessioni che devono essere usate nel pulsante condiviso.
   
    ![pulsante Condividi](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    È possibile visualizzare o modificare la scelta in qualsiasi momento. A tale scopo, selezionare la scheda **flussi** > il flusso condiviso > **utenti e connessioni** > la scheda **connessioni** > **modifica** sul pulsante che si vuole gestire.
   
    ![pulsante Condividi](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Visualizzare l'elenco degli utenti dei pulsanti
È possibile visualizzare tutti i gruppi o gli utenti con cui è stato condiviso un pulsante attenendosi alla seguente procedura dalla scheda **pulsanti** :

1. Toccare l'icona piccola accanto al pulsante a cui si è interessati.
2. Nella pagina **pulsante utenti** visualizzare tutti i gruppi o gli utenti con cui il pulsante è condiviso.
   
    ![Visualizza utenti pulsante](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Interrompi condivisione di un pulsante
È possibile interrompere la condivisione di un pulsante attenendosi alla seguente procedura dalla scheda **pulsanti** :

1. Toccare l'icona piccola accanto al pulsante che non si vuole più condividere.
2. Nella pagina **utenti pulsante** toccare l'utente o il gruppo con cui si desidera interrompere la condivisione del pulsante.
   
    ![pulsante Interrompi condivisione](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Toccare **Rimuovi utente** quando viene visualizzata la pagina dell'utente.
   
    ![pulsante Interrompi condivisione](./media/share-buttons/share-button-flows-remove-user.png)
4. Attendere il completamento dell'operazione di rimozione. Si noti che l'elenco **degli utenti del pulsante** viene aggiornato e che l'utente o il gruppo rimosso non è più elencato.
   
    ![pulsante Interrompi condivisione](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Monitorare la cronologia di esecuzione
Tutta la cronologia di esecuzione, incluse le esecuzioni avviate da una persona con cui è stato condiviso un pulsante, viene visualizzata solo nella scheda **attività** dell'app per dispositivi mobili Microsoft flow dell'autore dei pulsanti.

## <a name="use-shared-buttons"></a>Usare i pulsanti condivisi
Prima di poter eseguire un pulsante che qualcuno ha condiviso, è necessario aggiungerlo alla scheda **pulsanti** della pagina **Aggiungi pulsanti** .

1. Toccare **get more** (o i **nuovi pulsanti sono disponibili** banner se viene visualizzato) nella scheda **pulsanti** .
   
    ![nuovo pulsante condiviso con l'utente corrente](./media/share-buttons/share-button-flows-banner.png)
2. Toccare il pulsante che si vuole usare.
   
    Il pulsante toccato viene immediatamente aggiunto alla scheda **pulsanti** dell'app Microsoft Flow. È quindi possibile usare il pulsante dalla scheda **pulsanti** , esattamente come qualsiasi altro pulsante elencato qui.
   
    ![nuovo pulsante condiviso con l'utente corrente](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Ricondividere un pulsante
È possibile condividere un collegamento a un pulsante che è stato condiviso con l'utente.

1. Selezionare **...** accanto al pulsante che si vuole condividere.
2. Selezionare **Condividi collegamento al pulsante**.
   
    ![collegamento a un pulsante di ricondivisione](./media/share-buttons/re-share-button.png)
3. Selezionare l'app che si vuole usare per condividere il pulsante, quindi seguire i passaggi per inviare il pulsante alla persona con cui si vuole condividere.

## <a name="stop-using-a-shared-button"></a>Interrompi utilizzo di un pulsante condiviso
Se non si vuole più usare un pulsante che è stato condiviso, rimuoverlo dalla scheda **pulsanti** eseguendo questi passaggi:

1. Nella scheda **pulsanti** toccare **...** accanto al pulsante che non si vuole più usare.
   
    ![pulsante Rimuovi](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Toccare **Rimuovi** dal menu visualizzato.

Questo è tutto. Il pulsante non viene più visualizzato nella scheda **pulsanti** dell'app Microsoft Flow.

> [!NOTE]
> Dopo aver rimosso un pulsante condiviso, è possibile aggiungerlo di nuovo selezionando **Ottieni di più** dalla scheda **pulsanti** .
> 
> 

