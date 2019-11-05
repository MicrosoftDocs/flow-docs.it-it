---
title: Usare input e output nei flussi dell'interfaccia utente Web | Microsoft Docs
description: Usare input e output nei flussi dell'interfaccia utente Web.
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
ms.openlocfilehash: f8506846f8081819ad42c70e820397bdc43536e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549347"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Usare input e output nei flussi dell'interfaccia utente Web

[Questo argomento è una versione preliminare della documentazione ed è soggetto a modifiche.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Definire gli input per un flusso dell'interfaccia utente Web

Gli input di un flusso dell'interfaccia utente consentono di passare informazioni da un'origine esterna, ad esempio un database o un altro flusso dell'interfaccia utente al software legacy di destinazione da automatizzare.

Qualsiasi variabile utilizzata (lettura) prima dell'inizializzazione (in genere eseguita tramite i comandi di **Archivio** ) verrà automaticamente considerata come una variabile di input e verrà visualizzata nella scheda **Esegui un flusso dell'interfaccia utente per** le azioni Web.

È possibile usare le variabili tramite l'interpolazione di stringhe, ad esempio, modificare il campo di destinazione del comando clic in "ID =\${elementId}". In alternativa, modificare il campo del valore del comando type in "\${inputText}".

Il comando, **impostare le dimensioni della finestra** e il **tipo** di comando nelle schermate seguenti usano variabili non inizializzate \${Width}, \${Height} e \${search}. Queste variabili diventeranno valori di input.

![Imposta la dimensione e il tipo della finestra](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Imposta la dimensione e il tipo della finestra")

È possibile utilizzare direttamente le variabili in alcuni comandi, ad esempio i campi destinazione/valore del comando forEach sono entrambe variabili, non è necessario racchiuderlo tra "\${}".

Per determinare i comandi che accettano direttamente il nome della variabile, vedere riferimenti ai [comandi Selenium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) .

## <a name="define-outputs-for-a-web-ui-flow"></a>Definire gli output per un flusso dell'interfaccia utente Web

Qualsiasi variabile definita nello script Selenium diventa automaticamente un valore di output. Usare i comandi seguenti per dichiarare le variabili:

[Negozio](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Attributo Store](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[Archivia JSON](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Titolo Archivio](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[valore dell'archivio](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Handle della finestra di archiviazione](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Conteggio XPath di archiviazione](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[Eseguire lo script](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script)(aggiungere la sintassi ' Return ' per restituire l'oggetto che si desidera archiviare alla fine dello script)

## <a name="next-steps"></a>Passaggi successivi

- Informazioni su come [creare flussi dell'interfaccia utente Web](create-web.md).
- Informazioni su come [attivare i flussi dell'interfaccia utente](run-ui-flow.md).

