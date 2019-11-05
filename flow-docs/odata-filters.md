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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: be5863c51e17bdba32d79891725a81b386ec2e90
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548940"
---
# <a name="filter-and-copy-data-with-microsoft-flow"></a>Filtrare e copiare i dati con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Questa procedura dettagliata illustra come creare un flusso che monitora un'origine per gli elementi nuovi o modificati e quindi copia tali modifiche in una destinazione. È possibile creare un flusso di questo tipo se gli utenti immettono dati in un'unica posizione, ma il team lo necessita in un percorso o in un formato diverso.

Mentre questa procedura dettagliata copia i dati da un [elenco](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) Microsoft SharePoint (origine) a una tabella del [database SQL di Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) (destinazione), è possibile copiare i dati tra i servizi più di [150](https://flow.microsoft.com/connectors/) supportati da Microsoft Flow.

> [!IMPORTANT]
> Le modifiche apportate nella destinazione non vengono copiate nell'origine perché le sincronizzazioni bidirezionali non sono supportate. Se si tenta di configurare una sincronizzazione bidirezionale, si creerà un ciclo infinito in cui le modifiche vengono inviate all'infinito tra l'origine e la destinazione.
> 
> 

## <a name="prerequisites"></a>Prerequisiti
* Accesso a un'origine dati e a una destinazione. Questa procedura dettagliata non include i passaggi per creare l'origine e la destinazione.
* Accesso a [Microsoft Flow](https://flow.microsoft.com).
* Conoscenza di base del modo in cui vengono archiviati i dati.
* Familiarità con le nozioni di base per la creazione di flussi. È possibile esaminare come aggiungere [azioni, trigger](multi-step-logic-flow.md#add-another-action)e [condizioni](add-condition.md). Nei passaggi seguenti si presuppone che si sappia come eseguire queste azioni.

> [!TIP]
> Non è necessario che ogni nome di colonna nell'origine e nella destinazione corrisponda, ma è necessario fornire i dati per tutte le colonne *obbligatorie* quando si inserisce o si aggiorna un elemento. Microsoft Flow identifica i campi necessari.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Panoramica rapida dei passaggi
Se si ha familiarità con Microsoft Flow, usare questi passaggi rapidi per copiare i dati da un'origine dati a un'altra:

1. Identificare l'origine da monitorare e la destinazione in cui verranno copiati i dati modificati. Confermare di avere accesso a entrambi.
2. Identificare almeno una colonna che identifichi in modo univoco gli elementi nell'origine e nella destinazione. Nell'esempio seguente viene usata la colonna **title** , ma è possibile usare qualsiasi colonna desiderata.
3. Configurare un trigger che monitora l'origine per le modifiche.
4. Eseguire una ricerca nella destinazione per determinare se l'elemento modificato esiste.
5. Usare una **condizione** simile alla seguente:
   * Se l'elemento nuovo o modificato non esiste nella destinazione, crearlo.
   * Se l'elemento nuovo o modificato esiste nella destinazione, aggiornarlo.
6. Attivare il flusso, quindi verificare che gli elementi nuovi o modificati vengano copiati dall'origine alla destinazione.

> [!NOTE]
> Se non è stata creata in precedenza una connessione a SharePoint o al database SQL di Azure, seguire le istruzioni visualizzate quando viene richiesto di effettuare l'accesso.
> 
> 

Ecco i passaggi dettagliati per creare il flusso.

## <a name="monitor-the-source-for-changes"></a>Monitorare l'origine delle modifiche
1. Accedere [Microsoft Flow](https://flow.microsoft.com), selezionare **flussi personali** > **Crea da zero**.
2. Cercare **sharepoint** > selezionare il trigger **SharePoint-quando viene creato o modificato un elemento** dall'elenco di trigger.
3. Immettere l' **indirizzo del sito** e quindi selezionare il **nome dell'elenco** nella scheda **quando viene creato o modificato un elemento** .
   
    Specificare l' **indirizzo del sito** e il **nome elenco** per l'elenco di SharePoint in cui vengono monitorati i flussi per gli elementi nuovi o aggiornati.
   
    ![configurare il trigger di SharePoint](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Cerca l'elemento nuovo o modificato nella destinazione
Per cercare l'elemento nuovo o modificato si usa l'azione **SQL Server Get rows** .

1. Selezionare **nuovo passaggio** > **Aggiungi un'azione**.
2. Cercare **Ottieni righe**, selezionare **SQL Server-Ottieni righe**, quindi selezionare la tabella che si vuole monitorare dall'elenco **nome tabella** .
3. Selezionare **Mostra opzioni avanzate**.
4. Nella casella **query filtro** immettere **title EQ "** , selezionare il token del **titolo** dall'elenco di contenuto dinamico, quindi immettere **"** .
   
    Nel passaggio precedente si presuppone che i titoli delle righe nell'origine e nella destinazione siano corrispondenti.
   
    La scheda **Ottieni righe** dovrebbe ora apparire come questa immagine:
   
    ![provare a ottenere l'elemento dal database di destinazione](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Controllare se l'elemento nuovo o modificato è stato trovato
Selezionare **nuovo passaggio** > **aggiungere una condizione** per aprire la scheda **condizione** .

Nella scheda condizione:

1. Selezionare la casella a sinistra.
   
    Viene visualizzato il **Aggiungi contenuto dinamico dalle app e dai connettori usati in questo elenco di flussi** .
2. Selezionare **valore** dalla categoria **Ottieni righe** .
   
   > [!TIP]
   > Confermare di aver selezionato **valore** dalla categoria **Ottieni righe** . Non selezionare **valore** dalla categoria **quando viene creato o modificato un elemento** .
   > 
   > 
3. Selezionare **è uguale a** nell'elenco nella casella al centro.
4. Immettere **0** (zero) nella casella sul lato destro.
   
    La scheda **condizione** è ora simile all'immagine seguente:
   
    ![configurare una condizione](media/odata-filters/configure-condition.png)
5. Selezionare **modifica in modalità avanzata**.
   
    Quando si apre la modalità avanzata, viene visualizzato **\@uguale a (Body (' Get_rows ')? [' valore '], 0)** espressione nella casella. Modificare questa espressione aggiungendo **Length ()** intorno al **corpo (' Get_items ')? [' funzione value ']** . L'intera espressione ora appare come questa: **@equals(length (Body (' Get_rows ')? [' valore ']), 0)**
   
    La scheda **condizione** è ora simile all'immagine seguente:
   
    ![configurare una condizione](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > L'aggiunta della funzione **Length ()** consente al flusso di controllare l'elenco di **valori** e determinare se contiene elementi.
   > 
   > 

Quando il flusso "ottiene" gli elementi dalla destinazione, sono disponibili due possibili risultati.

| Risultato | Passaggio successivo |
| --- | --- |
| L'elemento esiste |[Aggiornare l'elemento](odata-filters.md#update-the-item-in-the-destination) |
| L'elemento non esiste |[Crea un nuovo elemento](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> Le immagini delle schede **Inserisci riga** e **Aggiorna riga** illustrate di seguito possono essere diverse da quelle della propria organizzazione, perché mostrano i nomi delle colonne nella tabella del database SQL di Azure usata nel flusso.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Creare l'elemento nella destinazione
Se l'elemento non esiste nella destinazione, crearlo utilizzando l'azione **SQL Server-Inserisci riga** .

Nel ramo **If Yes** della **condizione**:

1. Selezionare **Aggiungi un'azione**, cercare **Inserisci riga**, quindi selezionare **SQL Server-Inserisci riga**.
   
    Verrà visualizzata la scheda **Inserisci riga** .
2. Dall'elenco **nome tabella** selezionare la tabella in cui verrà inserito il nuovo elemento.
   
    La scheda **Inserisci riga** consente di espandere e visualizzare tutti i campi della tabella selezionata. I campi con un asterisco (*) sono obbligatori e devono essere popolati affinché la riga sia valida.
3. Selezionare ogni campo che si vuole popolare e immettere i dati.
   
    È possibile immettere i dati manualmente, selezionare uno o più token dal **contenuto dinamico**oppure immettere una qualsiasi combinazione di testo e token nei campi.
   
    La scheda **Inserisci riga** ora è simile a questa immagine:
   
    ![configurare una condizione](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Aggiornare l'elemento nella destinazione
Se l'elemento è presente nella destinazione, aggiornarlo con le modifiche.

1. Aggiungere l'azione **SQL Server-Update Row** al ramo **if no** della **condizione**.
2. Attenersi alla procedura descritta nella sezione [creare l'elemento](odata-filters.md#create-the-item-in-the-destination) di questo documento per popolare i campi della tabella.
   
    ![Visualizza ambienti](media/odata-filters/update-row.png)
3. Nella parte superiore della pagina immettere un nome per il flusso nella casella **Nome flusso** e quindi selezionare **Crea flusso** per salvarlo.
   
    ![assegnare un nome al flusso](media/odata-filters/give-the-flow-a-name.png)

A questo punto, ogni volta che viene modificato un elemento nell'elenco di SharePoint (origine), il flusso viene attivato e viene inserito un nuovo elemento o viene aggiornato un elemento esistente nel database SQL di Azure (destinazione).

> [!NOTE]
> Il flusso non viene attivato quando viene eliminato un elemento dall'origine. Se si tratta di uno scenario importante, è consigliabile aggiungere una colonna separata che indica quando un elemento non è più necessario.
> 
> 

## <a name="learn-more"></a>Ulteriori informazioni
Usare [le operazioni sui dati](data-operations.md) nei flussi.

