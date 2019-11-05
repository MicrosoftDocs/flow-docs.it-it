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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 269239bd3fbb07c78bf316f9e58003690c63d878
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548967"
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Gestione delle approvazioni sequenziali con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Alcuni flussi di lavoro richiedono la pre-approvazione prima che il responsabile approvazione finale debba disconnettersi. Ad esempio, un'azienda può disporre di un criterio di approvazione sequenziale che richiede la pre-approvazione per le fatture su $1000,00 prima che siano approvate dal reparto finanziario.

In questa procedura dettagliata viene creato un flusso di approvazione sequenziale che gestisce le richieste di ferie dei dipendenti.

> [!NOTE]
> SharePoint viene usato solo come esempio. non è necessario creare flussi di approvazione. È possibile usare uno dei più di 200 servizi con cui Microsoft Flow si integra per guidare i flussi.


## <a name="detailed-steps-in-the-flow"></a>Passaggi dettagliati nel flusso
Il flusso:

1. Viene avviato quando un dipendente crea una richiesta di ferie in un [elenco di SharePoint Online](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
2. Aggiunge la richiesta di ferie al Centro approvazioni, quindi invia tramite posta elettronica la richiesta al responsabile approvazione.
3. Invia tramite posta elettronica la decisione di approvazione preliminare al dipendente.
4. Aggiorna l'elenco di SharePoint Online con la decisione e i commenti del responsabile approvazione.
   
   Nota: se la richiesta è già stata approvata, il flusso continua con i passaggi seguenti:
5. Invia la richiesta al responsabile approvazione finale.
6. Invia tramite posta elettronica la decisione finale al dipendente.
7. Aggiorna l'elenco di SharePoint con la decisione finale.

Questa immagine riepiloga i passaggi precedenti:

   ![diagramma di Visio del flusso](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Prerequisiti
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Ai fini di questa procedura dettagliata, l'elenco di SharePoint Online creato deve includere le colonne seguenti:

   ![Colonne elenco SharePoint](./media/sequential-modern-approvals/sharepoint-columns.png)

Prendere nota del nome e dell'URL dell'elenco di SharePoint Online. Questi elementi vengono usati in un secondo momento quando si configura il trigger **SharePoint-quando viene creato un nuovo elemento** .

## <a name="create-your-flow-from-the-blank-template"></a>Creare il flusso dal modello vuoto
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Aggiungere un trigger
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![informazioni su SharePoint](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Chiedere al responsabile della persona che ha creato la richiesta di ferie
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Specificare un nome per il flusso e quindi selezionare **Crea flusso** per salvare il lavoro svolto finora.
   
    ![Salva flusso](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Selezionare periodicamente **Aggiorna flusso** dalla parte superiore dello schermo per salvare le modifiche apportate al flusso.
   > 
   > 
   
    ![Selezionare l'azione di aggiornamento](./media/sequential-modern-approvals/update.png)

Dopo ogni operazione di salvataggio, selezionare **Modifica flusso** nella parte superiore dello schermo e quindi continuare a apportare modifiche.

## <a name="add-an-approval-action-for-pre-approvals"></a>Aggiungere un'azione di approvazione per le approvazioni preliminari
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Nota: questa azione Invia la richiesta di approvazione preliminare all'indirizzo di posta elettronica nella casella di **assegnato a** .

## <a name="add-a-condition"></a>Aggiungere una condizione
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Questa condizione controlla la risposta dall'azione **Avvia un'approvazione** .
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Aggiungere un'azione di posta elettronica per le approvazioni preliminari
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurare il modello di posta elettronica pre-approvato](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Aggiungere un'azione di aggiornamento per le richieste pre-approvate
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![Aggiorna configurazione elemento](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Ottenere il responsabile del responsabile approvazione
1. Usare il [Get the Manager per la persona che ha creato la richiesta di ferie](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) descritta in precedenza per aggiungere e quindi configurare un'altra azione **Get Manager** . Questa volta si ottiene il responsabile del pre-responsabile approvazione.
2. Al termine, la scheda **Get Manager 2 dovrebbe essere** simile a questa immagine. Assicurarsi di usare il token di **posta elettronica** della categoria **Get Manager** nel **aggiungere il contenuto dinamico dalle app e dai servizi usati in questa scheda di flusso** .
   
   ![ottenere il responsabile del responsabile approvazione](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Aggiungere l'azione di approvazione finale
1. Usare l' [azione Aggiungi un'approvazione per le procedure preliminari approvate](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) in precedenza per aggiungere e quindi configurare un'altra azione **Avvia un'approvazione** . Questa azione Invia una richiesta di posta elettronica per l'approvazione finale.
2. Al termine, la scheda sarà simile a questa immagine:
   
    ![configurare l'approvazione](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Aggiungere la condizione di approvazione finale
1. Ripetere i passaggi da [aggiungere una condizione](sequential-modern-approvals.md#add-a-condition) da aggiungere e quindi configurare una **condizione** che controlla la decisione del responsabile approvazione finale.

## <a name="send-email-with-final-approval"></a>Inviare un messaggio di posta elettronica con l'approvazione finale
1. Usare la procedura descritta in [aggiungere un'azione di posta elettronica per le approvazioni preliminari](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) da aggiungere e quindi configurare un'azione che invii un messaggio di posta elettronica quando vengono approvate le richieste di ferie.
2. Al termine, la scheda sarà simile a questa immagine:
   
   ![modello di posta elettronica di approvazione finale](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Aggiornare SharePoint con approvazione
1. Usare la procedura descritta in [aggiungere un'azione di aggiornamento per le richieste pre-approvate](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) da aggiungere e quindi configurare un'azione che aggiorni SharePoint quando la richiesta di ferie viene approvata.
2. Al termine, la scheda sarà simile a questa immagine:
   
    ![Aggiorna configurazione elemento](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Inviare un messaggio di posta elettronica con rifiuto dell'approvazione preliminare
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![configurazione per le richieste rifiutate](./media/sequential-modern-approvals/configure-rejected-email.png)

Nota: questa azione deve essere aggiunta al ramo **se no, non fare nulla** sotto la scheda **condizione** .

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Aggiornare SharePoint con rifiuto dell'approvazione preliminare
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![aggiornare SharePoint per le richieste rifiutate](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Inviare un messaggio di posta elettronica con rifiuto finale
1. Usare la procedura descritta in [inviare un messaggio di posta elettronica con rifiuto dell'approvazione preliminare](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) per aggiungere e quindi configurare un'azione che invii un messaggio di posta elettronica quando la richiesta di ferie viene rifiutata dal responsabile approvazione finale.
   
    Nota: questa azione deve essere aggiunta al ramo **se no, non fare nulla** sotto la scheda **condizione 2** .
2. Al termine, la scheda sarà simile a questa immagine:
   
   ![configurazione per le richieste rifiutate](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Aggiornare SharePoint con rifiuto finale
1. Usare la procedura descritta in [aggiornare SharePoint con il rifiuto di approvazione preliminare](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) per aggiungere e quindi configurare un'azione che aggiorni SharePoint se il responsabile approvazione finale rifiuta la richiesta di ferie.
2. Al termine, la scheda sarà simile a questa immagine:
   
   ![Aggiorna scheda elemento](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Selezionare **Aggiorna flusso** per salvare il lavoro svolto.
   
   ![Selezionare l'azione di aggiornamento](./media/sequential-modern-approvals/update.png)

Se è stata seguita, il flusso dovrebbe essere simile all'immagine seguente:

![Panoramica di Flow](./media/sequential-modern-approvals/completed-flow.png)

Ora che è stato creato il flusso, è possibile vederlo in azione.

## <a name="request-an-approval"></a>Richiedi approvazione
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

La richiesta dovrebbe essere simile a questa immagine:

![richiesta di ferie](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Visualizza le richieste di approvazione in sospeso
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Pre-approva una richiesta
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>Approva la richiesta
I passaggi per approvare una richiesta sono identici ai passaggi per la [pre-approvazione di una richiesta](sequential-modern-approvals.md#pre-approve-a-request)

Nota: il responsabile approvazione finale ottiene la richiesta di ferie solo dopo che la richiesta è stata pre-approvata.

## <a name="reject-a-request"></a>Rifiutare una richiesta
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Ulteriori informazioni
[Procedura dettagliata per le approvazioni moderne](modern-approvals.md)

