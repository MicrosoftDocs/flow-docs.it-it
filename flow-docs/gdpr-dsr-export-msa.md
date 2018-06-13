---
title: Richieste di esportazione del soggetto dei dati GDPR in Microsoft Flow per account del servizio gestito Microsoft (MSA) | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di esportazione del soggetto dei dati GPDR per gli account Microsoft.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
ms.openlocfilehash: 6c1bf3038020f56e5eae57e345391ace2fe65d7f
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563115"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Risposta alle richieste di esportazione del soggetto dei dati GDPR per Microsoft Flow

Come parte dell'impegno di Microsoft a collaborare con i clienti per soddisfare i requisiti del Regolamento generale sulla protezione dei dati (GDPR), è stata redatta la documentazione per agevolare i preparativi. La documentazione non solo descrive cosa sta facendo Microsoft per prepararsi per il regolamento GDPR, ma include anche esempi delle misure che è possibile adottare sin da subito con Microsoft per il supporto della conformità a GDPR quando si usa Microsoft Flow.

## <a name="manage-export-requests"></a>Gestire le richieste di esportazione

Il *diritto alla portabilità dei dati* consente a un soggetto dei dati di richiedere una copia dei dati personali in formato elettronico (ovvero un "formato strutturato, di uso comune, leggibile da computer e interoperabile") che può essere trasmessa a un altro titolare del trattamento dei dati.

Usare il [dashboard di privacy di Microsoft](https://account.microsoft.com/privacy/) o [Microsoft Flow](https://flow.microsoft.com/) per trovare o esportare i dati personali per un utente specifico.

|Dati personali|Posizione|
|-----------------|-------------------|
|Attività con prodotti e servizi|Dashboard di privacy di Microsoft|
|Flussi|Portale per gli autori di Microsoft Flow|
|Cronologia di esecuzione|Portale per gli autori di Microsoft Flow|
|Feed attività|Portale per gli autori di Microsoft Flow|
|Connessioni|Portale per gli autori di Microsoft Flow|

## <a name="export-product-and-service-activity"></a>Esportare attività con prodotti e servizi

1. Accedere al [dashboard di privacy di Microsoft](https://account.microsoft.com/privacy/) usando l'account del servizio gestito Microsoft (MSA).
1. Selezionare **Cronologia attività**.

    In ![Cronologia attività](./media/gdpr-dsr-export-msa/activityhistory.png) è possibile cercare o sfogliare la cronologia attività per i servizi e le applicazioni Microsoft usate.
1. Per esportare i dati di **Attività con prodotti e servizi** selezionare **Download your data** (Scarica i dati), quindi selezionare **CREATE NEW ARCHIVE** (CREA NUOVO ARCHIVIO).

    ![Scaricare i dati](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Selezionare **App & service usage** (Uso di app e servizi), quindi selezionare **Crea archivio**.

    ![Scaricare i dati](./media/gdpr-dsr-export-msa/create-archive.png)
1. Viene creato un nuovo archivio. Selezionare **Scarica** per ottenere l'esportazione dei dati delle attività con prodotti e servizi.

    ![Scarica](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Esportare un flusso

Un utente finale che dispone di accesso a un flusso può esportare il flusso seguendo questa procedura:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com/).

1. Selezionare **Flussi personali** e quindi selezionare il flusso da esportare.

1. Selezionare **Altro** e quindi selezionare **Esporta**.

    ![Esportare il flusso](./media/gdpr-dsr-export/export-flow.png)

1. Selezionare **Pacchetto (ZIP)**.

Il flusso sarà ora disponibile come pacchetto compresso. Per altre informazioni, vedere il post di blog su [come esportare e importare un flusso](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Esportare la cronologia di esecuzione

La cronologia di esecuzione include un elenco di tutte le esecuzioni di un flusso. Questi dati includono lo stato, l'ora di inizio, la durata e i dati di input/output per azioni e trigger del flusso.

Un utente finale che dispone di accesso al flusso può esportare i dati seguendo questa procedura:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com/).
1. Selezionare il collegamento **Flussi personali** e quindi selezionare il flusso per il quale si vuole esportare la cronologia di esecuzione.
1. Nel riquadro **Cronologia esecuzioni** selezionare **Visualizza tutto**.

    ![Cronologia di esecuzione](./media/gdpr-dsr-export/run-history.png)

1. Selezionare **Scarica CSV**.

    ![Scarica CSV](./media/gdpr-dsr-export/download-csv.png)

La cronologia di esecuzione viene scaricata come file con estensione csv ed è possibile aprire il file in Microsoft Excel o in un editor di testo per analizzare i risultati.

## <a name="export-a-users-activity-feed"></a>Esportare il feed attività di un utente

In [Microsoft Flow](https://flow.microsoft.com/) il feed attività mostra la cronologia di attività, errori e notifiche di un utente. Un utente può visualizzare il feed attività personale seguendo questa procedura:

1. Accedere a [Microsoft Flow](http://flow.microsoft.com/), selezionare l'icona a forma di campanello nell'angolo superiore destro e quindi selezionare **Mostra tutta l'attività**.

    ![Visualizzare il feed attività](./media/gdpr-dsr-export/show-activity-feed.png)

1. Nella schermata **Attività** copiare i risultati e quindi incollarli in un editor di testo, ad esempio Microsoft Word.

    ![Visualizzare il feed attività](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Esportare le connessioni di un utente

Le connessioni consentono ai flussi di connettersi ad API, applicazioni SaaS e altri sistemi di terze parti. Seguire questa procedura per visualizzare le connessioni:

1. Accedere a [Microsoft Flow](http://flow.microsoft.com/), selezionare l'icona a forma di ingranaggio in prossimità dell'angolo superiore destro e quindi selezionare **Connessioni**.

    ![Visualizzare le connessioni](./media/gdpr-dsr-export/show-connections.png)
1. Copiare i risultati e incollarli in un editor di testo, ad esempio Microsoft Word.
