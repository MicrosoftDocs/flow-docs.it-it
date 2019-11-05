---
title: Automatizzare facilmente i flussi di lavoro di approvazione. | Microsoft Docs
description: Automatizza i flussi di lavoro di approvazione che si integrano con SharePoint, Dynamics CRM, Salesforce, OneDrive for business, Zendesk o WordPress.
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c46ac3dc65b6e1a3970bd0b9b4ef17df5bef16f8
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548706"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Creazione e test di un flusso di lavoro di approvazione con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Con Microsoft Flow è possibile gestire l'approvazione di documenti o processi in diversi servizi, tra cui SharePoint, Dynamics 365, Salesforce, OneDrive for business, Zendesk o WordPress.

Per creare un flusso di lavoro di approvazione, aggiungere le **approvazioni-avviare un'** azione di approvazione a qualsiasi flusso. Dopo aver aggiunto questa azione, il flusso può gestire l'approvazione di documenti o processi. È ad esempio possibile creare flussi di approvazione dei documenti che approvano fatture, ordini di lavoro o quote di vendita. È anche possibile creare flussi di approvazione del processo che approvano richieste di ferie, lavoro straordinario o piani di viaggio.

Gli approvatori possono rispondere alle richieste provenienti dalla posta in arrivo, [dal Centro approvazioni](https://flow.microsoft.com/manage/approvals/received/) nel sito Web Microsoft Flow o dall'app Microsoft Flow.

## <a name="create-an-approval-flow"></a>Creare un flusso di approvazione
Ecco una panoramica del flusso che verrà creato e testato:

   ![Panoramica di Flow](./media/modern-approvals/create-flow-overview.png)

Il flusso esegue i passaggi seguenti:

1. Viene avviato quando un utente crea una richiesta di ferie in un elenco di SharePoint Online.
2. Aggiunge la richiesta di ferie al Centro approvazioni e quindi la invia tramite posta elettronica al responsabile approvazione.
3. Invia un messaggio di posta elettronica con la decisione del responsabile approvazione per la persona che ha richiesto ferie.
4. Aggiorna l'elenco di SharePoint Online con i commenti della decisione del responsabile approvazione.

## <a name="prerequisites"></a>Prerequisiti
Per completare questa procedura dettagliata, è necessario avere accesso a:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Creare le colonne nell'elenco di SharePoint Online:

   ![Colonne elenco di SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Prendere nota del nome e dell'URL dell'elenco di SharePoint Online. Questi elementi saranno necessari in un secondo momento quando si configura il trigger **SharePoint-quando viene creato un elemento** .

## <a name="create-your-flow-from-the-blank-template"></a>Creare il flusso dal modello vuoto
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Aggiungere un trigger

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

L' **indirizzo del sito** e il **nome dell'elenco** sono gli elementi annotati in precedenza in questa procedura dettagliata.

![Informazioni su SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Aggiungere un'azione del profilo

1. Selezionare **nuovo passaggio**, quindi selezionare **Aggiungi un'azione**.
   
    ![Nuovo passaggio](./media/modern-approvals/select-sharepoint-add-action.png)
2. Immettere **profile** nella casella di ricerca **scegliere un'azione** .
   
    ![Cerca profilo](./media/modern-approvals/search-for-profile.png)
3. Trovare, quindi selezionare l'azione **utenti di Office 365-Ottieni profilo personale** .
   
    ![Seleziona utenti Office](./media/modern-approvals/select-my-profile.png)
4. Specificare un nome per il flusso e quindi selezionare **Crea flusso** per salvare il lavoro svolto finora.
   
    ![Salva flusso](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Aggiungere un'azione di approvazione

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Questa azione Invia la richiesta di approvazione all'indirizzo di posta elettronica nella casella di **assegnato a** .
>
>

## <a name="add-a-condition"></a>Aggiungere una condizione

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Aggiungere un'azione di posta elettronica per le approvazioni

Seguire questa procedura per inviare un messaggio di posta elettronica se la richiesta di ferie viene approvata:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurare il modello di posta elettronica approvato](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Aggiungere un'azione di aggiornamento per le richieste approvate

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> Sono necessari l' **indirizzo del sito**, il **nome dell'elenco**, l' **ID**e il **titolo** .
>
>

![Aggiorna configurazione elemento](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Aggiungere un'azione di posta elettronica per i rifiuti

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configurazione per le richieste rifiutate](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Aggiungere un'azione di aggiornamento per le richieste rifiutate

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > Sono necessari l' **indirizzo del sito**, il **nome dell'elenco**, l' **ID**e il **titolo** .
   >
   >

![Aggiorna scheda elemento](./media/modern-approvals/configure-update-item-no.png)

1. Selezionare **Aggiorna flusso** per salvare il lavoro svolto.
   
    ![Selezionare l'azione di aggiornamento](./media/modern-approvals/update.png)

Se è stata seguita, il flusso dovrebbe essere simile a questo screenshot:

![Panoramica di Flow](./media/modern-approvals/completed-flow.png)

Ora che è stato creato il flusso, è possibile eseguirne il test.

## <a name="request-an-approval"></a>Richiedi approvazione

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Creare approvazioni con esecuzione prolungata

Se è probabile che il flusso venga eseguito per più di 30 giorni, è consigliabile archiviare le approvazioni in Common Data Service. In questo modo è possibile creare flussi che agiscono sulle risposte alle richieste di approvazione, anche dopo il timeout dell'esecuzione del flusso originale. A tale scopo, usare due flussi, uno per inviare una richiesta di approvazione e l'altro per eseguire la logica di business sulle risposte alla richiesta di approvazione, in base all'azione **Crea un'approvazione (v2)** . Altre informazioni sulle [approvazioni con esecuzione prolungata](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/long-lived-approvals-other-approval-improvements).

>[!TIP]
> Se si usano i client di posta elettronica moderni, non è necessario chiedersi se una richiesta è ancora necessaria perché Microsoft Flow aggiorna automaticamente il messaggio di posta elettronica per indicare che l'approvazione è stata completata.

## <a name="cancel-an-approval-requests"></a>Annulla le richieste di approvazione

In alcuni casi potrebbe essere necessario annullare una richiesta di approvazione inviata. Probabilmente è stato commesso un errore nella richiesta o non è più pertinente. In entrambi i casi, la persona che ha inviato la richiesta può annullarla attenendosi alla procedura seguente:

1. Selezionare l'approvazione
1. Selezionare **Annulla approvazione** nel riquadro laterale.

>[!TIP]
>È sempre possibile selezionare la scheda **cronologia** per visualizzare le richieste di approvazione annullate.

>[!NOTE]
> La funzionalità Annulla è supportata nell'azione **Crea un'approvazione (v2)** .

## <a name="request-approvals-from-guest-users"></a>Richiedi approvazioni dagli utenti Guest

È possibile inviare le richieste di approvazione a persone all'esterno dell'organizzazione. A tale scopo, usare Azure Active Directory (Azure AD) utenti Guest [invitando gli utenti di altri tenant come](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite)Guest.

Quando si assegna un ruolo a un Guest, questo fornisce al Guest l'autorizzazione necessaria per partecipare al processo di approvazione.

Ora che è stato creato e testato il flusso, assicurarsi di consentire ad altri utenti di conoscerne l'utilizzo.

## <a name="learn-more"></a>Ulteriori informazioni

* Visualizza e gestisce [le richieste di approvazione in sospeso](approve-reject-requests.md)
* Creare [flussi di approvazione sequenziale.](sequential-modern-approvals.md)
* Creare [flussi di approvazione paralleli.](parallel-modern-approvals.md)
* Installare l'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).
