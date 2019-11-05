---
title: Osservare un'esecuzione del flusso | Microsoft Docs
description: Visualizzare gli input e gli output per ogni passaggio di un flusso per verificare che si comporti come previsto.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/05/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 32afe2ef424b00f4d13ee4589b95062625d5f12c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548444"
---
# <a name="watch-your-flows-in-action"></a>Guarda i flussi in azione
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

>[!VIDEO https://www.youtube.com/embed/3wPoUCGm7Yg]

Per assicurarsi che i flussi vengano eseguiti come previsto, eseguire il trigger, quindi esaminare gli input e gli output generati da ogni passaggio nel flusso.

1. Creare o aggiornare un flusso, quindi lasciare aperta la finestra di progettazione dopo aver selezionato **Crea flusso** o **Aggiorna flusso**.

     Ad esempio, [creare un flusso](get-started-logic-flow.md) che invii un messaggio di posta elettronica ogni volta che un utente invia un tweet usando l'hashtag **#azure** .
1. Eseguire l'azione di avvio per il flusso.

    Ad esempio, inviare un tweet che contiene il **#azure** hashtag.

    L'azione iniziale e ogni passaggio successivo indicano se ha avuto esito positivo e il tempo impiegato.

    ![Immagine di un'esecuzione riuscita](./media/see-a-flow-run/successful-flow-run.png)
1. Selezionare il trigger o l'azione per visualizzare i relativi input e output.

    ![Immagine di una corretta esecuzione con schede espanse](./media/see-a-flow-run/successful-flow-expanded-cards.png)
1. Selezionare **Modifica flusso** per apportare altre modifiche oppure selezionare **fine** se il flusso funziona come previsto.
