---
title: Panoramica dei flussi con riconoscimento della soluzione | Microsoft Docs
description: Informazioni sui vantaggi della creazione di flussi nelle soluzioni.
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
ms.openlocfilehash: 8b0e64317b868dc32ede173329fa2f88ed53de76
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64465241"
---
# <a name="overview"></a>Panoramica

I flussi ospitati in una [soluzione](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview) diventano portabili e ciò significa che diventa molto semplice spostarli insieme a tutti i relativi componenti da un ambiente a un altro. Un caso d'uso tipico è quello di un fornitore di software indipendente (ISV) che sviluppa flussi in un ambiente sandbox e quindi li sposta in un ambiente di test. Al termine dei test, l'ISV dovrebbe quindi spostare i flussi in un ambiente di produzione per i client che li acquistano. Questo processo è molto più semplice quando si creano i flussi nelle soluzioni e quindi si spostano le soluzioni e i relativi contenuti.

I flussi creati all'interno di una soluzione sono noti come flussi con *riconoscimento della soluzione*. È possibile aggiungere più flussi in un'unica soluzione.

> [!NOTE] 
> Non è possibile spostare flussi senza riconoscimento della soluzione (i flussi non creati in una soluzione) in una soluzione.

## <a name="prerequisites"></a>Prerequisiti

Sono necessari i componenti seguenti per creare soluzioni e flussi con riconoscimento della soluzione:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Un ambiente con la versione 9.1.0.267 o versione successiva.

  Per controllare la versione, passare all'[interfaccia di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com), selezionare **Ambienti**, selezionare l'ambiente a cui si è interessati e quindi selezionare la scheda **Dettagli**.

## <a name="create-a-solution"></a>Creare una soluzione

Seguire questa procedura per creare una soluzione:

1. Eseguire l'accesso a [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare **Soluzioni** dalla barra di spostamento.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Selezionare **+ Nuova soluzione**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Specificare tutte le informazioni richieste per la nuova soluzione, tra cui **Nome visualizzato**, **Editore**, **Versione** e **Nome**. È anche consigliabile fornire una descrizione della soluzione.

   ![](./media/overview-solution-flows/new-solution.png)

1. Selezionare **Salva e chiudi** dal menu nella parte superiore.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   La nuova soluzione potrebbe essere simile all'immagine seguente:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Selezionare **Soluzioni** per aggiornare l'elenco delle soluzioni se non viene visualizzata la nuova soluzione.

## <a name="learn-more"></a>Altre informazioni

- [Creare un flusso in una soluzione](./create-flow-solution.md)
- [Esportare una soluzione](./export-flow-solution.md)
- [Importare una soluzione](./import-flow-solution.md)
- [Modificare un flusso con riconoscimento della soluzione](./edit-solution-aware-flow.md)
- [Rimuovere un flusso con riconoscimento della soluzione](./remove-solution-aware-flow.md)
