---
title: Richieste di chiusura dell'account del soggetto dei dati GDPR in Microsoft Flow per account del servizio gestito Microsoft (MSA) | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di chiusura dell'account del soggetto dei dati GPDR per gli account Microsoft.
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
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: be12491490cac51a0b91906b1a663522c2a7658f
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688767"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Risposta alle richieste di chiusura dell'account del soggetto dei dati GDPR per Microsoft Flow

Il **diritto alla cancellazione** dei dati personali è una protezione chiave nel regolamento GDPR. Questo diritto include la rimozione di tutti i dati personali tranne le informazioni del log di controllo. Quando un utente sceglie di chiudere il proprio account del servizio gestito Microsoft (MSA), vengono eliminati anche i dati dell'utente sottostanti.

Le seguenti risorse contengono dati personali che vengono eliminati automaticamente quando un utente chiude un account del servizio gestito Microsoft (MSA):

|Risorse contenenti dati personali|
|------|
|Attività con prodotti e servizi|
|Cronologia di esecuzione|
|Flussi|
|Feed attività|
|Dettagli utente|
|Connessioni|

## <a name="account-close-requests"></a>Richieste di chiusura account

La procedura self-service seguente descrive come gestire le richieste di chiusura account per il regolamento GDPR.

1. Accedere alla sezione [Chiudi l'account](http://go.microsoft.com/fwlink/?LinkId=523898) del portale Microsoft con l'account Microsoft e selezionare **Avanti**.

    > [!NOTE]
    > Un messaggio ricorda di eliminare le sottoscrizioni esistenti o di esportare i dati dai servizi esistenti ai quali è stata effettuata la sottoscrizione.
    >
    >

    ![Annullare le sottoscrizioni](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confermare di aver compreso gli effetti della chiusura dell'account e selezionare **Contrassegna l'account per la chiusura**.

    Una notifica indica che l'account verrà chiuso tra 30 giorni. È possibile riaprire l'account in qualsiasi momento durante questo periodo di 30 giorni.

    ![Account chiuso](./media/gdpr-dsr-delete-msa/accountclosed.png)

    Al termine di questo periodo di 30 giorni inizia il processo di eliminazione di tutte le risorse Microsoft Flow per questo account del servizio gestito Microsoft (MSA).

## <a name="learn-more"></a>Altre informazioni

* Attività iniziali con [Microsoft Flow](getting-started.md)
* Informazioni sulle [novità](release-notes.md) di Microsoft Flow
