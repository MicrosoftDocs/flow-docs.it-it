---
title: Informazioni su come modificare i flussi dell'interfaccia utente Web | Microsoft Docs
description: Informazioni su come modificare i flussi dell'interfaccia utente Web.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 263f8634b2435217fba436e68ab7e744dd3b52b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549577"
---
# <a name="edit-web-ui-flows"></a>Modificare i flussi dell'interfaccia utente Web

[Questo argomento è una versione preliminare della documentazione ed è soggetto a modifiche.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

I flussi dell'interfaccia utente Web automatizzano i siti Web in esecuzione nella [prossima versione di Microsoft Edge](https://www.microsoftedgeinsider.com/) o Google Chrome. Dopo aver [creato un flusso dell'interfaccia utente Web](create-web.md), potrebbe essere necessario modificarlo. Attenersi alla procedura descritta in questo documento per informazioni su come modificare i flussi dell'interfaccia utente Web.

## <a name="edit-in-selenium-ide"></a>Modifica nell'IDE Selenium

Usare l'IDE Selenium per modificare i flussi dell'interfaccia utente Web.

>[!NOTE]
>La modifica nell'IDE di Selenium è destinata a utenti e sviluppatori avanzati.

È possibile fare riferimento ai [comandi del selenio](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) per apprendere come modificare lo script.

L'IDE Selenio suggerisce selettori diversi e uno predefinito quando la destinazione è un elemento dell'interfaccia utente. È anche possibile definire un nuovo selettore se nessuno dei selettori proposti è appropriato. Questa situazione si verifica in genere quando la struttura HTML del sito Web è altamente dinamica.

Di seguito è riportato un esempio di possibili selettori identificati dall'IDE selenico:

![Selettori possibili](../media/edit-web/possible-selectors.png "Selettori possibili")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Accesso a una proprietà di una variabile oggetto o di un elemento di una variabile di matrice * *

Questa funzionalità avanzata consente di usare la sintassi come \${foo. bar} per accedere alla proprietà barra dell'oggetto Foo. È anche possibile scrivere nella proprietà barra di foo usando foo. bar come proprietà Value in un comando Store. È anche possibile usare la sintassi come \${foo [0]} per accedere all'elemento in corrispondenza dell'indice 0 nella matrice foo.

## <a name="next-steps"></a>Passaggi successivi

- [Creare flussi dell'interfaccia utente Web](create-web.md)
- [Esegui flussi dell'interfaccia utente](run-ui-flow.md)
