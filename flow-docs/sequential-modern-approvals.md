---
title: Creare un flusso di lavoro di approvazione moderno con più responsabili approvazione | Microsoft Docs
description: 'Creare un flusso di lavoro di approvazione moderno con più responsabili approvazione '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
ms.openlocfilehash: 8620cd49f9e19f6641909fcab3103568d148e565
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "23442315"
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Gestire le approvazioni sequenziali con Microsoft Flow
Alcuni flussi di lavoro richiedono l'approvazione preliminare prima che il responsabile approvazione finale debba disconnettersi. Ad esempio, una società potrebbe avere un criterio di approvazione sequenziale che richieda l'approvazione preliminare per le fatture di importo superiore a €1.000 prima che siano approvate dal reparto finanziario.

In questa procedura dettagliata viene creato un flusso di lavoro di approvazione sequenziale che gestisce le richieste di ferie dei dipendenti.

## <a name="detailed-steps-in-the-flow"></a>Procedura dettagliata nel flusso
Il flusso:

1. Inizia quando un dipendente crea una richiesta di ferie in un [elenco di SharePoint Online](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
2. Aggiunge la richiesta di ferie al Centro approvazioni, quindi invia tramite posta elettronica la richiesta al responsabile approvazione preliminare.
3. Invia tramite posta elettronica la decisione di approvazione preliminare al dipendente.
4. Aggiorna l'elenco di SharePoint Online con la decisione e i commenti del responsabile approvazione preliminare.
   
   Nota: se la richiesta viene preapprovata, il flusso procede con questi passaggi:
5. Invia la richiesta al responsabile approvazione finale.
6. Invia tramite posta elettronica la decisione finale al dipendente.
7. Aggiorna l'elenco di SharePoint con la decisione finale.

Questa immagine riepiloga i passaggi precedenti:

   ![diagramma visio del flusso](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Prerequisiti
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

L'elenco di SharePoint Online creato dall'utente deve includere le colonne seguenti:

   ![Colonne elenco di SharePoint](./media/sequential-modern-approvals/sharepoint-columns.png)

Annotare il nome e l'URL dell'elenco di SharePoint Online. Questi elementi verranno usati in un secondo momento per configurare il trigger **SharePoint - Quando viene creato un nuovo elemento**.

## <a name="create-your-flow-from-the-blank-template"></a>Creare il flusso dal modello vuoto
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Aggiungere un trigger
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![informazioni di SharePoint](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Recuperare il responsabile per la persona che ha creato la richiesta di ferie
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Specificare un nome per il flusso e selezionare **Crea flusso** per salvare il lavoro svolto finora.
   
    ![salvare flusso](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Selezionare periodicamente **Aggiorna flusso** nella parte superiore dello schermo per salvare le modifiche apportate al flusso.
   > 
   > 
   
    ![selezionare azione di aggiornamento](./media/sequential-modern-approvals/update.png)

Dopo ogni operazione di salvataggio, selezionare **Modifica flusso** nella parte superiore dello schermo e quindi continuare ad apportare modifiche.

## <a name="add-an-approval-action-for-pre-approvals"></a>Aggiungere un'azione di approvazione per le approvazioni preliminari
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Nota: questa azione invia la richiesta di approvazione preliminare all'indirizzo e-mail indicato nella casella **Assegnato a**.

## <a name="add-a-condition"></a>Aggiungere una condizione
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Questa condizione controlla la risposta dell'azione **Avviare un'approvazione**.
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Aggiungere un'azione di posta elettronica per le approvazioni preliminari
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurare il modello di posta elettronica preapprovato](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Aggiungere un'azione di aggiornamento per le richieste preapprovate
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![aggiornare la configurazione dell'elemento](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Recuperare il responsabile del responsabile approvazione
1. Seguire la procedura [Recupera il responsabile per la persona che ha creato la richiesta di ferie](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) eseguita in precedenza per aggiungere e quindi configurare un'altra azione **Recupera il responsabile**. Stavolta, si recupererà il responsabile del responsabile approvazione.
2. Al termine, la scheda **Recupera il responsabile 2** dovrebbe avere il seguente aspetto. Assicurarsi di usare il token **Posta elettronica** dalla categoria **Recupera il responsabile** nella scheda **Aggiunge il contenuto dinamico dalle app e dai servizi usati in questo flusso**.
   
   ![recuperare il responsabile del responsabile approvazione](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Aggiungere l'azione di approvazione finale
1. Seguire la procedura per [aggiungere un'azione di approvazione per le approvazioni preliminari](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) eseguita in precedenza per aggiungere e quindi configurare un'altra azione **Avviare un'approvazione**. Questa azione invia una richiesta di posta elettronica per l'approvazione finale.
2. Al termine, la scheda dovrebbe avere il seguente aspetto:
   
    ![configurare l'approvazione](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Aggiungere la condizione di approvazione finale
1. Ripetere i passaggi da [aggiungere una condizione](sequential-modern-approvals.md#add-a-condition) per aggiungere e quindi configurare un **Condizione** che controlla la decisione del responsabile approvazione finale.

## <a name="send-email-with-final-approval"></a>Inviare posta elettronica con l'approvazione finale
1. Seguire la procedura in [Aggiungere un'azione di posta elettronica per le approvazioni preliminari](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) per aggiungere e quindi configurare un'azione che invii un messaggio di posta elettronica quando vengono approvate le richieste di ferie.
2. Al termine, la scheda sarà simile all'immagine seguente:
   
   ![modello di posta elettronica di approvazione finale](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Aggiornare SharePoint con approvazione
1. Seguire la procedura in [Aggiungere un'azione di aggiornamento per le richieste preapprovate](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) per aggiungere e quindi configurare un'azione che aggiorni SharePoint quando la richiesta di ferie viene approvata.
2. Al termine, la scheda sarà simile all'immagine seguente:
   
    ![aggiornare la configurazione dell'elemento](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Inviare posta elettronica con rifiuto dell'approvazione preliminare
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![configurazione delle richieste rifiutate](./media/sequential-modern-approvals/configure-rejected-email.png)

Nota: è necessario aggiungere quest'azione al ramo **SE NO, NON FARE NULLA** sotto la scheda **Condizione**.

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Aggiornare SharePoint con rifiuto dell'approvazione preliminare
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![aggiornare sharepoint per le richieste rifiutate](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Inviare posta elettronica con il rifiuto finale
1. Seguire la procedura in [Inviare posta elettronica con rifiuto dell'approvazione preliminare](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) per aggiungere e quindi configurare un'azione che invii un messaggio di posta elettronica quando la richiesta di ferie viene rifiutata dal responsabile approvazione finale.
   
    Nota: è necessario aggiungere quest'azione al ramo **SE NO, NON FARE NULLA** sotto la scheda **Condizione 2**.
2. Al termine, la scheda sarà simile all'immagine seguente:
   
   ![configurazione delle richieste rifiutate](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Aggiornare SharePoint con rifiuto finale
1. Seguire la procedura in [Aggiornare SharePoint con rifiuto dell'approvazione preliminare](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) per aggiungere e quindi configurare un'azione che aggiorni SharePoint se il responsabile approvazione finale rifiuta la richiesta di ferie.
2. Al termine, la scheda sarà simile all'immagine seguente:
   
   ![aggiornare scheda elemento](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Selezionare **Aggiorna flusso** per salvare il lavoro svolto.
   
   ![selezionare azione di aggiornamento](./media/sequential-modern-approvals/update.png)

Se tutti i passaggi sono stati eseguiti correttamente, il flusso sarà simile all'immagine seguente:

![panoramica del flusso](./media/sequential-modern-approvals/completed-flow.png)

Dopo aver creato il flusso, è opportuno vederlo in azione.

## <a name="request-an-approval"></a>Richiedere un'approvazione
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

La richiesta deve essere simile all'immagine seguente:

![richiesta di ferie](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Visualizzare le richieste di approvazione in sospeso
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Preapprovare una richiesta
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>Approvare la richiesta
La procedura per approvare una richiesta è identica a quella necessaria per [preapprovare una richiesta](sequential-modern-approvals.md#pre-approve-a-request)

Nota: il responsabile approvazione finale riceve la richiesta di ferie solo dopo che è stata preapprovata.

## <a name="reject-a-request"></a>Rifiutare una richiesta
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Altre informazioni
[Procedura dettagliata di approvazioni moderne di un unico responsabile approvazione](modern-approvals.md)

