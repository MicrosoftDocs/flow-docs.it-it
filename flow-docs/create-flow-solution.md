---
title: Informazioni su come creare flussi compatibili con la soluzione | Microsoft Docs
description: Informazioni su come creare flussi compatibili con la soluzione.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbd1ee543cfe5f54b61486eefbacbd5bb837f33
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546482"
---
# <a name="create-a-flow-in-a-solution"></a>Creare un flusso in una soluzione
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I flussi creati in una soluzione sono noti come flussi compatibili con la *soluzione* . Seguire questa procedura per creare un flusso in grado di riconoscere la soluzione.

## <a name="prerequisites"></a>Prerequisiti

Per poter creare un flusso in grado di riconoscere la soluzione, è necessario disporre di almeno una soluzione.

## <a name="create-the-flow"></a>Creare il flusso 

1. Accedere a [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare **soluzioni** dalla barra di spostamento.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Selezionare la soluzione in cui verrà creato il flusso.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Selezionare **+ nuovo**, quindi selezionare **Flow**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow si apre.

1. Usare i connettori e i trigger disponibili per compilare il flusso.

   In questo esempio verrà creato un flusso semplice che invia una notifica all'arrivo di un messaggio di posta elettronica nella posta in arrivo.
1. Cercare e quindi selezionare **Office 365 Outlook**.
1. Selezionare il trigger **quando arriva un nuovo messaggio di posta elettronica** .
1. Selezionare **+ nuovo passaggio**.
1. Selezionare l'azione **Invia una notifica per dispositivi mobili** .
1. Aggiungere il token dinamico **soggetto** al campo di **testo** della casella **Invia una notifica per dispositivi mobili** .
1. Assegnare un nome al flusso e quindi salvare il flusso.

   Il flusso dovrebbe apparire come segue:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Selezionare **soluzioni** per visualizzare il flusso nella soluzione:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Ulteriori informazioni

* [Creare una soluzione](./overview-solution-flows.md)
* [Esportare una soluzione](./export-flow-solution.md)
* [Importare una soluzione](./import-flow-solution.md)
* [Modificare un flusso in grado di riconoscere la soluzione](./edit-solution-aware-flow.md)
* [Rimuovere un flusso in grado di riconoscere la soluzione](./remove-solution-aware-flow.md)
