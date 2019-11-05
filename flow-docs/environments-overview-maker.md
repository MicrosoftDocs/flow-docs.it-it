---
title: Informazioni sugli ambienti Microsoft Flow | Microsoft Docs
description: Informazioni su come usare gli ambienti per isolare i flussi
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8890e621d14fb0f2d00af4cdf767f05ddeab9f21
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547953"
---
# <a name="choosing-an-environment"></a>Scelta di un ambiente
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Questo articolo presenta Microsoft Flow **ambienti** in cui è possibile creare e isolare in modo sicuro i flussi, i gateway, le connessioni e altre risorse.

Verranno fornite informazioni su:

* Funzionalità fornite dagli ambienti.
* Passare da un ambiente all'altra.
* Come creare un flusso nell'ambiente corretto.

## <a name="environments-overview"></a>Panoramica degli ambienti

Quando si crea un flusso, si sceglie un ambiente per ospitare il flusso e le risorse utilizzate dal flusso. È possibile utilizzare ambienti distinti per scenari diversi.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Ecco alcuni scenari per l'uso degli ambienti

Scenario|Raccomandazione
-----|-----
Si vuole creare un flusso che usa una connessione a Microsoft Common Data Service.|Posizionare il flusso e il Common Data Service nello stesso ambiente. In questo modo si garantisce che tutti i dati siano isolati all'interno di tale ambiente (limite di isolamento).
Si sta creando un flusso per il reparto risorse umane. Si vuole assicurare che solo gli utenti del reparto risorse umane abbiano accesso al flusso.|Creare un ambiente e aggiungervi solo gli utenti HR. Inserire il flusso e tutte le altre risorse utilizzate dal flusso in questo ambiente.
Sono presenti utenti in Europa che usano un flusso per mostrare i dati di SharePoint.|Creare un ambiente in Europa, quindi creare il flusso e la connessione a SharePoint al suo interno. Questo ambiente europeo offre agli utenti europei prestazioni ottimali, perché tutte le risorse sono locali rispetto all'Europa (località dei dati).

Per creare gli ambienti, è necessario essere un amministratore Microsoft Flow. Gli amministratori controllano chi ha accesso agli ambienti. Per informazioni dettagliate su come è possibile creare e gestire gli ambienti, vedere l'argomento [amministrare gli ambienti](environments-overview-admin.md) .

## <a name="switching-environments"></a>Cambio di ambiente

Microsoft Flow facilita il passaggio tra gli ambienti. Quando si cambia ambiente, vengono visualizzati solo gli elementi creati in tale ambiente specifico. non sarà possibile visualizzare o accedere agli elementi in un altro ambiente.

Ecco un esempio.

È stato creato un flusso denominato *NewEmployee* nell'ambiente *risorse umane* . In [Microsoft Flow](https://flow.microsoft.com)si apre l'ambiente *Sales* . Il flusso *NewEmployee* non è elencato. Per visualizzare il flusso *NewEmployee* , aprire l'ambiente *risorse umane* . Tenere presente che le stesse regole si applicano a qualsiasi altro elemento creato nell'ambiente, incluse le connessioni, i gateway, i flussi e altro ancora.

Per cambiare ambiente, attenersi alla procedura seguente:

1. Accedere [Microsoft Flow](https://flow.microsoft.com).
1. Nell'angolo superiore destro viene visualizzata un'immagine che rappresenta il profilo.

   ![immagine del profilo](./media/environments-overview-maker/default-environment.png)

1. Selezionare l'immagine. Un elenco a discesa Visualizza tutti gli ambienti disponibili. L'ambiente in cui si è attualmente connessi è selezionato:

   ![immagine dell'elenco di ambienti](./media/environments-overview-maker/all-environments.png)
1. Per passare a un altro ambiente, selezionare l'ambiente nell'elenco:

   ![Selezionare un ambiente a cui passare](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow passa al nuovo ambiente.

## <a name="create-flows-in-the-right-environment"></a>Creare flussi nell'ambiente corretto

Prima di creare un flusso, selezionare l'ambiente in cui si aggiungerà il flusso e le relative risorse.

> [!NOTE]
> Se si crea un flusso nell'ambiente errato, sarà necessario eliminarlo e quindi crearlo nell'ambiente corretto.

Quando si sceglie un ambiente per ospitare i flussi, tenere presenti i seguenti fattori:

* È possibile creare gateway solo nell'ambiente predefinito. Se quindi si vuole usare un gateway per connettere il flusso ai dati locali, è necessario usare l'ambiente predefinito.
* I database di Microsoft Common Data Service sono collegati a un ambiente specifico. Se quindi si vuole creare un flusso che usa la Common Data Service, è necessario creare il flusso nell'ambiente che ospita il database.
* Verranno visualizzati tutti gli ambienti in cui è possibile modificare le risorse. Tuttavia, sarà necessario richiedere a un amministratore di aggiungersi come autore a tutti gli ambienti in cui si desidera creare flussi.

> [!NOTE]
> Sarà sempre possibile creare flussi nell'ambiente predefinito.

## <a name="next-steps"></a>Passaggi successivi

* [Creare un flusso da un modello](get-started-logic-template.md)
* [Creare un flusso](get-started-logic-flow.md)
* [Panoramica dell'ambiente per gli amministratori](environments-overview-admin.md)
