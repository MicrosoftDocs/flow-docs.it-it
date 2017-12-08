---
title: Domande su fatturazione e misurazione | Microsoft Docs
description: Risposte alle domande frequenti in materia di fatturazione e misurazione in Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/21/2016
ms.author: deonhe
ms.openlocfilehash: b627c008e1483360f35b6de579e2c0da32e60c93
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="billing-and-metering-questions"></a>Domande su fatturazione e misurazione
Questo articolo risponde alle domande frequenti in materia di fatturazione e misurazione Flow Microsoft.

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Dove posso reperire informazioni su quali sono i piani tariffari disponibili?
Vedere la [pagina dei prezzi](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Dove posso reperire informazioni sul mio piano?
Vedere la [pagina dei prezzi](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Come faccio a passare da un piano all'altro?
Nel menu di spostamento superiore, scegliere o toccare **Apprendi**, quindi scegliere o toccare **Prezzi**.

![Apprendi > Prezzi](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Come posso reperire i dati sul consumo?
Scegliere o toccare **Attività** per visualizzare i log delle esecuzioni, le notifiche e gli errori.

![Collegamento Attività](./media/billing-questions/activity-link.png)

Se si è scelto un piano gratuito o di valutazione, scegliere o toccare l'icona a forma di ingranaggio nella barra di spostamento superiore per visualizzare l'utilizzo corrente rispetto al piano.   

![Pulsante Impostazioni](./media/billing-questions/settings.png)

Se non si è scelto un piano gratuito o di valutazione, le esecuzioni vengono rese disponibili a tutti gli utenti dell'organizzazione. Sono in via di sviluppo le funzionalità che permetteranno di esporre la quota disponibile e l'utilizzo nell'intera organizzazione.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Cosa succede se i dati sul consumo superano i limiti?
Microsoft Flow può iniziare a limitare le esecuzioni.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Dove posso trovare altre informazioni sui limiti di utilizzo?
Vedere la sezione [Domande e risposte](https://flow.microsoft.com/pricing/) nella **pagina dei prezzi**.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Cosa succede se tento di avviare esecuzioni con una frequenza eccessiva?
Il piano determina la frequenza con cui eseguono i flussi. Ad esempio, i flussi possono essere eseguiti ogni 15 minuti se si è scelto il piano gratuito. Se un flusso viene attivato meno di 15 minuti dopo che è stata eseguita l'esecuzione più recente, verrà messo in coda fino a quando non saranno trascorsi 15 minuti. I controlli per verificare la presenza di nuovi dati non contano come esecuzioni.

## <a name="what-counts-as-a-run"></a>Cosa viene considerato come un'esecuzione?
Ogni volta che si attiva un flusso, tramite un trigger automatico o manualmente, questa operazione viene conteggiata come un'esecuzione.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>A fini di fatturazione, ci sono differenze tra gli account di Microsoft e gli account aziendali o scolastici?
Sì. Se si accede con un account Microsoft (ad esempio un account che termina in @outlook.com o @gmail.com), è possibile usare solo il piano gratuito. Per poter sfruttare le funzionalità del piano a pagamento, accedere con un account di posta elettronica aziendale o di un istituto scolastico.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Sto provando a eseguire l'aggiornamento, ma un messaggio informa che il mio account non è idoneo.
Per eseguire l'aggiornamento, usare un account aziendale o dell'istituto di istruzione o creare una versione di valutazione di Office 365 seguendo le istruzioni riportate in questo [articolo di Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Per quale motivo ho esaurito le esecuzioni a mia disposizione se il flusso è stato eseguito solo poche volte?
Alcuni flussi possono essere eseguiti più spesso del previsto. Ad esempio, è possibile creare un flusso che invia una notifica push ogni volta che il gestore invia un messaggio di posta elettronica all'utente. Tale flusso deve essere eseguito ogni volta che si riceve un messaggio di posta elettronica (da chiunque) perché deve controllare se il messaggio è stato inviato dal proprio responsabile. Quest'azione viene considerata come un'esecuzione.

È possibile risolvere questo problema inserendo nel trigger tutti i parametri di filtro necessari. Nell'esempio precedente, espandere il menu **Opzioni avanzate** e specificare l'indirizzo di posta elettronica del responsabile nel campo **Da**.

## <a name="other-limits-and-caveats"></a>Altri limiti e rischi
* Ogni account può avere fino a:
  * 50 flussi
  * 15 connettori personalizzati
  * 20 connessioni per API e 100 connessioni totali.
* È possibile installare un gateway solo nell'ambiente predefinito.   
* Alcuni connettori esterni, ad esempio Twitter, implementano la limitazione di connessione per controllare la qualità del servizio. Quando la limitazione è attiva, i flussi hanno esito negativo. È possibile esaminare i dettagli di questa limitazione visualizzando l'esecuzione non riuscita nella cronologia delle esecuzioni del flusso.
