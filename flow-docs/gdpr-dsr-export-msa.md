---
title: Microsoft Flow richieste di esportazione del soggetto dei dati GDPR per gli account Microsoft (MSA) | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di esportazione del soggetto dei dati alle GPDR per gli account Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 253d6785228fb28b5c78d0cae629a237a2e176da
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548140"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Risposta alle richieste di esportazione del soggetto dei dati GDPR per Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Nell'ambito del nostro impegno per collaborare con il tuo viaggio verso la Regolamento generale sulla protezione dei dati (GDPR), abbiamo sviluppato la documentazione per aiutarti a prepararti. La documentazione non solo descrive cosa si sta preparando per la GDPR, ma condivide anche esempi di passaggi che è possibile eseguire oggi con Microsoft per supportare la conformità GDPR quando si usa Microsoft Flow.

## <a name="manage-export-requests"></a>Gestire le richieste di esportazione

Il *diritto di portabilità dei dati* consente agli oggetti dati di richiedere una copia dei dati personali in formato elettronico, ovvero un formato "strutturato, comunemente utilizzato, leggibile da computer e interoperabile", che può essere trasmesso a un altro controller di dati.

Usare [Microsoft Privacy dashboard](https://account.microsoft.com/privacy/)o [Microsoft Flow](https://flow.microsoft.com/) per trovare o esportare i dati personali per un utente specifico.

|Dati personali|Percorso|
|-----------------|-------------------|
|Attività del prodotto e del servizio|Dashboard privacy Microsoft|
|Flussi|Portale di Microsoft Flow Maker|
|cronologia di esecuzione|Portale di Microsoft Flow Maker|
|Feed attività|Portale di Microsoft Flow Maker|
|Connessioni|Portale di Microsoft Flow Maker|

## <a name="export-product-and-service-activity"></a>Esporta attività prodotto e servizio

1. Accedere al [Dashboard della privacy di Microsoft](https://account.microsoft.com/privacy/) usando il proprio account Microsoft (MSA).
1. Selezionare **Cronologia attività**.

    ![cronologia attività](./media/gdpr-dsr-export-msa/activityhistory.png) è possibile esplorare la cronologia delle attività per le diverse applicazioni e i servizi Microsoft utilizzati.
1. Per esportare i dati relativi alle **attività di prodotti e servizi** , selezionare **Scarica i dati**, quindi selezionare **Crea nuovo archivio**.

    ![Scaricare i dati](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Selezionare **App & Service Usage**, quindi selezionare **Crea archivio**.

    ![Scaricare i dati](./media/gdpr-dsr-export-msa/create-archive.png)
1. Viene creato un nuovo archivio. Selezionare **download** per ottenere i dati esportati relativi al prodotto e all'attività del servizio.

    ![Scaricare](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Esportare un flusso

Un utente finale che ha accesso a un flusso può esportare il flusso attenendosi alla procedura seguente:

1. Accedere [Microsoft Flow](https://flow.microsoft.com/).

1. Selezionare **flussi personali**e quindi selezionare il flusso da esportare.

1. Seleziona **... Altro**, quindi selezionare **Esporta**.

    ![Esporta flusso](./media/gdpr-dsr-export/export-flow.png)

1. Selezionare **pacchetto (zip)** .

Il flusso sarà ora disponibile come pacchetto compresso. Per altre informazioni, vedere il post di Blog su [come esportare e importare un flusso](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Esporta cronologia di esecuzione

La cronologia di esecuzione include un elenco di tutte le esecuzioni per un flusso. Questi dati includono lo stato del flusso, l'ora di inizio, la durata e i dati di input/output per i trigger e le azioni.

Un utente finale che ha accesso al flusso può seguire questa procedura per esportare i dati:

1. Accedere [Microsoft Flow](https://flow.microsoft.com/).
1. Selezionare il collegamento **flussi personali** e quindi selezionare il flusso per il quale si vuole esportare la cronologia di esecuzione.
1. Nel riquadro **cronologia di esecuzione** selezionare **Visualizza tutto**.

    ![cronologia di esecuzione](./media/gdpr-dsr-export/run-history.png)

1. Selezionare **Scarica CSV**.

    ![Scarica CSV](./media/gdpr-dsr-export/download-csv.png)

La cronologia di esecuzione viene scaricata come file con estensione CSV in modo che sia possibile aprirla in Microsoft Excel o in un editor di testo per analizzare i risultati.

## <a name="export-a-users-activity-feed"></a>Esportare il feed attività di un utente

In [Microsoft Flow](https://flow.microsoft.com/)il feed attività Mostra la cronologia di un utente di attività, errori e notifiche. Gli utenti possono visualizzare il proprio feed attività attenendosi alla procedura seguente:

1. Accedere [Microsoft Flow](https://flow.microsoft.com/), selezionare l'icona a forma di campana nell'angolo in alto a destra, quindi selezionare **Mostra tutte le attività**.

    ![Mostra feed attività](./media/gdpr-dsr-export/show-activity-feed.png)

1. Nella schermata **Activity (attività** ) copiare i risultati e quindi incollarli in un editor di testo, ad esempio Microsoft Word.

    ![Mostra feed attività](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Esportare le connessioni di un utente

Le connessioni consentono ai flussi di connettersi alle API, alle applicazioni SaaS e ad altri sistemi di terze parti. Per visualizzare le connessioni, attenersi alla procedura seguente:

1. Accedere [Microsoft Flow](https://flow.microsoft.com/), selezionare l'icona a forma di ingranaggio nell'angolo in alto a destra e quindi selezionare **connessioni**.

    ![Mostra connessioni](./media/gdpr-dsr-export/show-connections.png)
1. Copiare i risultati e quindi incollarli in un editor di testo, ad esempio Microsoft Word.
