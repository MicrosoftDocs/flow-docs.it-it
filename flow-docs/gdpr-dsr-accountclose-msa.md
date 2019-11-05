---
title: Microsoft Flow GDPR richieste di chiusura dell'account oggetto dati per gli account Microsoft (MSA) | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di chiusura dell'account del soggetto dei dati alle GPDR per gli account Microsoft.
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
ms.openlocfilehash: 8665148baf4d752f1f384670b296a66bbfca6163
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548015"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Risposta alle richieste di chiusura dell'account del soggetto dei dati GDPR per Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Il **diritto di** cancellare i dati personali è una protezione chiave nella GDPR. Questo diritto include la rimozione di tutti i dati personali eccetto le informazioni sul log di controllo. Quando gli utenti decidono di chiudere il proprio account Microsoft (MSA), vengono eliminati anche i dati sottostanti dell'utente.

Queste risorse contengono dati personali che vengono eliminati automaticamente quando un utente chiude un MSA:

|Risorse contenenti dati personali|
|------|
|Attività del prodotto e del servizio|
|cronologia di esecuzione|
|Flussi|
|Feed attività|
|Dettagli utente|
|Connessioni|

## <a name="account-close-requests"></a>Richieste di chiusura dell'account

Questi passaggi descrivono come gestire in modo autonomo le richieste di chiusura dell'account per GDPR.

1. Accedere al [portale di chiusura dell'account Microsoft](https://go.microsoft.com/fwlink/?LinkId=523898) usando il proprio account Microsoft e quindi fare clic su **Avanti**.

    > [!NOTE]
    > Si ricorda di annullare le sottoscrizioni esistenti o di esportare i dati dai servizi esistenti a cui è stata effettuata la sottoscrizione.
    >
    >

    ![Annulla sottoscrizioni](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confermare di aver compreso l'effetto della chiusura di MSA, quindi selezionare **Mark account per la chiusura**.

    Viene visualizzata una notifica che indica che l'account verrà chiuso entro 30 giorni. È possibile riaprire l'account in qualsiasi momento durante questo periodo di 30 giorni.

    ![Account chiuso](./media/gdpr-dsr-delete-msa/accountclosed.png)

    Alla fine di questo intervallo di 30 giorni, inizia il processo di eliminazione di tutte le risorse Microsoft Flow per questo MSA.

## <a name="learn-more"></a>Ulteriori informazioni

* Inizia a usare [Microsoft Flow](getting-started.md)
* Scopri le [novità](release-notes.md) di Microsoft Flow
