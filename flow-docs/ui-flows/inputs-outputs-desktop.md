---
title: Usare input e output nei flussi dell'interfaccia utente desktop | Microsoft Docs
description: Usare input e output nei flussi dell'interfaccia utente desktop.
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
ms.openlocfilehash: 88bea3b8a038c01360fc5f3e61dbf30599b5deba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589773"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Usare input e output nei flussi dell'interfaccia utente desktop

[Questo argomento è una versione preliminare della documentazione ed è soggetto a modifiche.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Definire gli input

Gli input consentono di passare informazioni da un'origine esterna, ad esempio un database o qualsiasi connettore supportato, al software legacy che i flussi dell'interfaccia utente automatizzano.

Ad esempio, è possibile utilizzare le informazioni del cliente da un elenco di SharePoint come origine per l'input nel software di contabilità legacy.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>Definire gli input nella creazione guidata flussi dell'interfaccia utente

1. Selezionare "nuovo input"

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Aggiungere un nome, i dati di esempio e una descrizione all'input.

    - I dati di esempio vengono usati durante la registrazione o il test.

    - La descrizione sarà utile per distinguere gli input creati.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Una volta creati gli input, è possibile fare clic su Avanti per usarli in una registrazione.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Usare gli input per passare le informazioni all'applicazione

1. Durante la registrazione, è possibile usare un input in un'app selezionando **Usa input**.

1. Nell'elenco è possibile scegliere tra tre opzioni:

    - Selezionare uno degli input definiti nel passaggio **imposta campi di input** del flusso dell'interfaccia utente.

    - Usare un output definito in precedenza (vedere la sezione output). Questa operazione è utile per passare informazioni tra applicazioni diverse nello stesso flusso dell'interfaccia utente.

    - Creare un nuovo input durante la registrazione. Verrà rilevata nel passaggio di configurazione dei **campi di input** dei flussi dell'interfaccia utente.

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Selezionare la località in cui si vuole usare l'input. Il valore di esempio definito viene usato automaticamente. Nell'esempio seguente "Hello World" è il valore di esempio per il nome di input "My input" e viene aggiunto alla pagina in Microsoft Word.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. In Power automatizzare i **passaggi di registrazione e modifica**, espandere azioni che usano input per visualizzare quello selezionato.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. Quando si attiva il flusso dell'interfaccia utente, è possibile modificare il valore di input in. Per altre informazioni, vedere usare input & output.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Usare gli output per estrarre le informazioni dall'app

Gli output consentono di passare informazioni dal software legacy che i flussi dell'interfaccia utente automatizzano in una destinazione esterna, ad esempio un database o qualsiasi [connettore supportato](https://flow.microsoft.com/connectors/).

Ad esempio, è possibile estrarre le informazioni sui clienti dal software di contabilità legacy e aggiungerle a un elenco di SharePoint.

Gli output possono essere creati solo quando si registra il flusso dell'interfaccia utente.

1. Durante una registrazione, selezionare nel pulsante "Ottieni output" del registratore

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. Selezionare il pulsante "seleziona testo" (questo è l'unico tipo di output disponibile per ora)

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Fare clic su un elemento dell'interfaccia utente per selezionare il relativo testo per l'output. Il valore verrà acquisito automaticamente.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Definire il nome e la descrizione dell'output.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Selezionare **Salva.** 

L'output è ora disponibile nell'area dedicata della procedura guidata

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Ogni output ha:

-  Un nome di output come definito durante la registrazione
-  Descrizione: questo campo può essere molto utile quando si definiscono molti output durante una registrazione e si desidera identificarli con facilità.
-  Nome azione: azione in cui l'output è stato definito nel flusso dell'interfaccia utente

## <a name="delete-an-output-from-a-ui-flow"></a>Eliminare un output da un flusso dell'interfaccia utente

Se l'output non è più necessario, è possibile eliminarlo tornando all'azione associata e rimuovendo il nome di output nel valore dinamico.

## <a name="test-your-ui-flow"></a>Testare il flusso dell'interfaccia utente

Il test dei flussi dell'interfaccia utente consente di convalidare le modifiche e il comportamento di riproduzione appropriato.

1. Opzionale Immettere un nuovo valore nel campo di input. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Fare clic su **test adesso** per visualizzare il software legacy da automatizzare. Si noterà che l'automazione del flusso dell'interfaccia utente riproduce i passaggi registrati. **Per la durata della riproduzione, non interagire con il dispositivo.**

1. Al termine della riproduzione, verrà visualizzato lo stato di esecuzione del flusso dell'interfaccia utente:

    - Per ogni azione, uno stato che indica che il test ha funzionato correttamente e gli input associati.

    - Valore degli output ottenuti per il test.

    - Se è stato generato un errore, sarà possibile vedere quale passaggio è stato problematico con una schermata del momento in cui si è verificato l'errore.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Ulteriori informazioni

- Informazioni su come [attivare il flusso dell'interfaccia utente](run-ui-flow.md) appena creato.

- Se si desidera eseguire altre operazioni con i flussi dell'interfaccia utente, è anche possibile provare i flussi dell'interfaccia utente con parametri di [input e output](inputs-outputs-web.md) .


