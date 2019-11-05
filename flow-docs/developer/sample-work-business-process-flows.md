---
title: 'Esempio: usare i flussi del processo di business | MicrosoftDocs'
description: Nell'esempio viene illustrato come utilizzare a livello di codice i flussi del processo di business, ad esempio il recupero delle istanze di flusso del processo di business per un record di entità, il recupero del percorso attivo per un'istanza del flusso del processo di business e le fasi del processo e la modifica del fase attiva.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 2eb6f7586ddc8d5bf51b9c57f91bbc5c7c10131b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547760"
---
# <a name="sample-work-with-business-process-flows"></a>Esempio: usare i flussi del processo di business
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

In questo esempio viene illustrato come utilizzare a livello di codice i flussi del processo di business, ad esempio il recupero delle istanze di flusso del processo di business per un record di entità, il recupero del percorso attivo per un'istanza del flusso del processo di business e le fasi del processo e la modifica del fase attiva. Per informazioni su questi concetti, vedere [usare i flussi del processo di business tramite codice](business-process-flows-code.md)  

 Questo esempio è disponibile per il download da [esempio: usare i flussi del processo di business](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Prima di poter eseguire l'esempio:  

1. Avere accesso a un ambiente di Common Data Service.  

2. Disporre dei privilegi appropriati per le entità lead, opportunità e flusso di lavoro e i record di entità di definizione del flusso dei processi di business usati in questo esempio.  

3. Per eseguire l'esempio, fare in modo che Visual Studio 2015 o versione successiva.  

4. Disporre di una connessione Internet per scaricare il progetto di esempio e per ripristinare i pacchetti NuGet usati nel progetto di esempio.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Cosa fa questo esempio  

1.  Crea un record lead di esempio. In questo modo viene creata automaticamente un'istanza del flusso del processo di business "lead to Opportunity Sales process" per il record lead.  

2.  Converte il record principale in un record di opportunità.  


4.  Recupera le istanze del flusso del processo di business associate al record "opportunity" utilizzando il messaggio di `RetrieveProcessInstances`. Il primo record nella raccolta restituita è l'istanza di flusso del processo di business attivo per il record di opportunità, che in questo caso è "lead to Opportunity Sales process".  

5.  Recupera il percorso attivo e le fasi del processo per l'istanza "lead to Opportunity Sales process" utilizzando il messaggio di `RetrieveActivePath`.  

6.  Recupera la fase attualmente attiva per l'istanza "lead to Opportunity Sales process" e chiede all'utente se passare alla fase successiva. Quando si conferma lo spostamento, imposta la fase successiva nel percorso attivo come fase attiva per l'istanza "lead to Opportunity Sales process".  

7.  Infine, chiede all'utente se eliminare i record creati durante l'esecuzione dell'esempio.  

     Ecco l'output dell'esempio:  

    ![Esempio di output](media/work-with-bpf-sample-output.png "Esempio di output")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Eseguire l'esempio  

1. [Scaricare](https://go.microsoft.com/fwlink/p/?LinkId=846108) il progetto di esempio WorkWithBPF di Visual Studio ed estrarlo in una cartella nel computer.  

2. Individuare il file di `WorkWithBPF.sln` nella cartella estratta e aprirlo in Visual Studio.  

3. Il progetto di esempio usa i pacchetti NuGet che devono essere ripristinati prima di eseguire l'esempio. Assicurarsi che il ripristino automatico dei pacchetti NuGet sia abilitato in Visual Studio. Altre informazioni: [Abilitazione e disabilitazione del ripristino del pacchetto NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    In alternativa, selezionare **Project** > **Gestisci pacchetti NuGet**e selezionare **Ripristina** per ripristinare manualmente i pacchetti usati nell'esempio.  

4. Premere F5 o selezionare **debug** > **avviare il debug**.  

5. Se in precedenza non è stato eseguito uno degli esempi prima, sarà necessario immettere le informazioni per eseguire il codice. in caso contrario, immettere il numero di una delle istanze configurate in precedenza.  


   |                                 Prompt                                  |                                                                                             Descrizione                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Immettere il nome e la porta del server Dynamics 365 [crm.dynamics.com]       | Digitare il nome del server Dynamics 365. Il valore predefinito è Dynamics 365 (online) (crm.dynamics.com) in America del Nord.<br /><br /> Esempio <br />crm5.dynamics.com |
   | Viene effettuato il provisioning dell'organizzazione in Microsoft Servizi online (y/n) [n] |                                                 Digitare **y** se si tratta di un'organizzazione con provisioning di Microsoft servizi online. In caso contrario, digitare **n**.                                                  |
   |                          Immettere dominio\nomeutente                          |                                                                                    Digitare il account Microsoft.                                                                                     |
   |                             Immettere la password                              |                      Digitare la password. I caratteri vengono visualizzati come "\*" nella finestra. La password viene salvata in modo sicuro in Microsoft Credential Manager per un successivo riutilizzo.                       |
   |                Specificare un numero di organizzazione (1-n) [1]                 |                      Dall'elenco delle organizzazioni a cui si appartiene, digitare il numero corrispondente. Il valore predefinito è 1, che indica la prima organizzazione nell'elenco.                       |


6. L'esempio eseguirà le operazioni descritte in [questo esempio](#what-this-sample-does) e potrebbe richiedere opzioni aggiuntive.  

7. Al termine dell'esempio, premere INVIO per chiudere la finestra della console.  

