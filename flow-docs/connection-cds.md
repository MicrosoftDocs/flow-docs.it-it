---
title: Creare un flusso automatizzato con Common Data Service | Microsoft Docs
description: Creare flussi di lavoro usando una connessione a Common Data Service e Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: brandonsimons
manager: ryjones
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: brandonsimons
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6dba013481983d0b8c43c82c7bc6eed800fccc2e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456958"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Creare un flusso automatizzato usando Common Data Service

Il connettore Common Data Service consente di creare flussi che vengono avviati durante eventi di creazione e aggiornamento nel database di Common Data Service. Consente anche di creare, aggiornare, recuperare ed eliminare le azioni sui record presenti nel database di Common Data Service.

## <a name="initiate-a-flow-from-common-data-service"></a>Avviare un flusso da Common Data Service

Per avviare il flusso, è possibile usare uno dei trigger seguenti:

- Quando viene selezionato un record
- Quando un record viene creato
- Quando un record viene eliminato
- Quando un record viene aggiornato


> [!div class="mx-imgBorder"]
> ![Selezionare un trigger](./media/cds-connector/Triggers.png)

Se per il trigger selezionato è necessario un ambiente, è possibile scegliere `(Current)`, che userà sempre il database dell'ambiente in cui Microsoft Flow viene eseguito. Se si vuole avviare sempre il flusso in base a un evento in un ambiente specifico, selezionare l'ambiente corrispondente.

> [!div class="mx-imgBorder"]
> ![Scegliere l'ambiente](./media/cds-connector/Environments.png)

È possibile usare gli ambiti per determinare se il flusso sarà eseguito quando si creerà personalmente un nuovo record oppure quando sarà un utente della business unit o un qualsiasi utente dell'organizzazione a creare un nuovo record.

> [!div class="mx-imgBorder"]
> ![Scegliere l'ambito](./media/cds-connector/Scopes.png)

|Ambito|Intervallo di trigger|
| --- | --- |
|Business Unit|Viene eseguita un'azione su un record di proprietà della business unit|
|Organizzazione|Viene eseguita un'azione da un qualsiasi utente dell'organizzazione o del database|
|Business Unit padre-figlio|Viene eseguita un'azione su un record di proprietà della business unit o della Business Unit figlio|
|Utente|Viene eseguita un'azione su un record di proprietà dell'utente|

I trigger che vengono eseguiti quando un record viene aggiornato possono usare anche gli attributi di filtro. Si garantisce così che il flusso verrà eseguito solo quando uno degli attributi definiti viene aggiornato.

> [!IMPORTANT]
> Usare gli attributi di filtro per evitare l'inutile esecuzione del filtro.

Questo flusso viene attivato ogniqualvolta viene aggiornato il nome o il cognome del contatto di cui è proprietario l'utente del flusso.

> [!div class="mx-imgBorder"]
> ![Attributi di filtro](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Privilegi di trigger

Perché un utente possa creare un flusso avviato sulla base di operazioni di creazione, aggiornamento o eliminazione di un record, è necessario che disponga delle autorizzazioni per creare, leggere, scrivere, leggere ed eliminare nell'entità Registrazione callback. A seconda degli ambiti definiti, potrebbe anche essere necessario che l'utente abbia almeno quel livello di lettura nella stessa entità.  [Altre informazioni](https://docs.microsoft.com/power-platform/admin/database-security) sulla sicurezza dell'ambiente.

## <a name="write-data-into-common-data-service"></a>Scrivere i dati in Common Data Service

Per scrivere i dati in Common Data Service, usare una delle azioni seguenti:

- Creare un nuovo record
- Aggiornare un record

Di seguito è riportato un esempio di creazione di un'attività follow-up quando l'utente specificato crea un nuovo record dell'account.  

> [!div class="mx-imgBorder"]
> ![Attività follow-up](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Concetti avanzati

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Scrivere i dati nei campi Cliente, Proprietario e Tema

Per scrivere i dati nei campi Cliente, Proprietario e Tema, è necessario popolare due campi.

| Categoria campo | Impostazioni di esempio |
| --- | --- |
| Tema | ID del record (ad esempio ID account) e Tipo relativo come selezionato dall'elenco. |
| Cliente | ID del record e il tipo di cliente come selezionato dall'elenco. |
| Proprietario | ID dell'utente di sistema o del team e il tipo di proprietario come selezionato dall'elenco. |

### <a name="enable-upsert-behavior"></a>Abilitare il comportamento di upsert

È possibile usare il comando **Aggiorna un record** per eseguire azioni di upsert che consentono di aggiornare il record se è già esistente o crearne uno nuovo. Per richiamare l'upsert, specificare l'entità e una chiave GUID. Se esiste un record con il tipo e la chiave specificati, il record viene aggiornato. In caso contrario, viene creato un record con la chiave specificata.

### <a name="trigger-behavior"></a>Comportamento di trigger

Se esiste un trigger registrato nell'aggiornamento di un record, il flusso viene eseguito per ogni aggiornamento *eseguito* sul record specifico. Il servizio richiama il flusso in modo asincrono e usa il payload acquisito al momento della chiamata.

> [!NOTE]
> Se due aggiornamenti avvengono nell'arco di pochi secondi l'uno dall'altro, può succedere che il flusso sia avviato più di una volta e che usi il contenuto della versione più recente.

Le esecuzioni dei flussi possono essere ritardate in presenza di un backlog dei processi di sistema nell'ambiente.  Se l'esecuzione viene ritardata, il flusso viene avviato quando viene eseguito il processo di sistema che richiama il flusso.
