---
title: Aggiungere una condizione a un flusso | Microsoft Docs
description: Consente di specificare che un flusso esegue una o più attività solo se una condizione è true.
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
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c67991a008047b2c8c58de3b9ae8833a5874543
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544702"
---
# <a name="add-a-condition-to-a-flow"></a>Aggiungere una condizione a un flusso
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Consente di specificare che un flusso esegue una o più attività solo se una condizione è true. Ad esempio, specificare che si riceverà un messaggio di posta elettronica solo se un tweet che contiene una parola chiave viene retweeted almeno 10 volte.

## <a name="prerequisites"></a>Prerequisiti

* [Creare un flusso](get-started-logic-template.md) da un modello: questa esercitazione [Usa questo modello](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) come esempio

## <a name="add-a-condition"></a>Aggiungere una condizione

1. In [Microsoft Flow](https://flow.microsoft.com)selezionare **flussi personali** nella barra di spostamento superiore.

    Potrebbe essere necessario eseguire l'accesso se non è già stato effettuato l'accesso.

1. Nell'elenco dei flussi selezionare uno dei flussi che sono stati creati.

    Questa esercitazione usa un esempio con un trigger di Twitter e un'azione di SharePoint.

1. Selezionare **Modifica flusso**.

1. Nell'ultima azione selezionare **nuovo passaggio**.

1. Selezionare **Aggiungi una condizione**.

    ![Pulsante condizione](./media/add-condition/add-condition.png)

1. Nella scheda **condizione** selezionare un'area vuota nella casella a sinistra.

    Verrà visualizzato l'elenco di **contenuto dinamico** .

1. Selezionare il parametro **retweet count** per aggiungerlo alla casella.

1. Nella casella al centro della scheda **condizione** selezionare **è maggiore o uguale a**.

1. Nella casella a destra immettere **10**.

    ![Casella nome oggetto con un parametro](./media/add-condition/specify-condition.png)

1. Selezionare l'intestazione dell'azione da usare all'interno della condizione (ad esempio **Crea elemento**) e trascinarla sotto il testo che legge **se sì**.

    Quando si rilascia il cursore, l'azione viene spostata in tale casella.

    ![Azione di trascinamento](./media/add-condition/drag-action.png)

1. Configurare l'azione in caso di necessità.

1. Salvare il flusso.

## <a name="edit-in-advanced-mode"></a>Modifica in modalità avanzata

È anche possibile selezionare **modifica in modalità avanzata** per scrivere condizioni più avanzate. È possibile utilizzare qualsiasi espressione del *linguaggio di definizione del flusso di lavoro* in modalità avanzata. Informazioni su tutte le [espressioni](https://msdn.microsoft.com/library/azure/mt643789.aspx)disponibili.

## <a name="next-steps"></a>Passaggi successivi

Informazioni su come [usare le espressioni](use-expressions-in-conditions.md) nelle condizioni in modalità avanzata.
