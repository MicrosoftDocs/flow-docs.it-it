---
title: Usare espressioni con condizioni. | Microsoft Docs
description: Usare espressioni avanzate quali "and", "or", "Empty", "less" e "Greater" con Microsoft Flow condizioni.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 940ab40b9bac7d76734773805820911a20cd46aa
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548387"
---
# <a name="use-expressions-in-conditions-to-check-multiple-values"></a>Usare espressioni nelle condizioni per verificare più valori
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
In questa procedura dettagliata si apprenderà come usare le espressioni e **le condizioni** per confrontare più valori in **modalità avanzata**.

Quando si crea un flusso, è possibile usare la scheda [**condizione**](add-condition.md#add-a-condition) in modalità di base per confrontare rapidamente un singolo valore con un altro valore. Tuttavia, a volte è necessario confrontare più valori. Ad esempio, è possibile controllare il valore di alcune colonne in un foglio di calcolo o in una tabella di database.

Nelle condizioni è possibile utilizzare qualsiasi combinazione delle espressioni logiche seguenti.

espressione|Descrizione|Esempio
--------|-----------|-------
|[e](#use-the-and-expression)|Accetta due argomenti e restituisce true se entrambi i valori sono true.<br><b>Nota</b>: entrambi gli argomenti devono essere valori booleani.|Questa espressione restituisce false: <br>e (maggiore (1, 10), uguale a (0,0))
|[o](#use-the-or-expression)|Accetta due argomenti e restituisce true se uno degli argomenti è true. <br><b>Nota</b>: entrambi gli argomenti devono essere valori booleani.|Questa espressione restituisce true:<br>o (maggiore (1, 10), uguale a (0,0))
|È uguale a|Restituisce true se due valori sono uguali.|Ad esempio, se parametro1 è someValue, questa espressione restituisce true:<br>Equals (parametri (' parametro1'),' someValue ')
|[meno](#use-the-less-expression)|Accetta due argomenti e restituisce true se il primo argomento è minore del secondo argomento. <br><b>Nota</b>: i tipi supportati sono Integer, float e String.|Questa espressione restituisce true:<br>less (10100)
|lessOrEquals|Accetta due argomenti e restituisce true se il primo argomento è minore o uguale al secondo argomento. <br><b>Nota</b>: i tipi supportati sono Integer, float e String.|Questa espressione restituisce true:<br>lessOrEquals (10, 10)
|[maggiore](#use-the-greater-expression)|Accetta due argomenti e restituisce true se il primo argomento è maggiore del secondo argomento. <br><b>Nota</b>: i tipi supportati sono Integer, float e String.|Questa espressione restituisce false:<br>maggiore (10, 10)
|greaterOrEquals|Accetta due argomenti e restituisce true se il primo argomento è maggiore o uguale al secondo argomento. <br><b>Nota</b>: i tipi supportati sono Integer, float e String.|Questa espressione restituisce false:<br>greaterOrEquals (10100)
|[vuoto](#use-the-empty-expression)|Restituisce true se l'oggetto, la matrice o la stringa è vuota.|Questa espressione restituisce true:<br>Empty ('')
|non|Restituisce l'opposto di un valore booleano. |Questa espressione restituisce true:<br>Not (Contains (' 200 Success ',' fail '))
|Se|Restituisce un valore specifico se l'espressione restituisce true o false.|Questa espressione restituisce "Yes":<br>if (uguale a (1, 1),' Yes ',' No ')

## <a name="prerequisites"></a>Prerequisiti
* Accesso a Microsoft Flow.
* Un foglio di calcolo con le tabelle descritte più avanti in questa procedura dettagliata. Assicurarsi di salvare il foglio di calcolo in un percorso, ad esempio Dropbox o Microsoft OneDrive, in modo che Microsoft Flow possa accedervi.
* Microsoft Office 365 Outlook (mentre si usa Office 365 Outlook, è possibile usare qualsiasi servizio di posta elettronica supportato nei flussi).

## <a name="use-the-or-expression"></a>Usare l'espressione or
In alcuni casi il flusso di lavoro deve eseguire un'azione se il valore di un elemento è VALUEA **o** valoreB. È possibile, ad esempio, tenere traccia dello stato delle attività in una tabella del foglio di calcolo. Si supponga che nella tabella sia presente una colonna denominata *status* e che i valori possibili nella colonna *status* siano:

* **completato**
* **bloccato**
* **non necessari**
* **non avviata**

Ecco un esempio di come potrebbe apparire il foglio di calcolo:

![foglio di calcolo di esempio](./media/use-expressions-in-conditions/spreadsheet-table.png)

Dato il foglio di calcolo precedente, si vuole usare Microsoft Flow per rimuovere tutte le righe con una colonna *stato* impostata su *completato* o non *necessario*.

È ora di creare il flusso.

### <a name="start-with-a-blank-flow"></a>Inizia con un flusso vuoto
1. Accedere [Microsoft Flow](https://flow.microsoft.com).

    ![Accedi](includes/media/modern-approvals/sign-in.png)
2. Selezionare la scheda **flussi personali** .

    ![Selezionare flussi personali](includes/media/modern-approvals/select-my-flows.png)
3. Selezionare **Crea da zero**.

    ![Crea da zero](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>Aggiungere un trigger al flusso
1. Cercare **pianificazione**, quindi selezionare il trigger **pianificazione-ricorrenza**

    ![trigger di pianificazione](includes/media/schedule-trigger/schedule-trigger.png)
2. Impostare la pianificazione in modo che venga eseguita una volta al giorno.

    ![Imposta pianificazione](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>Selezionare il foglio di calcolo e ottenere tutte le righe
1. Selezionare **nuovo passaggio** > **Aggiungi un'azione**.

    ![Nuovo passaggio](includes/media/new-step/action.png)
2. Cercare le **righe**e quindi selezionare **Excel-Ottieni righe**.

    Nota: selezionare l'azione "Ottieni righe" che corrisponde al foglio di calcolo che si sta usando. Ad esempio, se si usano fogli Google, selezionare **Fogli Google-Ottieni righe**.

    ![Ottieni righe](includes/media/new-step/get-excel-rows.png)
3. Selezionare l'icona della cartella nella casella **nome file** , passare a, quindi selezionare il foglio di calcolo che contiene i dati.

    ![Seleziona foglio di calcolo](includes/media/new-step/select-spreadsheet.png)
4. Selezionare la tabella che contiene i dati nell'elenco **nome tabella** .

    ![Seleziona tabella](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>Controllare la colonna stato di ogni riga
1. Selezionare **nuovo passaggio** > **altro** > **aggiungere un applica a ogni**.

    ![Seleziona tabella](includes/media/new-step/apply-to-each.png)
2. Aggiungere il token di **valore** alla casella **selezionare un output dai passaggi precedenti** .

    ![Seleziona tabella](includes/media/apply-to-each/add-value-token.png)
3. Selezionare **Aggiungi una condizione** > **modifica in modalità avanzata**.
4. Aggiungere la seguente espressione **o** . Questa espressione **o** controlla il valore di ogni riga nella tabella (una riga è nota come elemento quando vi si accede in un'espressione). Se il valore della colonna **stato** è *completato* **o** non *necessario*, l'espressione **or** restituisce "true".

    L'espressione **or** viene visualizzata come illustrato di seguito:

    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````

    La scheda **condizione** è simile a questa immagine:

    ![o immagine dell'espressione](./media/use-expressions-in-conditions/or-expression.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>Elimina le righe corrispondenti dal foglio di calcolo
1. Selezionare **Aggiungi un'azione** nel ramo **se sì, non fare nulla** della condizione.
2. Cercare **Elimina riga**, quindi selezionare **Excel-Elimina riga**.

    ![Elimina immagine riga](includes/media/new-step/select-delete-excel-row.png)
3. Nella casella **nome file** cercare e selezionare il file del foglio di calcolo che contiene i dati che si desidera eliminare.
4. Nell'elenco **nome tabella** selezionare la tabella che contiene i dati.
5. Inserire il token **ID di riga** nella casella **ID riga** .

    ![file foglio di calcolo](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>Assegnare un nome al flusso e salvarlo
1. Assegnare un nome al flusso e quindi selezionare il pulsante **Crea flusso** .

    ![salvare il flusso](./media/use-expressions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-expression"></a>Eseguire il flusso con l'espressione o
Il flusso viene eseguito dopo il salvataggio. Se è stato creato il foglio di calcolo illustrato in precedenza in questa procedura dettagliata, di seguito viene illustrato l'aspetto dell'oggetto dopo il completamento dell'esecuzione:

![espressione or completata](./media/use-expressions-in-conditions/spreadsheet-table-after-or-expression-runs.png)

Si noti che tutti i dati delle righe con "completed" o "superflui" nella colonna stato sono stati eliminati.

## <a name="use-the-and-expression"></a>Usare l'espressione and
Si supponga di disporre di una tabella di fogli di calcolo con due colonne. I nomi delle colonne sono status e assegnati. Si supponga inoltre di voler eliminare tutte le righe se il valore della colonna stato è "bloccato" e il valore della colonna assegnata è "John Wonder".  Per eseguire questa operazione, seguire tutti i passaggi descritti in precedenza in questa procedura dettagliata. Tuttavia, quando si modifica la scheda **condizione** in modalità avanzata, usare l'espressione **and** illustrata qui:

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

La scheda **condizione** è simile a questa immagine:

![e immagine dell'espressione](./media/use-expressions-in-conditions/and-expression.png)

### <a name="run-the-flow-with-the-and-expression"></a>Eseguire il flusso con l'espressione and
Se è stata seguita, il foglio di calcolo sarà simile all'immagine seguente:

![prima ed esecuzione](./media/use-expressions-in-conditions/spreadsheet-table-before-and-expression-runs.png)

Al termine dell'esecuzione del flusso, il foglio di calcolo sarà simile all'immagine seguente:

![dopo ed eseguito](./media/use-expressions-in-conditions/spreadsheet-table-after-and-expression-runs.png)

## <a name="use-the-empty-expression"></a>Usa espressione vuota
Si noti che ora sono presenti diverse righe vuote nel foglio di calcolo. Per rimuoverli, usare l'espressione **vuota** per identificare tutte le righe che non hanno testo nelle colonne assegnato e stato.

Per eseguire questa operazione, seguire tutti i passaggi elencati nella sezione **usare l'espressione and** precedentemente in questa procedura dettagliata. Tuttavia, quando si modifica la scheda **condizione** in modalità avanzata, usare l'espressione vuota in questo modo:

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

La scheda **condizione** è simile a questa immagine:

![immagine espressione vuota](./media/use-expressions-in-conditions/empty-expression.png)

Al termine dell'esecuzione del flusso, il foglio di calcolo sarà simile all'immagine seguente:

![dopo le esecuzioni vuote](./media/use-expressions-in-conditions/spreadsheet-table-after-empty-expression-runs.png)

Si noti che le righe aggiuntive vengono rimosse dalla tabella.

## <a name="use-the-greater-expression"></a>Usa espressione maggiore
Si supponga di aver acquistato biglietti di baseball per i colleghi e che si stia usando un foglio di calcolo per assicurarsi di essere rimborsati da ogni persona. È possibile creare rapidamente un flusso che invia un messaggio di posta elettronica giornaliero a ogni persona che non ha pagato l'intero importo.

Usare l'espressione **Greater** per identificare i dipendenti che non hanno pagato l'intero importo. È quindi possibile inviare automaticamente un messaggio di posta elettronica di promemoria a coloro che non hanno pagato completamente.

Ecco una visualizzazione del foglio di calcolo:

![Visualizzazione del foglio di calcolo](./media/use-expressions-in-conditions/tickets-spreadsheet-table.png)

Di seguito è illustrata l'implementazione dell'espressione **Greater** che identifica tutte le persone che hanno pagato un importo inferiore rispetto a quello dovuto:

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-expression"></a>Usa espressione less
Si supponga di aver acquistato biglietti di baseball per i colleghi e che si stia usando un foglio di calcolo per assicurarsi di essere rimborsati da ogni persona entro la data in cui tutti sono stati concordati. È possibile creare un flusso che invii un messaggio di promemoria a ogni persona che non ha pagato l'importo completo se la data corrente è inferiore a un giorno prima della scadenza.

Usare l'espressione **and** insieme all'espressione **less** poiché ci sono due condizioni da convalidare:


|          Condizione da convalidare          | espressione da usare |                    Esempio                     |
|-----------------------------------------|-------------------|------------------------------------------------|
|   L'importo totale è dovuto a pagamento?    |      maggiore      |   @greater(Item ()? [' Scadenza:'], elemento ()? [' A pagamento '])    |
| La data di scadenza è inferiore a un giorno? |       meno        | @less(Item ()? [' DueDate '], addDays (utcNow (), 1)) |

## <a name="combine-the-greater-and-less-expressions-in-an-and-expression"></a>Combinare le espressioni Greater e less in un'espressione and
Utilizzare l'espressione **Greater** per identificare i dipendenti che hanno pagato meno dell'importo totale dovuto e utilizzare l'espressione **less** per determinare se la data di scadenza del pagamento è inferiore a un giorno dalla data corrente. Puoi quindi **inviare un'azione Invia un messaggio di posta elettronica** per inviare un promemoria semplice a coloro che non hanno pagato completamente e la data di scadenza è inferiore a un giorno.

Ecco una visualizzazione della tabella del foglio di calcolo:

![Visualizzazione del foglio di calcolo](./media/use-expressions-in-conditions/spreadsheet-table-due-date.png)

Di seguito è illustrata l'implementazione dell'espressione **and** che identifica tutte le persone che hanno pagato un importo inferiore rispetto a quello dovuto e la data di scadenza è inferiore a un giorno dalla data corrente:

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="use-functions-in-expressions"></a>Usare le funzioni nelle espressioni

Alcune espressioni ottengono i valori dalle azioni di runtime che potrebbero non essere ancora presenti all'avvio dell'esecuzione di un flusso. Per fare riferimento a questi valori nelle espressioni o utilizzarli, è possibile utilizzare le funzioni fornite dal linguaggio di definizione del flusso di lavoro. Altre informazioni: [riferimento alle funzioni per il linguaggio di definizione del flusso di lavoro in Microsoft Flow](https://docs.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference)
