---
title: Informazioni su come creare flussi con riconoscimento della soluzione | Microsoft Docs
description: Informazioni su come creare flussi con riconoscimento della soluzione.
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
ms.openlocfilehash: cbc6e3a8ffe50eb7ad27e80eba044957647a1da3
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456538"
---
# <a name="create-a-flow-in-a-solution"></a>Creare un flusso in una soluzione

I flussi creati all'interno di una soluzione sono noti come flussi con *riconoscimento della soluzione*. Seguire questi passaggi per creare un flusso con riconoscimento della soluzione.

## <a name="prerequisites"></a>Prerequisiti

È necessario avere a disposizione almeno una soluzione prima di poter creare un flusso con riconoscimento della soluzione.

## <a name="create-the-flow"></a>Creare il flusso 

1. Eseguire l'accesso a [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare **Soluzioni** dalla barra di spostamento.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Selezionare la soluzione in cui si creerà il flusso.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Selezionare **+ Nuovo** e quindi selezionare **Flusso**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Verrà aperto Microsoft Flow.

1. Usare i connettori e i trigger disponibili per creare il flusso.

   In questo esempio verrà creato un flusso semplice che invia una notifica quando arriva un messaggio di posta elettronica nella posta in arrivo.
1. Cercare e quindi selezionare **Office 365 Outlook**.
1. Selezionare il trigger **All'arrivo di un nuovo messaggio di posta elettronica**.
1. Selezionare **+ Nuovo passaggio**.
1. Selezionare l'azione **Send me a mobile notification** (Invia notifica a dispositivo mobile).
1. Aggiungere il token dinamico **Oggetto** al campo **Testo** della casella **Send me a mobile notification** (Invia notifica a dispositivo mobile).
1. Assegnare un nome al flusso e quindi salvarlo.

   Il flusso dovrebbe essere simile al seguente:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Selezionare **Soluzioni** per visualizzare il flusso nella soluzione:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Altre informazioni

* [Creare una soluzione](./overview-solution-flows.md)
* [Esportare una soluzione](./export-flow-solution.md)
* [Importare una soluzione](./import-flow-solution.md)
* [Modificare un flusso con riconoscimento della soluzione](./edit-solution-aware-flow.md)
* [Rimuovere un flusso con riconoscimento della soluzione](./remove-solution-aware-flow.md)
