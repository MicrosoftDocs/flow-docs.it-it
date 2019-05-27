---
title: Informazioni sugli ambienti di Microsoft Flow | Microsoft Docs
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
ms.openlocfilehash: 0e6b410f75f28ba13357878a5cda178bc66b69ff
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460831"
---
# <a name="choosing-an-environment"></a>Scelta di un ambiente

Questo articolo presenta gli **ambienti** di Microsoft Flow in cui è possibile creare e isolare in modo sicuro i flussi, i gateway, le connessioni e altre risorse.

Sono disponibili le informazioni seguenti:

* Funzionalità fornite dagli ambienti.
* Passaggio da un ambiente all'altro.
* Come creare un flusso nell'ambiente appropriato.

## <a name="environments-overview"></a>Panoramica degli ambienti

Quando si crea un flusso, è possibile scegliere un ambiente che dovrà ospitarlo e le risorse usate dal flusso. È possibile usare ambienti separati per scenari diversi.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Ecco alcuni scenari per l'uso degli ambienti

Scenario|Raccomandazione
-----|-----
Si vuole creare un flusso che usa una connessione a Microsoft Common Data Service.|Posizionare il flusso e Common Data Service nello stesso ambiente. Ciò garantisce l'isolamento di tutti i dati all'interno dell'ambiente (limite di isolamento).
È in corso la creazione di un flusso per il reparto Risorse umane. Si vuole avere la certezza che tale flusso sia accessibile soltanto agli utenti di questo reparto.|Creare un ambiente e aggiungervi solo le risorse del reparto Risorse umane. Posizionare il flusso e altre risorse usate dal flusso in questo ambiente.
Alcuni utenti in Europa usano un flusso per mostrare i dati di SharePoint.|Creare un ambiente in Europa e quindi creare il flusso e la connessione a SharePoint in tale ambiente. L'ambiente creato in Europa offre prestazioni migliori agli utenti in quest'area geografica, dal momento che tutte le risorse si trovano in Europa (principio di località dei dati).

Per creare ambienti, è necessario essere un amministratore di Microsoft Flow. Gli amministratori determinano quali utenti possono accedere agli ambienti. Per dettagli su come creare e gestire gli ambienti, vedere l'argomento [Amministrare gli ambienti](environments-overview-admin.md).

## <a name="switching-environments"></a>Passaggio da un ambiente all'altro

Microsoft Flow facilita il passaggio da un ambiente all'altro. Quando si passa da un ambiente all'altro vengono visualizzati solo gli elementi creati nell'ambiente specifico. Non sarà possibile visualizzare o accedere a elementi in altri ambienti.

Di seguito è riportato un esempio.

È stato creato un flusso denominato *NuovoDipendente* nell'ambiente *Risorse umane*. In [Microsoft Flow](https://flow.microsoft.com) aprire l'ambiente *Vendite*. Il flusso *NuovoDipendente* non è elencato. Per visualizzare il flusso *Nuovo_dipendente*, aprire l'ambiente *Risorse umane*. Occorre ricordare che le stesse regole sono applicabili a qualsiasi altro elemento creato nell'ambiente, ad esempio connessioni, gateway, flussi e altro ancora.

Per passare da un ambiente all'altro, seguire questa procedura:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com).
1. Nell'angolo superiore destro viene visualizzata un'immagine che rappresenta il profilo specifico.

   ![Immagine del profilo](./media/environments-overview-maker/default-environment.png)

1. Selezionare l'immagine. Un elenco a discesa mostra tutti gli ambienti disponibili. L'ambiente a cui si è attualmente connessi è selezionato:

   ![Immagine con l'elenco di ambienti](./media/environments-overview-maker/all-environments.png)
1. Per passare a un altro ambiente, selezionarlo nell'elenco:

   ![Selezionare un ambiente a cui passare](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow passa al nuovo ambiente.

## <a name="create-flows-in-the-right-environment"></a>Creare i flussi nell'ambiente appropriato

Prima di creare un flusso, selezionare l'ambiente in cui aggiungere il flusso e le rispettive risorse.

> [!NOTE]
> Se si crea un flusso nell'ambiente errato, sarà necessario eliminarlo e quindi crearlo nell'ambiente corretto.

Quando si sceglie un ambiente in cui ospitare i flussi, prendere in considerazione i fattori seguenti:

* È possibile creare gateway solo nell'ambiente predefinito. Se si vuole usare un gateway per la connessione del flusso ai dati locali, sarà quindi necessario usare l'ambiente predefinito.
* I database di Microsoft Common Data Service sono associati a un ambiente specifico. Se si vuole creare un flusso che usa Common Data Service, è quindi necessario creare il flusso nell'ambiente che ospita il database.
* Verranno visualizzati tutti gli ambienti in cui è possibile modificare le risorse. Sarà tuttavia necessario richiedere a un amministratore di essere aggiunti come autore a tutti gli ambienti in cui si vogliono creare flussi.

> [!NOTE]
> Sarà sempre possibile creare flussi nell'ambiente predefinito.

## <a name="next-steps"></a>Passaggi successivi

* [Creare un flusso da un modello](get-started-logic-template.md)
* [Creare un flusso](get-started-logic-flow.md)
* [Panoramica sull'ambiente per gli amministratori](environments-overview-admin.md)
