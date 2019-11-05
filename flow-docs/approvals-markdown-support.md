---
title: Usare Markdown per formattare le approvazioni di Microsoft Flow | Microsoft Docs
description: Informazioni su come usare Markdown per formattare le richieste di approvazione Microsoft Flow.
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
ms.openlocfilehash: b82ac7c53c8c018b5e61011e4c1d8b9cdabe9747
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545305"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Usare Markdown nelle richieste di approvazione Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Questo articolo illustra come usare la sintassi [Markdown](https://en.wikipedia.org/wiki/Markdown) per aggiungere tabelle e formattazione avanzate alle richieste di approvazione.

## <a name="headers"></a>Intestazioni

Strutturare i commenti usando le intestazioni. Le intestazioni segmentano i commenti più lunghi, rendendole più facili da leggere.

Avviare una riga con un carattere hash `#` per impostare un'intestazione. Organizzare i commenti con i sottotitoli avviando una riga con caratteri hash aggiuntivi, ad esempio `####`. Sono supportati fino a sei livelli di intestazioni.

**Esempio**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Risultato**

![Esporta flusso](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Paragrafi e interruzioni di riga

Per semplificare la lettura del testo, suddividerlo con paragrafi o interruzioni di riga. Immettere due spazi prima dell'interruzione di riga per iniziare un nuovo paragrafo o immettere due interruzioni di riga consecutive per iniziare un nuovo paragrafo.   
   
**Esempio**

Aggiungere righe tra il testo e il tasto INVIO.
In questo modo il testo viene spaziato meglio e semplifica la lettura.

**Risultato:**    
Aggiungere righe tra il testo e il tasto INVIO.      
In questo modo il testo viene spaziato meglio e semplifica la lettura.


**Esempio 2**

Aggiungere due spazi prima della fine della riga. (spazio, spazio)     
In questo modo viene aggiunto spazio tra i paragrafi.

**Risultato**  
Aggiungere due spazi prima della fine della riga.   

In questo modo viene aggiunto spazio tra i paragrafi.
  

## <a name="lists"></a>Elenchi

Organizzare gli elementi correlati con gli elenchi. È possibile aggiungere elenchi ordinati con numeri o elenchi non ordinati solo con elenchi puntati.

Gli elenchi ordinati iniziano con un numero seguito da un punto per ogni elemento dell'elenco. Gli elenchi non ordinati iniziano con un `*`. Inizia ogni elemento dell'elenco in una nuova riga. In un file o widget Markdown, immettere due spazi prima dell'interruzione di riga per iniziare un nuovo paragrafo o immettere due interruzioni di riga consecutive per iniziare un nuovo paragrafo.   

### <a name="ordered-or-numbered-lists"></a>Elenchi ordinati o numerati

**Esempio**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Risultato**

1. Primo elemento.
2. Secondo elemento.
3. Terzo elemento.

### <a name="bullet-lists"></a>Elenchi puntati

**Esempio**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Risultato**

- Elemento 1
- Elemento 2
- Elemento 3

### <a name="nested-lists"></a>Elenchi annidati

**Esempio**
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

**Risultato**  

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

È possibile impostare i collegamenti ipertestuali del testo per l'URL usando la sintassi di collegamento Markdown standard:

```Markdown
[Link Text](Link URL)
```

**Esempio**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Risultato**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Collegamenti di ancoraggio

Gli ID di ancoraggio vengono assegnati a tutte le intestazioni quando ne viene eseguito il rendering in formato HTML. L'ID è il testo dell'intestazione, con gli spazi sostituiti dai trattini (-) e tutti in lettere minuscole.

**Esempio**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Risultato**

Sintassi per un collegamento di ancoraggio a una sezione...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
L'ID è in lettere minuscole e il collegamento fa distinzione tra maiuscole e minuscole. Assicurarsi quindi di usare lettere minuscole, anche se l'intestazione usa lettere maiuscole.


## <a name="tables"></a>Tabelle

Organizzare i dati strutturati con le tabelle. 

- Posizionare ogni riga della tabella su una riga a se stante 
- Separare le celle della tabella utilizzando il carattere barra verticale `|` 
- Le prime due righe di una tabella impostano le intestazioni di colonna e l'allineamento degli elementi nella tabella
- Usare i due punti (`:`) per dividere l'intestazione e il corpo delle tabelle per specificare l'allineamento delle colonne (a sinistra, al centro, a destra) 
- Per avviare una nuova riga, usare il tag HTML Break (`<br/>`) (funziona all'interno di un wiki ma non altrove)  
- Assicurarsi di terminare ogni riga con un CR o LF. 

**Esempio**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Risultato**  

| Titolo 1 | Titolo 2 | Titolo 3 |  
|-----------|:---------:|-----------:|  
| Cella a1 | Cella a2 | Cella a3 |  
| Cella B1 | Cella B2 | Cella B3<br/>seconda riga di testo |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Enfasi (grassetto, corsivo, barrato)  

È possibile enfatizzare il testo applicando grassetto, corsivo o barrato ai caratteri: 
- Per applicare il corsivo: racchiudere il testo con un asterisco `*` o un carattere di sottolineatura `_`   
- Per applicare grassetto: racchiudere il testo con gli asterischi doppi `**`.    
- Per applicare barrato: racchiudere il testo con caratteri tilde doppi `~~`.   

Combinare questi elementi per applicare più enfasi al testo.    

**Esempio**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Risultato**

Usare l' _enfasi_ nei commenti per esprimere opinioni **complesse** e segnalare le <s>correzioni</s>   
**_Testo in grassetto e corsivo_**    
**~~Testo in grassetto e con attacco~~**  


## <a name="special-characters"></a>Caratteri speciali

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Sintassi</th>
<th width="350px">Esempio/note</th>
</tr>



<tr>
<td>
<p>Per inserire uno dei caratteri seguenti, anteporre un prefisso a una barra rovesciata:</p>

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
