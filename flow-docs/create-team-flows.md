---
title: Informazioni su come aggiungere altri proprietari a un flusso e creare flussi del team | Microsoft Docs
description: Microsoft Flow rende più semplice automatizzare attività ripetitive. È possibile aggiungere utenti o gruppi come proprietari e collaborare con loro per progettare e gestire i flussi.
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
ms.openlocfilehash: d4e8de2f9f67c07861297e079948a5336ff66e7f
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439687"
---
# <a name="create-team-flows"></a>Creare flussi del team
Creare un flusso del team aggiungendo altri utenti nell'organizzazione come proprietari. Tutti i proprietari di un flusso di team possono eseguire queste azioni:

* Visualizzare la cronologia dei flussi, ovvero le singole esecuzioni.
* Gestire le proprietà del flusso (ad esempio, avviare o arrestare il flusso, aggiungere proprietari o aggiornare le credenziali per una connessione).
* Modificare la definizione del flusso (ad esempio, aggiungere o rimuovere una condizione o azione).
* Aggiungere e rimuovere altri proprietari, ma non il creatore del flusso.
* Eliminare il flusso.

Il creatore o un proprietario di un flusso del team vedrà il flusso visualizzato nella scheda **Flussi team** in [Microsoft Flow](https://flow.microsoft.com).

![scheda flussi team](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Le connessioni condivise possono essere usate **solo** nel flusso in cui sono state create.
> 
> 

I proprietari possono usare i servizi in un flusso, ma non modificare le credenziali per una connessione creata da un altro proprietario.

## <a name="prerequisites"></a>Prerequisiti
Per creare un flusso del team occorre avere un [piano di Microsoft Flow a pagamento](https://flow.microsoft.com/pricing/). È anche necessario essere l'autore o il proprietario per aggiungere o rimuovere proprietari da un flusso del team.

## <a name="create-a-team-flow"></a>Creare un flusso del team
Seguire questi passaggi per creare un flusso del team o per aggiungere uno o più proprietari a un flusso del team.

1. Accedere a [Microsoft Flow](https://flow.microsoft.com), quindi selezionare **Flussi personali**.
2. Selezionare l'icona della persona per il flusso da modificare:
   
    ![icona team](./media/create-team-flows/addowner1.png)
3. Immettere il nome, l'indirizzo di posta elettronica o il nome del gruppo della persona o del gruppo da aggiungere come proprietario:
   
    ![cercare l'utente](./media/create-team-flows/addowner2.png)
4. Nell'elenco visualizzato selezionare l'utente da impostare come proprietario:
   
    ![selezionare l'utente](./media/create-team-flows/addowner3.png)
   
     L'utente o il gruppo selezionato diventa un proprietario del flusso:
   
    ![nuovo proprietario](./media/create-team-flows/addowner4.png)
   
     Congratulazioni &mdash; il flusso del team è stato creato.

## <a name="remove-an-owner"></a>Rimuovere un proprietario
> [!IMPORTANT]
> Quando si rimuove un proprietario le cui credenziali vengono usate per accedere ai servizi di Microsoft Flow, potrebbe essere necessario aggiornare le credenziali di queste connessioni in modo che il flusso continui a funzionare correttamente.
> 
> 

1. Selezionare l'icona della persona per il flusso da modificare:
   
    ![selezionare l'icona della persona](./media/create-team-flows/removeowner1.png)
2. Selezionare l'icona **Elimina** per il proprietario da rimuovere:
   
    ![selezionare elimina](./media/create-team-flows/removeowner2.png)
3. Nella finestra di dialogo di conferma selezionare **Rimuovi questo proprietario**:
   
    ![confermare rimozione](./media/create-team-flows/removeowner3.png)
4. Congratulazioni &mdash; l'utente o il gruppo rimosso non è più elencato come proprietario del flusso:
   
    ![utente rimosso](./media/create-team-flows/removeowner4.png)

## <a name="embedded-and-other-connections"></a>Connessioni incorporate e altri tipi
Le connessioni usate in un flusso rientrano in due categorie:

* **Incorporate** &mdash; Queste connessioni sono usate all'interno del flusso.
* **Altre** &mdash; Queste connessioni sono state definite per un flusso ma non vengono usate al suo interno.

Se si interrompe l'uso di una connessione in un flusso, verrà visualizzata nell'elenco di connessioni **Altre**, dove resterà resta finché un proprietario non la includerà di nuovo nel flusso.

L'elenco di connessioni viene visualizzato sotto l'elenco di proprietari nelle proprietà di un flusso:

![connessioni incorporate](./media/create-team-flows/embeddedconnections.png)

