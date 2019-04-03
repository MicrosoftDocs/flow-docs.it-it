---
title: Usare Markdown per formattare le approvazioni di Microsoft Flow| Microsoft Docs
description: Informazioni su come usare Markdown per formattare le richieste di approvazione di Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7611ccb8bba9f2647402df46753de284016d7cd4
ms.sourcegitcommit: 014f64bcc4aed27794d5c7efc2eca241d271518e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58656132"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Usare Markdown nelle richieste di approvazione di Microsoft Flow

Questo articolo illustra come usare la sintassi [Markdown](https://en.wikipedia.org/wiki/Markdown) per aggiungere formattazione RTF e tabelle alle richieste di approvazione.

## <a name="headers"></a>Intestazioni

Strutturare i commenti con le intestazioni. Le intestazioni consentono di segmentare i commenti più lunghi, migliorandone la leggibilità.

Iniziare una riga con un carattere cancelletto `#` per impostare un'intestazione. Organizzare le osservazioni con sottotitoli iniziando una riga con caratteri cancelletto aggiuntivi, ad esempio `####`. Sono supportati fino a sei livelli di intestazioni.

**Esempio:**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Risultato:**

![Esportare il flusso](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Paragrafi e interruzioni di riga

È possibile migliorare la leggibilità del testo suddividendolo in paragrafi o con interruzioni di riga. Immettere due spazi prima dell'interruzione di riga per iniziare un nuovo paragrafo o immettere due interruzioni di riga consecutive per iniziare un nuovo paragrafo.   
   
**Esempio**

Aggiungere righe nel testo con il tasto INVIO.
In questo modo si migliora la spaziatura del testo e quindi anche la leggibilità.

**Risultato:**   
Aggiungere righe nel testo con il tasto INVIO.      
In questo modo si migliora la spaziatura del testo e quindi anche la leggibilità.


**Esempio 2**

Aggiungere due spazi prima della fine della riga.(spazio, spazio)     
In questo modo viene aggiunto spazio tra i paragrafi.

**Risultato:**  
Aggiungere due spazi prima della fine della riga.   

In questo modo viene aggiunto spazio tra i paragrafi.
  

## <a name="lists"></a>Elenchi

Organizzare gli elementi correlati con gli elenchi. È possibile aggiungere elenchi ordinati con numeri o elenchi non ordinati con solo punti elenco.

Gli elenchi ordinati iniziano con un numero seguito da un punto per ogni elemento dell'elenco. Gli elenchi non ordinati iniziano con un `*`. Iniziare ciascun elemento dell'elenco in una nuova riga. In un file Markdown o widget, immettere due spazi prima dell'interruzione di riga per iniziare un nuovo paragrafo o immettere due interruzioni di riga consecutive per iniziare un nuovo paragrafo.   

### <a name="ordered-or-numbered-lists"></a>Elenchi ordinati o numerati

**Esempio:**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Risultato:**

1. Primo elemento.
2. Secondo elemento.
3. Terzo elemento.

### <a name="bullet-lists"></a>Elenchi puntati

**Esempio:**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Risultato:**

- Elemento 1
- Elemento 2
- Elemento 3

### <a name="nested-lists"></a>Elenchi annidati

**Esempio:**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**Risultato:**  

1. Primo elemento.

    - Elemento 1
    - Elemento 2
    - Elemento 3
2. Secondo elemento.
    - Elemento annidato 1
    - Elemento annidato 2
    - Elemento annidato 3


## <a name="links"></a>Collegamenti

Gli URL HTTP e HTTPS vengono formattati automaticamente come collegamenti. 

È possibile impostare i collegamenti ipertestuali per l'URL usando la sintassi di collegamento markdown standard:

```Markdown
[Link Text](Link URL)
```

**Esempio:**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Risultato:**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Collegamenti di ancoraggio

Gli ID di ancoraggio vengono assegnati a tutti i titoli per il rendering in formato HTML. L'ID è il testo del titolo, con gli spazi sostituiti dai trattini (-) e tutte le lettere minuscole.

**Esempio:**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Risultato:**

Sintassi per un collegamento di ancoraggio a una sezione...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
L'ID è tutto in lettere minuscole e per il collegamento viene fatta distinzione tra maiuscole e minuscole, pertanto assicurarsi di usare caratteri minuscoli, anche se il titolo usa lettere maiuscole.


## <a name="tables"></a>Tabelle

Organizzare i dati strutturati con le tabelle. 

- Inserire ogni riga della tabella su una riga a parte 
- Separare le celle della tabella con il carattere barra verticale `|` 
- Le prime due righe di una tabella impostano le intestazioni di colonna e l'allineamento degli elementi nella tabella
- Usare i due punti (`:`) quando si divide l'intestazione e il corpo delle tabelle per specificare l'allineamento delle colonne (a sinistra, al centro, a destra) 
- Per iniziare una nuova riga, usare il tag di interruzione HTML (`<br/>`) (funziona all'interno di un wiki ma non altrove)  
- Assicurarsi di terminare ogni riga con un carattere di ritorno a capo (CR) o di avanzamento riga (LF). 

**Esempio:**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Risultato:**  

| Intestazione 1 | Intestazione 2 | Intestazione 3 |  
|-----------|:---------:|-----------:|  
| Cella A1 | Cella A2 | Cella A3 |  
| Cella B1 | Cella B2 | Cella B3<br/>Seconda riga di testo |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Enfasi (grassetto, corsivo, barrato)  

È possibile evidenziare il testo applicando il formato grassetto, corsivo o barrato ai caratteri: 
- Per applicare il corsivo: racchiudere il testo tra asterischi `*` o caratteri di sottolineatura `_`   
- Per applicare il grassetto: racchiudere il testo tra asterischi doppi `**`.    
- Per applicare il barrato: racchiudere il testo tra caratteri tilde doppi `~~`.   

Combinare questi elementi per applicare più effetti di enfasi al testo.    

**Esempio:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Risultato:**

Usare gli _effetti di enfasi_ nei commenti per esprimere opinioni **importanti** e sottolineare <s>correzioni</s>   
**_Testo in grassetto e corsivo_**   
**~~Testo in grassetto e barrato~~**  


## <a name="special-characters"></a>Caratteri speciali

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Sintassi</th>
<th width="350px">Esempio/note</th>
</tr>



<tr>
<td>
<p>Per inserire uno dei caratteri seguenti, anteporre una barra rovesciata come prefisso:</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Alcuni esempi di inserimento di caratteri speciali
<p>Immettere ```\\``` per ottenere \\ </p>
<p>Immettere ```\_``` per ottenere _ </p>
<p>Immettere ```\#``` per ottenere \# </p>
<p>Immettere ```\(``` per ottenere \( </p>
<p>Immettere ```\.``` per ottenere \. </p>
<p>Immettere ```\!``` per ottenere \! </p>
</td>
</tr>

</tbody>
</table>
