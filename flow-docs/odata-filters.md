---
title: Filtrare e copiare i dati | Microsoft Docs
description: Informazioni su come filtrare e copiare i dati da un'origine a una destinazione con Microsoft Flow
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
ms.date: 09/21/2017
ms.author: deonhe
ms.openlocfilehash: 7c182328c341043ffc155a679f39bcbc2130a0bc
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "31008071"
---
# <a name="filter-and-copy-data-with-microsoft-flow"></a>Filtrare e copiare i dati con Microsoft Flow
Questa procedura dettagliata illustra come creare un flusso che monitora un'origine per verificare la presenza di elementi nuovi o modificati e copia quindi tali modifiche in una destinazione. Se gli utenti inseriscono dati in un'unica posizione, ma il team ha bisogno di dati in un formato o un percorso diverso, è possibile creare un flusso di questo tipo.

Mentre questa procedura dettagliata copia i dati da un [elenco](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) Microsoft SharePoint (l'origine) a una tabella del [database SQL di Microsoft Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) (la destinazione), è possibile copiare dati tra gli oltre [150 servizi](https://flow.microsoft.com/connectors/) supportati da Microsoft Flow.

> [!IMPORTANT]
> Le modifiche apportate nella destinazione non vengono copiate nell'origine, perché le sincronizzazioni bidirezionali non sono supportate. Se si prova a impostare una sincronizzazione bidirezionale, si creerà un ciclo infinito in cui le modifiche vengono inviate all'infinito tra l'origine e la destinazione.
> 
> 

## <a name="prerequisites"></a>Prerequisiti
* Accesso a un'origine dati e una destinazione. Questa procedura dettagliata non include i passaggi per creare l'origine e la destinazione.
* Avere accesso a [Microsoft Flow](https://flow.microsoft.com).
* Una conoscenza di base della modalità di archiviazione dei dati.
* Familiarità con le nozioni di base della creazione di flussi. È possibile esaminare come aggiungere [azioni, trigger](multi-step-logic-flow.md#add-another-action) e [condizioni](add-condition.md). I passaggi seguenti presuppongono che si sappia come eseguire queste azioni.

> [!TIP]
> I nomi delle colonne nell'origine e nella destinazione non devono per forza corrispondere, ma è necessario fornire i dati per tutte le colonne *obbligatorie* quando si inserisce o si aggiorna un elemento. Microsoft Flow identifica i campi obbligatori per l'utente.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Rapida panoramica dei passaggi
Se si ha familiarità con Microsoft Flow, è possibile usare questi passaggi rapidi per copiare dati da un'origine dati a un'altra:

1. Identificare l'origine da monitorare e la destinazione in cui verranno copiati i dati modificati. Verificare di aver accesso a entrambe.
2. Identificare almeno una colonna che identifichi in modo univoco gli elementi di origine e destinazione. Nell'esempio seguente viene usata la colonna **Titolo**, ma è possibile usare qualsiasi colonna desiderata (o anche più colonne).
3. Impostare un trigger che esegua il monitoraggio delle modifiche nell'origine.
4. Cercare nella destinazione per verificare se esiste l'elemento modificato.
5. Usare una **Condizione** come segue:
   * Se l'elemento nuovo o modificato non esiste nella destinazione, è necessario crearlo.
   * Se l'elemento nuovo o modificato esiste nella destinazione, è necessario aggiornarlo.
6. Attivare il flusso e quindi verificare che gli elementi nuovi o modificati vengano copiati dall'origine alla destinazione.

> [!NOTE]
> Se non è stata creata in precedenza una connessione al database SQL di Microsoft Azure o SharePoint, seguire le istruzioni quando viene chiesto di accedere.
> 
> 

Ecco i passaggi dettagliati per creare il flusso.

## <a name="monitor-the-source-for-changes"></a>Monitorare le modifiche nell'origine
1. Accedere a [Microsoft Flow](https://flow.microsoft.com), selezionare **Flussi personali** > **Crea da zero**.
2. Cercare **SharePoint** > selezionare il trigger **SharePoint - Quando viene creato o modificato un elemento** dall'elenco dei trigger.
3. Immettere l'**Indirizzo sito** e quindi selezionare il **Nome elenco** nella scheda **Quando viene creato o modificato un elemento**.
   
    Fornire l'**Indirizzo sito** e il **Nome elenco** per l'elenco di SharePoint che viene monitorato dal flusso per gli elementi nuovi o aggiornati.
   
    ![configurare il trigger di sharepoint](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Cercare l'elemento nuovo o aggiornato nella destinazione
A tale scopo, si userà l'azione **SQL Server - Ottieni righe**.

1. Selezionare **Nuovo passaggio** > **Aggiungi un'azione**.
2. Cercare **Ottieni righe**selezionare **SQL Server - Ottieni righe**e quindi selezionare la tabella che si vuole monitorare dall'elenco **Nome tabella**.
3. Selezionare **Mostra le opzioni avanzate**.
4. Nella casella **Query filtro** immettere **Title eq '**, selezionare il token **Titolo** dall'elenco del contenuto dinamico e quindi immettere **'**.
   
    Il passaggio precedente presuppone che i titoli delle righe nell'origine e nella destinazione corrispondano.
   
    La scheda **Ottieni righe** dovrebbe essere simile a questa immagine:
   
    ![provare a ottenere l'elemento dal database di destinazione](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Controllare se è stato trovato l'elemento nuovo o modificato
Selezionare **Nuovo passaggio** > **Aggiungi una condizione** per aprire la scheda **Condizione**.

Nella scheda Condizione:

1. Selezionare la casella a sinistra.
   
    Viene aperto l'elenco **Aggiunge il contenuto dinamico dalle app e dai connettori usati in questo flusso**.
2. Selezionare **valore** dalla categoria **Ottieni righe**.
   
   > [!TIP]
   > Verificare di aver selezionato **valore** dalla categoria **Ottieni righe**. Non selezionare **valore** dalla categoria **Quando viene creato o modificato un elemento**.
   > 
   > 
3. Selezionare **è uguale a** dall'elenco nella casella centrale.
4. Immettere **0** (zero) nella casella sulla destra.
   
    La scheda **Condizione** è ora simile all'immagine seguente:
   
    ![configurare una condizione](media/odata-filters/configure-condition.png)
5. Selezionare **Modifica in modalità avanzata**.
   
    Quando si apre la modalità avanzata, viene visualizzata l'espressione **\@equals(body('Get_rows')?['value'], 0)** nella casella. Modificare l'espressione aggiungendo **length()** attorno alla funzione **body('Get_items')?['valore']**. A questo punto l'intera espressione è simile alla seguente: **@equals(length(body('Get_rows')?['valore']), 0)**
   
    La scheda **Condizione** è ora simile all'immagine seguente:
   
    ![configurare una condizione](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > L'aggiunta della funzione **length()** consente al flusso di controllare l'elenco **valore** e determinare se contiene elementi.
   > 
   > 

Quando il flusso "ottiene" gli elementi dalla destinazione, sono possibili due risultati.

| Risultato | Passaggio successivo |
| --- | --- |
| L'elemento esiste |[Aggiornare l'elemento](odata-filters.md#update-the-item-in-the-destination) |
| L'elemento non esiste |[Creare un nuovo elemento](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> Le immagini delle schede **Inserisci riga** e **Aggiorna riga** illustrate nella figura seguente potrebbero differire da quelle in uso, perché tali schede mostrano i nomi delle colonne nella tabella del database SQL di Microsoft Azure che viene usata nel flusso.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Creare l'elemento nella destinazione
Se l'elemento non esiste nella destinazione, è necessario crearlo usando l'azione **SQL Server - Inserisci riga**.

Nel ramo **Se sì** della **Condizione**:

1. Selezionare **Aggiungi un'azione**, cercare **inserisci riga**, quindi selezionare **SQL Server - Inserisci riga**.
   
    Viene visualizzata la scheda **Inserisci riga**.
2. Dall'elenco **Nome tabella**, selezionare la tabella in cui verrà inserito il nuovo elemento.
   
    La scheda **Inserisci riga** si espande visualizzando tutti i campi della tabella selezionata. I campi con un asterisco (*) sono obbligatori e devono essere popolati per rendere valida la riga.
3. Selezionare ogni campo che si vuole popolare e immettere i dati.
   
    È possibile immettere manualmente i dati, selezionare uno o più token dal **Contenuto dinamico** oppure immettere qualsiasi combinazione di testo e di token nei campi.
   
    La scheda **Inserisci riga** è ora simile all'immagine seguente:
   
    ![configurare una condizione](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Aggiornare l'elemento nella destinazione
Se l'elemento esiste nella destinazione, è necessario aggiornarlo con le modifiche.

1. Aggiungere l'azione **SQL Server - Aggiungi riga** al ramo **Se no** della **Condizione**.
2. Seguire i passaggi nella sezione [Crea l'elemento](odata-filters.md#create-the-item-in-the-destination) di questo documento per popolare i campi della tabella.
   
    ![visualizzare gli ambienti](media/odata-filters/update-row.png)
3. Nella parte superiore della pagina immettere un nome nella casella **Nome flusso** e quindi selezionare **Crea flusso** per salvarlo.
   
    ![denominare il flusso](media/odata-filters/give-the-flow-a-name.png)

A questo punto, ogni volta che un elemento nell'elenco di SharePoint (origine) cambia, viene attivato il flusso, che inserisce un nuovo elemento o aggiorna un elemento esistente nel database SQL di Microsoft Azure (destinazione).

> [!NOTE]
> Il flusso non viene attivato quando un elemento viene eliminato dall'origine. Se si tratta di uno scenario importante, è possibile aggiungere una colonna separata che indichi quando un elemento non è più necessario.
> 
> 

## <a name="learn-more"></a>Altre informazioni
Usare le [operazioni dati](data-operations.md) nei flussi.

