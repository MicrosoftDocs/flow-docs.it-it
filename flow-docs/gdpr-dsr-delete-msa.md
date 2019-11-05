---
title: Richieste di eliminazione del soggetto dei dati Microsoft Flow GDPR per gli account Microsoft (MSA) | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di eliminazione del soggetto dei dati alle GPDR per gli account Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 379c88842b9724c7bdb6adfed79e2bb11497694d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548048"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Rispondere alle richieste di eliminazione del soggetto dei dati GDPR
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Il **diritto di cancellarsi** dalla rimozione dei dati personali è una protezione chiave nella GDPR. La rimozione dei dati personali include la rimozione di tutti i dati personali eccetto le informazioni sul log di controllo.

Microsoft Flow consente agli utenti di creare flussi di lavoro automatizzati. Quando un utente decide di eliminare i dati personali da Microsoft Flow, l'utente può esaminare i dati personali e determinare se eliminarne alcuni o tutti.

La tabella seguente illustra i dati personali che vengono eliminati automaticamente e i dati necessari a un utente di un account Microsoft (MSA) per esaminarli ed eliminarli.

|Richiede che l'utente MSA riveda ed elimini|Eliminata automaticamente|
|------|------|
|Attività del prodotto e del servizio|cronologia di esecuzione|
|Flussi|Feed attività|
|Connessioni||

Microsoft Flow offre le seguenti esperienze per aiutare gli utenti a trovare, rivedere o modificare i dati personali e le risorse che non vengono eliminate automaticamente:

## <a name="manage-delete-requests"></a>Gestisci richieste di eliminazione

I passaggi seguenti descrivono come gestire in modo autonomo le richieste di eliminazione per GDPR.

### <a name="delete-product-and-service-activity"></a>Elimina attività prodotto e servizio

1. Accedere al [Dashboard della privacy di Microsoft](https://account.microsoft.com/privacy/) con il servizio MSA.
1. Selezionare il collegamento **Cronologia attività** .

    ![Cronologia attività](./media/gdpr-dsr-export-msa/activityhistory.png)

1. È possibile cercare o esplorare la cronologia delle attività per i diversi servizi e applicazioni Microsoft usati, incluso Microsoft Flow. Selezionare **Elimina** per rimuovere gli eventi specifici relativi al prodotto o all'attività del servizio.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Entro pochi istanti, l'elemento viene eliminato e rimosso dal dashboard della privacy.

### <a name="list-and-delete-flows"></a>Elencare ed eliminare i flussi

Un utente può elencare ed eliminare i flussi da [Microsoft Flow](https://flow.microsoft.com) follwing questi passaggi:

1. Accedere al [Microsoft Flow](https://flow.microsoft.com)e quindi selezionare sui **flussi personali**.

1. Selezionare **...** accanto al flusso da eliminare e quindi selezionare **Elimina**.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Elimina connessioni

I connettori usano le connessioni per comunicare con le API e i sistemi SaaS. Le connessioni includono riferimenti all'utente che le crea. L'utente può eliminare questi riferimenti in qualsiasi momento follwing i passaggi seguenti:

1. Accedere [Microsoft Flow](https://flow.microsoft.com), selezionare l'icona a forma di ingranaggio e quindi selezionare **connessioni**.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Selezionare la connessione che si desidera eliminare, selezionare **...** e quindi selezionare **Elimina**.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Selezionare l'icona **Elimina** nella richiesta di conferma.

    ![Elimina evento](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Se altri flussi usano la connessione, si sta eliminando, viene visualizzata una notifica che indica che è necessaria una nuova connessione. In caso contrario, selezionare **Elimina** per continuare.
>
>

## <a name="learn-more"></a>Ulteriori informazioni

* Inizia a usare [Microsoft Flow](getting-started.md)
* Scopri le [novità](release-notes.md) di Microsoft Flow
