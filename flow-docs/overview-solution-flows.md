---
title: Panoramica dei flussi compatibili con la soluzione | Microsoft Docs
description: Scopri i vantaggi della creazione di flussi nelle soluzioni.
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
ms.openlocfilehash: 19eb7d051c4d1438ec45305620e369b5499252a0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548573"
---
# <a name="overview"></a>Panoramica
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Quando si ospitano i flussi in una [soluzione](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), diventano portabili, rendendoli più agevoli spostarli e tutti i relativi componenti da un ambiente a un altro. Un caso di utilizzo tipico è quello di un fornitore di software indipendente (ISV) per sviluppare flussi in un ambiente sandbox, quindi spostare tali flussi in un ambiente di testing. Dopo i test, l'ISV sposta i flussi in un ambiente di produzione per i client che acquistano i flussi. Questo processo è molto più semplice quando si creano flussi in soluzioni e quindi si spostano le soluzioni e il relativo contenuto.

I flussi creati all'interno di una soluzione sono noti come flussi compatibili con la *soluzione* . È possibile aggiungere più flussi in un'unica soluzione.

> [!NOTE] 
> Non è possibile spostare in una soluzione i flussi non compatibili con la soluzione (flussi non creati in una soluzione).

## <a name="prerequisites"></a>Prerequisiti

Per creare soluzioni e flussi compatibili con la soluzione, è necessario disporre dei componenti seguenti:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Ambiente con versione 9.1.0.267 o successiva.

  Per controllare la versione, passare a [Microsoft Flow](https://admin.flow.microsoft.com)interfaccia di amministrazione, selezionare **ambienti**, selezionare l'ambiente a cui si è interessati, quindi selezionare la scheda **Dettagli** .

## <a name="create-a-solution"></a>Creare una soluzione

Per creare una soluzione, attenersi alla procedura seguente:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare **soluzioni** dalla barra di spostamento.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Selezionare **+ nuova soluzione**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Fornire tutte le informazioni necessarie per la nuova soluzione, inclusi il **nome visualizzato**, l' **editore**, la **versione**e il **nome**. È inoltre consigliabile fornire una descrizione della soluzione.

   ![](./media/overview-solution-flows/new-solution.png)

1. Selezionare **Salva e Chiudi** dal menu in alto.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   La nuova soluzione potrebbe apparire come questa immagine:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Selezionare **soluzioni** per aggiornare l'elenco di soluzioni se la nuova soluzione non viene visualizzata.

## <a name="learn-more"></a>Ulteriori informazioni

- [Creare un flusso in una soluzione](./create-flow-solution.md)
- [Esportare una soluzione](./export-flow-solution.md)
- [Importare una soluzione](./import-flow-solution.md)
- [Modificare un flusso in grado di riconoscere la soluzione](./edit-solution-aware-flow.md)
- [Rimuovere un flusso in grado di riconoscere la soluzione](./remove-solution-aware-flow.md)
