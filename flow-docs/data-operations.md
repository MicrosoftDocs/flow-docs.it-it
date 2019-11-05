---
title: Informazioni sulle operazioni sui dati | Microsoft Docs
description: Informazioni su come eseguire operazioni, ad esempio creare una tabella HTML, creare una tabella CSV, comporre, unire, selezionare e filtrare una matrice con Microsoft Flow.
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
ms.date: 08/02/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 87d805fb7de5ee9688e9e89c201be00fda8fb319
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547775"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Usare le operazioni dati con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Questa procedura dettagliata illustra alcune delle operazioni sui dati più diffuse del Microsoft Flow, ad esempio compose, join, Select, Filter Array, create table e Parse JSON disponibili per modificare i dati quando si creano i flussi.

## <a name="prerequisites"></a>Prerequisiti
* Accesso a Microsoft Flow.
* Uno strumento come [poster](https://www.getpostman.com/postman) per inviare richieste HTTP post con una matrice JSON al flusso.

## <a name="use-the-compose-action"></a>Usare l'azione compose
Usare l'azione **operazioni dati-Componi** (compose) per evitare di immettere dati identici più volte durante la progettazione di un flusso. Ad esempio, se è necessario immettere una matrice di cifre: ````[0,1,2,3,4,5,6,7,8,9]```` più volte durante la progettazione del flusso, è possibile usare l'azione compose per salvare la matrice come questa:

1. Cercare **compose**, quindi selezionare l'azione **operazioni dati-Componi** (compose).
   
    ![cercare e selezionare l'azione Componi](./media/data-operations/search-select-compose.png)
2. Immettere la matrice nella casella **input** a cui si vuole fare riferimento in un secondo momento:
   
    ![configurare l'azione compose](./media/data-operations/add-array-compose.png)

> [!TIP]
> Per un riferimento più semplice in un secondo momento, rinominare la scheda **compose** facendo clic sul testo "compose" sulla barra del titolo della scheda **compose** .
> 
> 

Quando è necessario accedere al contenuto dell'azione compose, effettuare questa operazione tramite il token di **output** sul **Aggiungi contenuto dinamico dalle app e dai connettori usati in questo** elenco di flussi attenendosi alla procedura seguente:

1. Aggiungere un'azione, ad esempio **operazioni dati-** aggiunta.
2. Selezionare il controllo a cui si vuole aggiungere il contenuto salvato nell'azione compose.
   
    Viene aperto il **Aggiungi contenuto dinamico dalle app e dai connettori usati in questo flusso** .
3. In **Aggiungi contenuto dinamico dalle app e dai connettori usati in questo flusso**selezionare il token di **output** che si trova sotto la categoria **compose** della scheda **contenuto dinamico** .
   
    ![usare l'output dell'azione compose](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Usare l'azione di join
Usare l'azione **operazioni dati-Unione** (join) per delimitare una matrice con un separatore di propria scelta. Si supponga, ad esempio, che il flusso riceva una richiesta Web che includa la seguente matrice di indirizzi di posta elettronica: ````["d@example.com", "k@example.com", "dal@example.com"]````. Tuttavia, il programma di posta elettronica richiede che gli indirizzi siano costituiti da una singola stringa separata da punti e virgola. A tale scopo, utilizzare l'azione **operazioni dati-join** (join) per modificare il delimitatore di virgola in un punto e virgola ";" attenendosi alla seguente procedura:

1. Aggiungere una nuova azione, cercare **join**, quindi selezionare **operazioni dati-aggiunta** (join).
   
    ![cercare e selezionare l'azione di join](./media/data-operations/search-select-join.png)
2. Immettere la matrice nella casella **da** e quindi immettere il nuovo delimitatore che si desidera utilizzare nella casella **join con** .
   
    Qui ho usato il punto e virgola (;) come nuovo delimitatore.
   
    ![configurare l'azione di join](./media/data-operations/add-array-join.png)
3. Salvare il flusso, quindi eseguirlo.
4. Dopo l'esecuzione del flusso, l'output dell'azione **operazioni dati-join** sarà:
   
    ![output di join](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Usare l'azione seleziona
Usare le **operazioni dati-Select** (Select) per trasformare la forma degli oggetti in una matrice. Ad esempio, è possibile aggiungere, rimuovere o rinominare gli elementi in ogni oggetto in una matrice.

> [!NOTE]
> Sebbene sia possibile aggiungere o rimuovere elementi utilizzando l'azione seleziona, non è possibile modificare il numero di oggetti nella matrice.
> 
> 

Ad esempio, è possibile usare l'azione seleziona se i dati entrano nel flusso tramite una richiesta Web nel formato seguente:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

e si vuole modificare la forma dei dati in arrivo rinominando "First" in "FirstName", "Last" in "LastName" e aggiungendo un nuovo membro denominato "familyName" che combina "First" e "Last" (separati da uno spazio):

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Per eseguire questa operazione:

1. Aggiungere l'azione **richiesta/risposta-risposta** (richiesta) al flusso.
2. Selezionare **USA payload di esempio per generare lo schema** dalla scheda **richiesta** .
3. Nella casella che Visualizza, incollare un campione della matrice di dati di origine, quindi selezionare il pulsante **fine** .
4. Aggiungere l'azione **operazioni dati-seleziona** (selezione), quindi configurarla come nell'immagine seguente.
   
    ![configurare l'azione di selezione](./media/data-operations/select-card.png)
   
   > [!TIP]
   > L'output dell'azione SELECT è una matrice che contiene gli oggetti appena modellati. È quindi possibile usare questa matrice in qualsiasi altra azione, ad esempio **compose**, descritta in precedenza.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Usare l'azione filtra matrice
Usare **operazioni dati-filtra matrice** (Filtra matrice) per ridurre il numero di oggetti in una matrice a un subset che corrisponde ai criteri forniti.

> [!NOTE]
> Impossibile utilizzare la matrice di filtri per modificare la forma degli oggetti in una matrice. Inoltre, il testo su cui si esegue il filtro fa distinzione tra maiuscole e minuscole.
> 
> 

Ad esempio, è possibile usare la matrice di filtri in questa matrice:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

per creare una nuova matrice che contiene solo oggetti in cui *First* è impostato su "Deon".

Eseguiamo questa operazione.

1. Trovare, quindi aggiungere l'azione **operazioni dati-filtra** matrice (matrice di filtri) al flusso.
2. Configurare l'azione filtra matrice come la figura seguente.
   
    ![Configura azione filtra matrice](./media/data-operations/add-configure-filter-array.png)
3. Salvare e quindi eseguire il flusso.
   
    È possibile usare il [post](https://www.getpostman.com/postman) per generare una richiesta Web che invia una matrice JSON al flusso.
4. Quando viene eseguito il flusso, supponendo che l'input JSON appaia come questa matrice:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    l'output ha un aspetto simile a questa matrice (si noti che solo gli oggetti in cui *First* è impostato su "Deon" sono inclusi nell'output dell'azione):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Usare l'azione Crea tabella CSV
Usare la tabella **operazioni dati-crea tabella CSV** (Crea tabella CSV) per modificare l'input di una matrice JSON in una tabella con valori delimitati da virgole (CSV). Facoltativamente, è possibile rendere visibili le intestazioni nell'output CSV. Ad esempio, è possibile convertire la matrice seguente in una tabella CSV usando l'azione **Crea tabella CSV** :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Trovare, aggiungere e quindi configurare l'azione **operazioni dati-crea tabella CSV** in modo simile all'immagine seguente.
   
    ![configurare l'azione Crea tabella CSV](./media/data-operations/create-csv-table.png)
   
    Nota: il token del **corpo** in questa immagine deriva da un'azione **richiesta/risposta-risposta** , ma è possibile ottenere l'input per l'azione **Crea tabella CSV** dall'output di qualsiasi azione precedente nel flusso oppure è possibile immetterlo direttamente nel **Da** box.
2. Salvare e quindi eseguire il flusso.
   
    Quando viene eseguito il flusso, l'output della **creazione della tabella CSV** è simile a questa immagine:
   
    ![Crea output tabella CSV](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Usare l'azione Crea tabella HTML
Usare **operazioni dati-crea tabella HTML** per modificare un input di matrice JSON in una tabella HTML. Facoltativamente, è possibile rendere visibili le intestazioni nell'output HTML.

A tale scopo, seguire i passaggi della [sezione creare una tabella CSV](#use-the-create-csv-table-action) per un esempio dettagliato. Assicurarsi di usare l'azione **operazioni dati-crea tabella HTML** , anziché l'azione **operazioni dati-crea tabella CSV** .

> [!TIP]
> Se si prevede di inviare la tabella HTML tramite posta elettronica, ricordarsi di selezionare "IsSelected" nell'azione posta elettronica.
> 
> 

