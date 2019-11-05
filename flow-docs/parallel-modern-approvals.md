---
title: Creare un flusso di lavoro di approvazione moderno parallelo | Microsoft Docs
description: Creare un flusso di lavoro di approvazione moderno parallelo
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
ms.date: 05/09/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbaaecf70e4f6549a790861130dcde0b5a888e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548963"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Creare flussi di lavoro di approvazione paralleli con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

In un flusso di lavoro di approvazione parallelo, sono necessarie più persone per approvare elementi quali le fatture, gli ordini di acquisto, le richieste di ferie e così via. L'approvazione di ogni persona è indipendente da tutti gli altri responsabili approvazione.

In questa procedura dettagliata viene usato Microsoft Flow per creare un flusso che automatizza un flusso di lavoro di approvazione parallelo. Questo flusso consente di automatizzare un processo di richiesta di ferie dipendenti che richiede l'approvazione di tutte le persone (o Team) che il dipendente supporta regolarmente. I dipendenti usano un [elenco SharePoint](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) per richiedere una ferie. Le approvazioni delle ferie sono richieste dal responsabile diretto del dipendente, dal team di vendita e dal team delle risorse umane. Ogni richiesta di ferie viene indirizzata a ogni responsabile approvazione per una decisione. Il flusso Invia un messaggio di posta elettronica con le modifiche di stato e quindi aggiorna SharePoint con le decisioni.

## <a name="prerequisites"></a>Prerequisiti

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

L'elenco di SharePoint Online creato deve includere le colonne seguenti:

   ![Colonne elenco SharePoint](./media/parallel-modern-approvals/sharepoint-columns.png)

Prendere nota del nome e dell'URL dell'elenco di SharePoint Online. Questi elementi vengono usati in un secondo momento per configurare il trigger **SharePoint-quando viene creato un elemento** .

## <a name="create-your-flow-from-the-blank-template"></a>Creare il flusso dal modello vuoto

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Aggiungere un trigger

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Informazioni su SharePoint](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Chiedere al responsabile della persona che ha creato la richiesta di ferie

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Assegnare un nome e salvare il flusso

1. Specificare un nome per il flusso, quindi selezionare l'icona **Salva** per salvare il lavoro svolto finora.

   ![Salva flusso](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Selezionare l'icona **Salva** periodicamente per salvare le modifiche apportate al flusso.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Aggiungere un'azione di approvazione per gestione immediata

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Questa azione Invia la richiesta di ferie all'indirizzo di posta elettronica nella casella di **assegnato a** , quindi inserire il token di **posta elettronica** dall'elenco **Get Manager (v2)** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Inserire un'azione di approvazione del ramo parallelo per il team di vendita

1. Selezionare la freccia rivolta verso il basso che si trova tra le schede **Get Manager (v2)** e **Start an approvate** .
2. Selezionare il segno più che viene visualizzato sulla freccia rivolta verso il basso dopo averlo selezionato.
3. Selezionare **Aggiungi un ramo parallelo**.
4. Selezionare **Aggiungi un'azione**.

    ![ottenere la configurazione di gestione](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Cercare, selezionare, quindi configurare un'azione **Avvia un'approvazione** che invia la richiesta di ferie al team di vendita. Se non si è certi di come aggiungere l'azione **Avvia un'approvazione** , vedere la [procedura usata per aggiungere un'azione di approvazione per il responsabile immediato](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) .

> [!IMPORTANT]
> Usare l'indirizzo di posta elettronica del team di vendita nella casella **assegnato a** dell'azione **avviare un'approvazione 2** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Inserire un'azione di approvazione del ramo parallelo per il team delle risorse umane

1. Ripetere i passaggi per [inserire un ramo parallelo per il team di vendita](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) da aggiungere e quindi configurare un'azione **Avvia un'approvazione** per inviare le richieste di ferie alle risorse umane.

> [!IMPORTANT]
> Usare l'indirizzo di posta elettronica del team delle risorse umane nella casella **assegnato a** dell'azione **avviare un'approvazione 3** .
> 
> 

Se è stata seguita, il flusso dovrebbe essere simile a questo esempio:

   ![flusso con rami paralleli](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Opzioni dopo l'aggiunta di rami paralleli

Dopo aver aggiunto le azioni ai rami paralleli, sono disponibili due opzioni per l'aggiunta di altri passaggi al flusso:

1. Usare il pulsante **Inserisci piccolo nuovo passaggio** (il pulsante circolare con il segno più visualizzato quando si seleziona uno spazio vuoto in un ramo o nell'area immediatamente sotto un ramo). Questo pulsante aggiunge un passaggio a tale **branch specifico**. I passaggi aggiunti con questo pulsante vengono eseguiti dopo il completamento di questo ramo specifico.
1. Utilizzare il pulsante **nuovo passaggio** più grande nella parte inferiore dell'intero flusso di lavoro. I passaggi aggiunti con questo pulsante vengono eseguiti dopo il completamento di tutti i rami.

Nelle sezioni seguenti viene usato il piccolo pulsante **Inserisci un nuovo passaggio** per eseguire questi passaggi in ogni ramo:

* Aggiungere una condizione che controlla se la richiesta di ferie è stata approvata o rifiutata.
* Inviare un messaggio di posta elettronica che informa il dipendente della decisione.
* Aggiornare la richiesta di ferie in SharePoint con la decisione di approvazione.

Viene quindi usato il pulsante **nuovo passaggio** più grande per inviare un messaggio di posta elettronica che riepiloga tutte le decisioni prese per la richiesta di ferie.

Continua:

## <a name="add-a-condition-to-each-branch"></a>Aggiungere una condizione a ogni ramo

1. Selezionare gli spazi vuoti nel ramo **Avvia un'approvazione** .
2. Selezionare il pulsante **Inserisci piccolo nuovo passaggio** (il pulsante circolare con il segno più che viene visualizzato dopo aver selezionato lo spazio vuoto nel passaggio precedente).
3. Selezionare **Aggiungi una condizione** dal menu visualizzato.
4. Selezionare la prima casella nella scheda **condizione** e quindi selezionare il token di **risposta** dalla categoria **Avvia un'approvazione** nell'elenco contenuto dinamico.

    ![flusso con condizione dei rami paralleli](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Verificare che l'elenco (al centro della **scheda condizione**) sia impostato su **è uguale a**.
6. Immettere **approva** (questo testo fa distinzione tra maiuscole e minuscole) nell'ultima casella.
7. La scheda condizione dovrebbe ora essere simile a questo esempio:

    ![flusso con condizione dei rami paralleli](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Questa condizione controlla la risposta dall'azione **Avvia un'approvazione** che viene inviata al responsabile del dipendente.
   > 
   > 
8. Ripetere i passaggi precedenti nelle sezioni **avviare un'approvazione 2** (richiesta di approvazione per le vendite) e **avviare un'approvazione 3** (la richiesta di approvazione per le risorse umane).

## <a name="add-email-actions-to-each-branch"></a>Aggiungere azioni di posta elettronica a ogni ramo

Eseguire i passaggi seguenti sul lato **if sì** del ramo **Condition** .

   Nota: il flusso usa questa procedura per inviare un messaggio di posta elettronica quando la richiesta viene approvata:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurare il modello di posta elettronica pre-approvato](includes/media/parallel-modern-approvals/yes-email-config.png)

Per inviare un messaggio di posta elettronica quando una richiesta viene rifiutata, usare il lato **if no** del ramo **Condition** , quindi ripetere i passaggi precedenti per aggiungere un modello per il messaggio di posta elettronica di rifiuto.

Ripetere i passaggi precedenti nelle sezioni **avviare un'approvazione 2** (richiesta di approvazione per le vendite) e **avviare un'approvazione 3** (la richiesta di approvazione per le risorse umane).

## <a name="update-the-vacation-request-with-the-decision"></a>Aggiornare la richiesta di ferie con la decisione

Eseguire la procedura seguente per aggiornare SharePoint quando vengono prese le decisioni.

   Nota: assicurarsi di eseguire questi passaggi in entrambi i lati **se sì** e **se no** del ramo.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![Aggiorna configurazione elemento](./media/parallel-modern-approvals/configure-update-item.png)

Ripetere i passaggi precedenti nei rami **avviare un'approvazione 2** e **avviare un'approvazione 3** .

## <a name="complete-the-flow"></a>Completare il flusso

1. Selezionare **nuovo passaggio** > **Aggiungi un'azione**

    ![Aggiorna configurazione elemento](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Usare la procedura descritta in precedenza per inviare un messaggio di posta elettronica che riepiloga i risultati di ogni approvazione. Inviare questo messaggio di posta elettronica al dipendente che ha richiesto una ferie. La scheda potrebbe essere simile a questo esempio:

   ![Aggiorna configurazione elemento](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Scopri di più sulle approvazioni moderne

[Introduzione alle approvazioni moderne](modern-approvals.md)

