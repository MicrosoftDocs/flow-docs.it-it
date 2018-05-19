---
title: Automatizzare con facilità i flussi di lavoro di approvazione. | Microsoft Docs
description: Automatizzare i flussi di lavoro di approvazione che si integrano con SharePoint, Dynamics CRM, Salesforce, OneDrive for Business, Zendesk o WordPress.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
ms.openlocfilehash: bd89bca994a77072815a73ba1cbc7ba1db6955d3
ms.sourcegitcommit: e52f04b5953240d71d726c0e3373740cc59292dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2018
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Creare e testare un flusso di lavoro di approvazione con Microsoft Flow

Con Microsoft Flow, è possibile gestire l'approvazione dei documenti o dei processi in diversi servizi, inclusi SharePoint, Dynamics CRM, Salesforce, OneDrive for Business, Zendesk o WordPress.

Per creare un flusso di lavoro di approvazione, aggiungere l'azione **Approvals - Start an approval** (Approvazioni - Avvia un'approvazione) a qualsiasi flusso. Dopo l'aggiunta di questa azione, il flusso può gestire l'approvazione di documenti o processi. Ad esempio, è possibile creare un flusso di approvazione documenti che approva fatture, ordini di lavoro oppure preventivi di vendita. È anche possibile creare un flusso di approvazione processi che approva richieste di ferie, lavoro straordinario o piani di viaggio.

Gli approvatori possono rispondere alle richieste dalla propria cartella di posta in arrivo, dal [centro approvazioni](https://flow.microsoft.com/manage/approvals/received/) nel sito Web di Microsoft Flow o dall'app di Microsoft Flow.

## <a name="create-an-approval-flow"></a>Creare un flusso di approvazione
Ecco una panoramica del flusso che verrà creato e testato:

   ![panoramica del flusso](./media/modern-approvals/create-flow-overview.png)

Il flusso esegue i passaggi seguenti:

1. Inizia quando un utente crea una richiesta di ferie in un elenco di SharePoint Online.
2. Aggiunge la richiesta di ferie al Centro approvazioni, quindi la invia tramite posta elettronica al responsabile approvazione.
3. Invia un messaggio di posta elettronica con la decisione del responsabile approvazione all'utente che ha richiesto le ferie.
4. Aggiorna l'elenco di SharePoint Online con i commenti relativi alla decisione del responsabile approvazione.

## <a name="prerequisites"></a>Prerequisiti
Per completare questa procedura dettagliata, è necessario avere accesso a:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Creare queste colonne nell'elenco di SharePoint Online:

   ![Colonne dell'elenco di SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Annotare il nome e l'URL dell'elenco di SharePoint Online. Questi elementi serviranno in un secondo momento per configurare il trigger**SharePoint - Quando viene creato un elemento**.

## <a name="create-your-flow-from-the-blank-template"></a>Creare il flusso dal modello vuoto
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Aggiungere un trigger

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

**Indirizzo sito** e **Nome elenco** sono le voci annotate in precedenza.

![Informazioni su SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Aggiungere un'azione profilo

1. Selezionare **Nuovo passaggio**, quindi scegliere **Aggiungi un'azione**.
   
    ![nuovo passaggio](./media/modern-approvals/select-sharepoint-add-action.png)
2. Immettere **profilo** nella casella di ricerca **Scegliere un'azione**.
   
    ![ricerca profilo](./media/modern-approvals/search-for-profile.png)
3. Trovare e selezionare l'azione **Office 365 Users - Get my profile** (Utenti di Office 365 - Ottieni profilo personale)
   
    ![selezionare utenti di office](./media/modern-approvals/select-my-profile.png)
4. Specificare un nome per il flusso e selezionare **Crea flusso** per salvare il lavoro svolto finora.
   
    ![salvare flusso](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Aggiungere un'azione di approvazione

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Questa azione invia la richiesta di approvazione all'indirizzo di posta elettronica indicato nella casella **Assegnato a**.
>
>

## <a name="add-a-condition"></a>Aggiungere una condizione

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Aggiungere un'azione di posta elettronica per le approvazioni

Seguire questa procedura per inviare un messaggio di posta elettronica in caso di approvazione della richiesta di ferie:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurare il modello di posta elettronica per le approvazioni](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Aggiungere un'azione di aggiornamento per le richieste approvate

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> I campi **Indirizzo del sito**, **Nome lista**, **ID** e **Titolo** sono obbligatori.
>
>

![aggiornare la configurazione dell'elemento](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Aggiungere un'azione di posta elettronica per le richieste rifiutate

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configurazione delle richieste rifiutate](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Aggiungere l'azione di aggiornamento per le richieste rifiutate

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > I campi **Indirizzo del sito**, **Nome lista**, **ID** e **Titolo** sono obbligatori.
   >
   >

![aggiornare scheda elemento](./media/modern-approvals/configure-update-item-no.png)

1. Selezionare **Aggiorna flusso** per salvare il lavoro svolto.
   
    ![selezionare azione di aggiornamento](./media/modern-approvals/update.png)

Se tutti i passaggi sono stati eseguiti correttamente, il flusso sarà simile alla schermata seguente:

![panoramica del flusso](./media/modern-approvals/completed-flow.png)

Dopo aver creato il flusso, è opportuno testarlo.

## <a name="request-an-approval"></a>Richiedere un'approvazione

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Dopo avere creato e testato il flusso, occorre assicurarsi di illustrarne il funzionamento agli altri utenti.

## <a name="learn-more"></a>Altre informazioni

* Visualizzare e gestire le [richieste di approvazione in sospeso](approve-reject-requests.md)
* Creare [flussi di approvazione sequenziali](sequential-modern-approvals.md).
* Creare [flussi di approvazione paralleli](parallel-modern-approvals.md).
* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).
