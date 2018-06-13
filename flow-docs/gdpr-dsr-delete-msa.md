---
title: Richieste di eliminazione del soggetto dei dati GDPR in Microsoft Flow per account del servizio gestito Microsoft (MSA) | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di eliminazione del soggetto dei dati GPDR per gli account Microsoft.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
ms.openlocfilehash: c7bede08503fc1c009f07201f98e1a2197251bda
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563103"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Rispondere alle richieste di eliminazione del soggetto dei dati GPDR

Il **diritto alla cancellazione** con rimozione dei dati personali è una protezione chiave nel regolamento GDPR. La rimozione dei dati personali include la rimozione di tutti i dati personali tranne le informazioni del log di controllo.

Microsoft Flow consente agli utenti di creare flussi di lavoro automatizzati. Quando un utente sceglie di eliminare i dati personali da Microsoft Flow, può leggere i dati personali e decidere se eliminarne alcuni o eliminarli tutti.

La tabella seguente visualizza i dati personali che vengono eliminati automaticamente e quelli che devono essere verificati ed eliminati manualmente da un utente di account del servizio gestito Microsoft (MSA).

|Richiede l'eliminazione da parte dell'utente dell'account Microsoft|Eliminato automaticamente|
|------|------|
|Attività con prodotti e servizi|Cronologia di esecuzione|
|Flussi|Feed attività|
|Connessioni||

Microsoft Flow offre le esperienze seguenti per aiutare gli utenti a trovare o modificare i dati e le risorse personali che non vengono eliminate automaticamente:

## <a name="manage-delete-requests"></a>Gestire le richieste di eliminazione

La procedura self-service seguente descrive come gestire le richieste di eliminazione per il regolamento GDPR.

### <a name="delete-product-and-service-activity"></a>Eliminare attività con prodotti e servizi

1. Accedere al [dashboard di privacy di Microsoft](https://account.microsoft.com/privacy/) con l'account Microsoft.
1. Selezionare il collegamento **Cronologia attività**.

    ![Cronologia attività](./media/gdpr-dsr-export-msa/activityhistory.png)

1. È possibile cercare o sfogliare la cronologia attività per i servizi e le applicazioni Microsoft usate, tra cui Microsoft Flow. Selezionare **Elimina** per rimuovere eventi attività per prodotti o servizi specifici.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Dopo qualche istante l'elemento viene eliminato e rimosso dal dashboard di privacy.

### <a name="list-and-delete-flows"></a>Elencare ed eliminare i flussi

Un utente può visualizzare l'elenco dei flussi personali ed eliminarli da [Microsoft Flow](https://flow.microsoft.com) seguendo questa procedura:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com) e selezionare **Flussi personali**.

1. Selezionare **...** accanto al flusso che si vuole eliminare e quindi selezionare **Elimina**.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Eliminare le connessioni

I connettori usano le connessioni per comunicare con le API e i sistemi SaaS. Le connessioni includono riferimenti all'utente che le ha create. L'utente può eliminare i riferimenti in qualsiasi momento seguendo questa procedura:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com), selezionare l'icona a forma di ingranaggio e quindi selezionare **Connessioni**.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Selezionare la connessione che si vuole eliminare, selezionare **...** e quindi selezionare **Elimina**.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Selezionare l'icona **Elimina** nella richiesta di conferma.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Se la connessione che si sta eliminando è usata da altri flussi, una notifica segnala che è necessaria una nuova connessione. In caso contrario, selezionare **Elimina** per continuare.
>
>

## <a name="learn-more"></a>Altre informazioni

* Attività iniziali con [Microsoft Flow](getting-started.md)
* Informazioni sulle [novità](release-notes.md) di Microsoft Flow
