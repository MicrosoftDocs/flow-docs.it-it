---
title: 'Esempio: Usare i processi aziendali (Guida per sviluppatori di Dynamics 365 Customer Engagement) | MicrosoftDocs'
description: Nell'esempio viene illustrato come usare i processi aziendali a livello di codice, ad esempio come recuperare le istanze dei processi aziendali per un record di entità, come recuperare il percorso attivo per un'istanza dei processi aziendali e le relative fasi del processo e come modificare la fase attiva.
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
ms.openlocfilehash: 6f3543b666e471d1f7fa0fe24fc718e50d35aec8
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2019
ms.locfileid: "58352965"
---
# <a name="sample-work-with-business-process-flows"></a>Esempio: Usare i processi aziendali

In questo esempio viene illustrato come usare i processi aziendali a livello di codice, ad esempio come recuperare le istanze dei processi aziendali per un record di entità, come recuperare il percorso attivo per un'istanza dei processi aziendali e le relative fasi del processo e come modificare la fase attiva. Per informazioni su questi concetti, vedere [Usare i processi aziendali con il codice](business-process-flows-code.md)  

 Questo esempio può essere scaricato da [Esempio: Usare i processi aziendali](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per poter eseguire l'esempio è necessario:  

1. Avere accesso a un ambiente Common Data Service.  

2. Avere i privilegi appropriati per le entità Lead, Opportunità e Flusso di lavoro e i record di entità per la  definizione dei processi aziendali usati in questo esempio.  

3. Avere Visual Studio 2015 o versione successiva per eseguire l'esempio.  

4. Avere una connessione Internet per scaricare il progetto di esempio e ripristinare i pacchetti NuGet usati nel progetto di esempio.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Scopo dell'esempio  

1.  Crea un record Lead di esempio. Crea automaticamente un'istanza del processo aziendale "Processo di vendita lead - opportunità" per il record Lead.  

2.  Converte il record Lead in un record Opportunità.  


4.  Recupera le istanze del processo aziendale associate al record "Opportunità" usando il messaggio `RetrieveProcessInstances`. Il primo record nella raccolta restituita corrisponde all'istanza del processo aziendale attiva per il record Opportunità, che in questo caso è "Processo di vendita lead - opportunità".  

5.  Recupera il percorso attivo e le fasi del processo per l'istanza "Processo di vendita lead - opportunità" usando il messaggio `RetrieveActivePath`.  

6.  Recupera la fase attualmente attiva per l'istanza "Processo di vendita lead - opportunità" e chiede se si vuole passare alla fase successiva. In caso affermativo, la fase successiva viene impostata nel percorso attivo come fase attiva dell'istanza "Processo di vendita lead - opportunità".  

7.  Infine, viene chiesto se eliminare i record creati durante l'esecuzione dell'esempio.  

     Di seguito è riportato l'output dell'esempio:  

    ![Esempio dell'output](media/work-with-bpf-sample-output.png "Esempio dell'output")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Eseguire l'esempio  

1. [Scaricare](https://go.microsoft.com/fwlink/p/?LinkId=846108) il progetto di esempio WorkWithBPF di Visual Studio ed estrarlo in una cartella del computer.  

2. Individuare il file `WorkWithBPF.sln` nella cartella estratta e aprirlo in Visual Studio.  

3. Il progetto di esempio usa pacchetti NuGet che devono essere ripristinati prima di eseguire l'esempio. Assicurarsi che in Visual Studio sia abilitato il ripristino automatico dei pacchetti NuGet. Altre informazioni: [Abilitazione e disabilitazione del ripristino dei pacchetti NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    In alternativa, selezionare **Progetto** > **Gestisci pacchetti NuGet** e selezionare **Ripristina** per ripristinare manualmente i pacchetti usati nell'esempio.  

4. Premere F5 o selezionare **Debug** > **Avvia debug**.  

5. Se non sono stati ancora eseguiti esempi, sarà necessario immettere le informazioni per eseguire il codice, oppure immettere il numero di una delle istanze che è stata precedentemente configurata.  


   |                                 Prompt                                  |                                                                                             Descrizione                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Immettere un nome del server di Dynamics 365 e la porta [crm.dynamics.com]       | Digitare il nome del server di Dynamics 365. Il valore predefinito è Dynamics 365 (online)  (crm.dynamics.com) in America del Nord.<br /><br /> Esempio: <br />crm5.dynamics.com |
   | È stato eseguito il provisioning dell'organizzazione in Microsoft Online Services (y/n) [n] |                                                 Digitare **S** se è stato eseguito il provisioning dell'organizzazione in Microsoft Online Services. In caso contrario, digitare **N**.                                                  |
   |                          Immettere dominio\nome utente                          |                                                                                    Digitare l'account Microsoft.                                                                                     |
   |                             Immettere la password                              |                      Digitare la password. I carattere saranno visualizzati come "\*" nella finestra. La password viene salvata in modo sicuro in Gestione credenziali di Microsoft per essere riusata successivamente.                       |
   |                Specificare un numero di organizzazione (1-n) [1]                 |                      Digitare il numero corrispondente selezionandolo dall'elenco delle organizzazioni di appartenenza. Il valore predefinito è 1, vale a dire la prima organizzazione nell'elenco.                       |


6. L'esempio eseguirà tutte le operazioni descritte in [Scopo dell'esempio](#what-this-sample-does). Potrebbero essere richieste opzioni aggiuntive.  

7. Dopo aver completato l'esempio, premere INVIO per chiudere la finestra della console.  

