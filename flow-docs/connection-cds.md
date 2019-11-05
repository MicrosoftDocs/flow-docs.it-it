---
title: Creare un flusso automatizzato con Common Data Service | Microsoft Docs
description: Creare flussi di lavoro tramite una connessione Common Data Service e Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 110f3947cf7ece97bfd9b83ca6a12ee46d04b4d6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547131"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Creare un flusso automatizzato usando Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Con il connettore Common Data Service è possibile creare flussi avviati da eventi di creazione e aggiornamento all'interno del database di Common Data Service. Inoltre, è possibile eseguire operazioni di creazione, aggiornamento, recupero ed eliminazione dei record all'interno del database Common Data Service.

## <a name="initiate-a-flow-from-common-data-service"></a>Avviare un flusso da Common Data Service

Per avviare il flusso, è possibile usare uno dei trigger seguenti:

- Quando viene selezionato un record
- Quando viene creato un record
- Quando un record viene eliminato
- Quando un record viene aggiornato


> [!div class="mx-imgBorder"]
> ![selezionare un trigger](./media/cds-connector/Triggers.png)

Se per il trigger selezionato è necessario selezionare un ambiente, è possibile scegliere `(Current)`, che utilizzerà sempre il database all'interno dell'ambiente in cui viene eseguito Microsoft Flow. Se si vuole che il flusso venga sempre attivato in base a un evento in un ambiente specifico, selezionare l'ambiente.

> [!div class="mx-imgBorder"]
> ![scegliere l'ambiente](./media/cds-connector/Environments.png)

È possibile usare gli ambiti per determinare se il flusso viene eseguito se si crea un nuovo record, se un nuovo record viene creato da un utente all'interno della business unit o se viene creato un nuovo record da qualsiasi utente dell'organizzazione.

> [!div class="mx-imgBorder"]
> ![Scegli ambito](./media/cds-connector/Scopes.png)

|Ambito|Temporizzazione trigger|
| --- | --- |
|Business Unit|L'azione viene eseguita su un record di proprietà della business unit|
|Organizzazione|L'azione viene eseguita da chiunque all'interno dell'organizzazione o del database|
|Padre: business unit figlio|L'azione viene eseguita su un record di proprietà della business unit o di una business unit figlio|
|Utente|L'azione viene eseguita su un record di proprietà dell'utente|

Anche i trigger che vengono eseguiti quando un record viene aggiornato possono usare gli attributi di filtro. Ciò garantisce che il flusso venga eseguito solo quando uno degli attributi definiti viene aggiornato.

> [!IMPORTANT]
> Usare gli attributi di filtro per impedire che il flusso venga eseguito inutilmente.

Questo flusso viene attivato ogni volta che viene aggiornato il nome o il cognome del contatto a cui appartiene l'utente Microsoft Flow.

> [!div class="mx-imgBorder"]
> attributi filtro ![](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Privilegi di trigger

Per creare un flusso che viene attivato in base a creazione, aggiornamento o eliminazione in un record, l'utente deve disporre delle autorizzazioni a livello di utente per la creazione, la lettura, la scrittura e l'eliminazione nell'entità di registrazione di callback. Inoltre, a seconda degli ambiti definiti, l'utente potrebbe richiedere almeno questo livello di lettura sulla stessa entità.  [Altre](https://docs.microsoft.com/power-platform/admin/database-security) informazioni sulla sicurezza dell'ambiente.

## <a name="write-data-into-common-data-service"></a>Scrivere dati in Common Data Service

Per scrivere i dati in Common Data Service, utilizzare una delle azioni seguenti:

- Crea un nuovo record
- Aggiornare un record

Di seguito è riportato un esempio di creazione di un'attività di completamento quando l'utente specificato crea un nuovo record di account.  

> [!div class="mx-imgBorder"]
> ![attività di follow](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Concetti avanzati

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Scrivere dati in campi cliente, proprietario e relativo

Per scrivere dati in campi cliente, proprietario e relativo, è necessario popolare due campi.

| Categoria di campi | impostazioni di esempio |
| --- | --- |
| Sulla | Relativa a = ID del record (ad esempio, ID account) e relativo al tipo selezionato nell'elenco. |
| Cliente | Rappresenta l'ID del record e il tipo di cliente selezionato nell'elenco. |
| Proprietario | Rappresenta l'ID dell'utente o del team di sistema e il tipo di proprietario selezionato nell'elenco. |

### <a name="enable-upsert-behavior"></a>Abilita il comportamento di Upsert

È possibile usare il comando **Aggiorna un record** per fornire azioni Upsert, che aggiorna il record se esiste già o crea un nuovo record. Per richiamare Upsert, fornire l'entità e una chiave GUID. Se esiste un record con il tipo e la chiave specificati, viene eseguito un aggiornamento. In caso contrario, viene creato un record con la chiave specificata.

### <a name="trigger-behavior"></a>Comportamento del trigger

Se si dispone di un trigger registrato sull'aggiornamento di un record, il flusso viene eseguito per ogni aggiornamento di cui è stato eseguito il *commit* nel record specificato. Il servizio richiama il flusso in modo asincrono e con il payload acquisito nel momento in cui si verifica la chiamata.

> [!NOTE]
> Se si dispone di due aggiornamenti che si verificano in pochi secondi, il flusso può essere attivato più di una volta con il contenuto più recente con versione.

Le esecuzioni dei flussi possono essere posticipate se è presente un backlog di processi di sistema nell'ambiente in uso.  Se si verifica questo ritardo, il flusso viene attivato quando viene eseguito il processo di sistema per richiamare il flusso.
