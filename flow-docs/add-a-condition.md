---
title: Aggiungere una condizione a un flusso | Microsoft Docs
description: "Specificare che un flusso esegue una o più attività solo se si verifica una particolare condizione."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: 1291b32f001be211acddbf1c83f3b1bdf03f2ac3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="add-a-condition-to-a-flow"></a>Aggiungere una condizione a un flusso
Specificare che un flusso esegue una o più attività solo se si verifica una particolare condizione. Ad esempio, specificare che si riceverà un messaggio di posta elettronica solo se un tweet che contiene una parola chiave viene ritwittato almeno 10 volte.

**Prerequisiti**

* [Creare un flusso](get-started-logic-template.md) da un modello: in questa esercitazione il [modello verrà usato come](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) esempio

## <a name="add-a-condition"></a>Aggiungere una condizione
1. In [flow.microsoft.com](https://flow.microsoft.com), selezionare **Flussi personali** nella barra di spostamento in alto.
2. Nell'elenco dei flussi, selezionare un flusso creato. Questa esercitazione usa un esempio con un trigger di Twitter e un'azione di SharePoint.
3. Nell'ultima azione, selezionare il pulsante **Nuovo passaggio**.
4. Selezionare **Aggiungere una condizione**.
   
    ![Pulsante condizione](./media/add-a-condition/add-condition.png)
5. Selezionare un'area vuota in **Nome oggetto** e fare clic su **Aggiungi contenuto dinamico** per aprire il menu del contenuto dinamico.
6. Selezionare il parametro **Retweet count** (Conteggio retweet) da aggiungere alla casella.
7. Nella casella **Relazione** selezionare **è maggiore o uguale a**.
8. Nella casella **Valore** digitare **10**.
   
    ![La casella NOME OGGETTO contenente un parametro](./media/add-a-condition/specify-condition.png)
9. Fare clic sull'intestazione dell'azione che si desidera all'interno della condizione (ad esempio **Crea elemento**) e trascinarla sotto al testo **SE SÌ**. Quando si rilascia il cursore, l'azione deve spostarsi in tale casella.
   
    ![Operazione di trascinamento](./media/add-a-condition/drag-action.png)
10. Salvare il flusso.

## <a name="edit-in-advanced-mode"></a>Modifica in modalità avanzata
È anche possibile selezionare il collegamento **Modifica in modalità avanzata** per scrivere condizioni più avanzate. Qui è possibile usare qualsiasi espressione tratta dal *linguaggio di definizione del flusso di lavoro*. [Altre informazioni su](https://msdn.microsoft.com/library/azure/mt643789.aspx) sulle funzioni disponibili.

