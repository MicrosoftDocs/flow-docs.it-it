---
title: Aggiungere una condizione a un flusso | Microsoft Docs
description: Specificare che un flusso esegue una o più attività solo se si verifica una condizione.
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
ms.openlocfilehash: b4407238f9d1782db802b47060b156b8b77c328b
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689043"
---
# <a name="add-a-condition-to-a-flow"></a>Aggiungere una condizione a un flusso

Specificare che un flusso esegue una o più attività solo se si verifica una condizione. Ad esempio, specificare che si riceverà un messaggio di posta elettronica solo se un tweet che contiene una parola chiave viene ritwittato almeno 10 volte.

## <a name="prerequisites"></a>Prerequisiti

* [Creare un flusso](get-started-logic-template.md) da un modello: questa esercitazione [usa il modello](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) come esempio

## <a name="add-a-condition"></a>Aggiungere una condizione

1. In [Microsoft Flow](https://flow.microsoft.com), selezionare **Flussi personali** sulla barra di spostamento in alto.

    Potrebbe essere necessario accedere, se non è già stato eseguito l'accesso.

1. Nell'elenco di flussi selezionare uno dei flussi creati.

    Questa esercitazione usa un esempio con un trigger di Twitter e un'azione di SharePoint.

1. Selezionare **Modifica flusso**.

1. Nell'ultima azione selezionare **Nuovo passaggio**.

1. Selezionare **Aggiungere una condizione**.

    ![Pulsante condizione](./media/add-condition/add-condition.png)

1. Nella scheda **Condizione** selezionare un'area vuota nella casella a sinistra.

    Viene visualizzato l'elenco **Contenuto dinamico**.

1. Selezionare il parametro **Retweet count** (Conteggio retweet) da aggiungere alla casella.

1. Nella casella centrale della scheda **Condizione** selezionare **è maggiore o uguale a**.

1. Nella casella a destra immettere **10**.

    ![La casella NOME OGGETTO contenente un parametro](./media/add-condition/specify-condition.png)

1. Selezionare l'intestazione dell'azione da usare all'interno della condizione, ad esempio **Crea elemento**, quindi trascinarla sotto il testo **Se sì**.

    Quando si rilascia il cursore, l'azione si sposta in tale casella.

    ![Operazione di trascinamento](./media/add-condition/drag-action.png)

1. Configurare l'azione in base alla necessità.

1. Salvare il flusso.

## <a name="edit-in-advanced-mode"></a>Modifica in modalità avanzata

È anche possibile selezionare **Modifica in modalità avanzata** per scrivere condizioni più avanzate. Qui è possibile usare qualsiasi espressione tratta dal *linguaggio di definizione del flusso di lavoro* in modalità avanzata. Informazioni su tutte le [espressioni](https://msdn.microsoft.com/library/azure/mt643789.aspx) disponibili.

## <a name="next-steps"></a>Passaggi successivi

Informazioni su come [usare le espressioni](use-expressions-in-conditions.md) nelle condizioni in modalità avanzata.
