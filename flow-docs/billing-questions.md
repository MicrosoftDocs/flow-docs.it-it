---
title: Domande su fatturazione e misurazione | Microsoft Docs
description: Risposte alle domande frequenti relative alla fatturazione e alla misurazione in Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 69fecb42ba2b89f7a3f5b7541f62a4ee984832ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546209"
---
# <a name="billing-and-metering-questions"></a>Domande su fatturazione e misurazione
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Questo articolo fornisce le risposte alle domande frequenti relative alla fatturazione e alla misurazione in Microsoft Flow.

>[!NOTE]
> PowerApps e Microsoft Flow utilizzeranno un [nuovo modello di licenza](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) a partire dall'1 ottobre 2019. 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Dove è possibile trovare I piani tariffari disponibili?

Vedere la [pagina dei prezzi](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Dove posso trovare il mio piano?

Vedere la [pagina dei prezzi](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Ricerca per categorie i piani di cambio?

Nel menu di navigazione superiore selezionare **Learn** > **pricing**, quindi selezionare il piano a cui si desidera passare.

![Informazioni sui prezzi >](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Ricerca per categorie conoscere quanto è stato usato?

Se si usa un piano gratuito o un piano di valutazione, toccare o fare clic sull'icona a forma di ingranaggio nella barra di spostamento superiore per visualizzare l'utilizzo corrente rispetto al piano. 

![Pulsante Impostazioni](./media/billing-questions/settings.png)

Se si usa un piano a pagamento, le esecuzioni vengono raggruppate in tutti gli utenti dell'organizzazione. Stiamo lavorando sulle funzionalità per esporre la quota e l'utilizzo disponibili in un'organizzazione.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Cosa accade se l'utilizzo supera i limiti?

Microsoft Flow limita le esecuzioni del flusso.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Dove è possibile trovare altre informazioni sui limiti di utilizzo?

Nella [pagina dei prezzi](https://flow.microsoft.com/pricing/), vedere la sezione **domande frequenti** .

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Cosa accade se si tenta di eseguire le esecuzioni troppo spesso?

Il piano determina la frequenza con cui vengono eseguiti i flussi. Ad esempio, i flussi possono essere eseguiti ogni 15 minuti se il piano è gratuito. Se un flusso viene attivato meno di 15 minuti dopo l'ultima esecuzione, viene accodato fino a quando non sono trascorsi 15 minuti.

## <a name="what-counts-as-a-run"></a>Quali sono i conteggi di un'esecuzione?

Ogni volta che viene attivato un flusso, da un trigger automatico o dall'avvio manuale, questo viene considerato un'esecuzione. Verifica se i nuovi dati non sono conteggiati come esecuzioni.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Esistono differenze tra account Microsoft e account aziendali o dell'Istituto di istruzione per la fatturazione?

Sì. Se si accede con un account Microsoft (ad esempio un account che termina con @outlook.com o @gmail.com), è possibile usare solo il piano gratuito. Per sfruttare i vantaggi delle funzionalità del piano a pagamento, accedere con un indirizzo di posta elettronica aziendale o dell'Istituto di istruzione.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Sto tentando di eseguire l'aggiornamento, ma viene indicato che il mio account non è idoneo.

Per eseguire l'aggiornamento, usare un account aziendale o dell'Istituto di istruzione oppure creare un [account di valutazione di Office 365](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Perché ho esaurito le esecuzioni quando il flusso è stato eseguito solo alcune volte?

Alcuni flussi possono essere eseguiti più frequentemente di quanto previsto. Ad esempio, è possibile creare un flusso che invia una notifica push ogni volta che il responsabile invia un messaggio di posta elettronica. Il flusso deve essere eseguito ogni volta che si riceve un messaggio di posta elettronica (da qualsiasi utente) perché il flusso deve verificare se il messaggio di posta elettronica è stato inviato dal responsabile. Questa azione viene conteggiata come un'esecuzione.

Per ovviare a questo problema, è possibile inserire tutti i filtri necessari nel trigger. Nell'esempio di notifica push espandere il menu **Opzioni avanzate** e quindi specificare l'indirizzo di posta elettronica del responsabile nel campo **da** .

## <a name="other-limits-and-caveats"></a>Altri limiti e avvertenze

* Ogni account può avere un numero di:
  * 250 flussi.
  * 15 connettori personalizzati.
  * 20 connessioni per API e 100 connessioni totali.
* È possibile installare un gateway solo nell'ambiente predefinito.
* Alcuni connettori esterni, ad esempio Twitter, implementano la limitazione della connessione per controllare la qualità del servizio. I flussi hanno esito negativo quando è attiva la limitazione delle richieste. Se i flussi hanno esito negativo, esaminare i dettagli dell'esecuzione non riuscita nella cronologia di esecuzione del flusso.
