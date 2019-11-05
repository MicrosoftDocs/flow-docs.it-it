---
title: Informazioni su come aggiungere altri proprietari a un flusso e creare flussi del team | Microsoft Docs
description: Microsoft Flow semplifica l'automazione delle attività ripetitive. È possibile aggiungere utenti o gruppi come proprietari e collaborare con loro per progettare e gestire i flussi.
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
ms.date: 04/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2a986568a44f8329e55fc62aef4705207cdfc49
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547609"
---
# <a name="create-team-flows"></a>Creare flussi del team
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Creare un flusso del team aggiungendo altri utenti all'interno dell'organizzazione come proprietari. Tutti i proprietari di un flusso del team possono eseguire queste azioni:

* Visualizzare la cronologia del flusso (ovvero ogni esecuzione).
* Gestire le proprietà del flusso (ad esempio, avviare o arrestare il flusso, aggiungere proprietari o aggiornare le credenziali per una connessione).
* Modificare la definizione del flusso (ad esempio, aggiungere o rimuovere un'azione o una condizione).
* Aggiungere e rimuovere altri proprietari, ma non il creatore del flusso.
* Eliminare il flusso.

Se si è il creatore o un proprietario di un flusso del team, è possibile trovarlo nella scheda **flussi del team** in [Microsoft Flow](https://flow.microsoft.com).

![scheda flussi team](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Le connessioni condivise possono essere usate **solo** nel flusso in cui sono state create.
> 
> 

I proprietari possono usare i servizi in un flusso, ma non possono modificare le credenziali per una connessione creata da un altro proprietario.

## <a name="prerequisites"></a>Prerequisiti
Per creare un flusso del team, è necessario disporre di un [piano di Microsoft Flow a pagamento](https://flow.microsoft.com/pricing/) . Inoltre, è necessario essere il creatore o il proprietario per aggiungere o rimuovere proprietari da un flusso del team.

## <a name="create-a-team-flow"></a>Creare un flusso del team
Seguire questa procedura per creare un flusso del team o per aggiungere altri proprietari a un flusso del team.

1. Accedere al [Microsoft Flow](https://flow.microsoft.com)e quindi selezionare **flussi personali**.
2. Selezionare l'icona persone per il flusso che si desidera modificare:
   
    ![icona del team](./media/create-team-flows/addowner1.png)
3. Immettere il nome, l'indirizzo di posta elettronica o il nome del gruppo per la persona o il gruppo che si desidera aggiungere come proprietario:
   
    ![cercare l'utente](./media/create-team-flows/addowner2.png)
4. Nell'elenco visualizzato selezionare l'utente di cui si desidera creare un proprietario:
   
    ![Selezionare l'utente](./media/create-team-flows/addowner3.png)
   
     L'utente o il gruppo selezionato diventa un proprietario del flusso:
   
    ![nuovo proprietario](./media/create-team-flows/addowner4.png)
   
     Congratulazioni &mdash; il flusso del team è stato creato.

## <a name="add-a-list-as-a-co-owner"></a>Aggiungere un elenco come comproprietario

È possibile aggiungere gli elenchi di SharePoint come co-proprietari a un flusso in modo che tutti gli utenti che dispongono dell'accesso di modifica all'elenco ottengano automaticamente l'accesso in modifica al flusso. Una volta condiviso il flusso, è possibile semplicemente distribuirvi un collegamento.

> [!TIP]
> Utilizzare un elenco quando il flusso è connesso a SharePoint e utilizzare un gruppo in altri casi.
>

## <a name="remove-an-owner"></a>Rimuovere un proprietario

> [!IMPORTANT]
> Quando si rimuove un proprietario le cui credenziali vengono usate per accedere ai servizi di Microsoft Flow, è necessario aggiornare le credenziali per le connessioni in modo che il flusso continui a funzionare correttamente.
> 
> 

1. Selezionare l'icona persone per il flusso che si desidera modificare:
   
    ![icona Seleziona persone](./media/create-team-flows/removeowner1.png)
2. Selezionare l'icona di **eliminazione** del proprietario che si desidera rimuovere:
   
    ![Selezionare Elimina](./media/create-team-flows/removeowner2.png)
3. Nella finestra di dialogo di conferma selezionare **Rimuovi questo proprietario**:
   
    ![Conferma rimozione](./media/create-team-flows/removeowner3.png)
4. Congratulazioni &mdash; l'utente o il gruppo rimosso non è più elencato come proprietario del flusso:
   
    ![utente rimosso](./media/create-team-flows/removeowner4.png)


## <a name="update-connection-owner"></a>Aggiorna il proprietario della connessione

Se si rimuove il proprietario esistente, potrebbe essere necessario modificare il proprietario di una connessione in un flusso. Per cambiare il proprietario di un flusso, seguire questa procedura:

1. Selezionare **dati** dal pannello sul lato sinistro.
1. Selezionare **connessioni**.
1. Cercare la connessione che si vuole aggiornare e quindi selezionarla.
1. Selezionare **...** (altri comandi) nella connessione selezionata e quindi selezionare **Cambia account**.
1. Seguire i passaggi per usare un account diverso per la connessione.

## <a name="embedded-and-other-connections"></a>Connessioni incorporate e altre

Le connessioni usate in un flusso rientrano in due categorie:

* **Incorporato** &mdash; queste connessioni vengono usate nel flusso.
* **Altre** &mdash; queste connessioni sono state definite per un flusso, ma non vengono usate al suo interno.

Se si interrompe l'uso di una connessione in un flusso, tale connessione viene visualizzata nell'elenco **altre** connessioni, dove rimane fino a quando un proprietario non lo include nuovamente nel flusso.

Seguire i passaggi per [aggiornare un proprietario della connessione](./create-team-flows.md#update-connection-owner) per apportare modifiche alle connessioni incorporate.

L'elenco delle connessioni viene visualizzato sotto l'elenco dei proprietari nelle proprietà di un flusso:

![connessioni incorporate](./media/create-team-flows/embeddedconnections.png)

