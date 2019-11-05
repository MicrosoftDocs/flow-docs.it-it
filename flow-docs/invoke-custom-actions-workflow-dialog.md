---
title: Richiamare azioni personalizzate da un flusso di lavoro | MicrosoftDocs
description: Informazioni su come richiamare un'azione personalizzata da un flusso di lavoro
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9ed3c2114bfb167eb8d4d6a5670ccec8050ee9d0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547426"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Richiamare azioni personalizzate da un flusso di lavoro
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I flussi di lavoro hanno numerose funzionalità che supportano scenari aziendali. La chiamata di operazioni di base sui dati per un record, ad esempio creazione, aggiornamento ed eliminazione, dall'interno di un flusso di lavoro risolve alcuni scenari aziendali. Tuttavia, se si abbinano le funzionalità dei flussi di lavoro con la potenza delle azioni personalizzate richiamate direttamente dall'interno di un flusso di lavoro, si aggiunge un'intera nuova gamma di scenari aziendali all'applicazione senza dover scrivere codice.  
  
 Verrà ora esaminato lo scenario in cui un'azione personalizzata viene richiamata da un flusso di lavoro. Verrà richiamata un'azione personalizzata per richiedere l'approvazione del responsabile quando uno sconto per una determinata opportunità supera il 20%.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Esempio: creare un'azione personalizzata usando l'entità opportunity
  
1. In [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) selezionare **processi**.  
  
2.  Sulla barra di navigazione scegliere **nuovo**. Assegnare un nome al processo e scegliere la categoria **azione** .  
  
 Per richiedere un'approvazione per lo sconto, viene usata un'azione personalizzata denominata **processo di approvazione**. Sono stati aggiunti un parametro di input, **SpecialNotes**, e un passaggio Invia messaggio di **posta elettronica** per creare un nuovo messaggio e inviare una richiesta per l'approvazione del responsabile, come illustrato di seguito.  
  
 ![Aggiungi un passaggio &#45; inviare un messaggio di posta elettronica](media/enable-custom-action-approval-proces-sadd-email.png "Aggiungere un passaggio-inviare un messaggio di posta elettronica")  
  
 Per configurare il messaggio di posta elettronica, scegliere **Imposta proprietà**. Quando il modulo viene aperto, usare **Assistente moduli** per aggiungere note speciali e altre informazioni al messaggio di posta elettronica, come evidenziato nella schermata. Per aggiungere le note speciali, posizionare il cursore nel punto in cui si desidera che vengano visualizzate nel messaggio e quindi in **Assistente form**, in **Cerca**, scegliere gli **argomenti** nel primo elenco a discesa e scegliere **SpecialNotes** nel secondo elenco a discesa, quindi scegliere **OK**.  
  
 ![Configurare la posta elettronica](media/enable-custom-action-approval-process-setup-email.png "Configurare la posta elettronica")  
  
 Prima di poter richiamare l'azione da un flusso di lavoro, è necessario attivarla. Dopo aver attivato l'azione, è possibile visualizzarne le proprietà scegliendo **Visualizza proprietà**.  
  
 ![Attivare il processo &#45; di approvazione dell'azione personalizzata](media/enable-custom-action-approval-process-activate-action.png "Attivare il processo di approvazione dell'azione personalizzata")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Richiamare un'azione personalizzata da un flusso di lavoro  
  
1. In [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) selezionare **processi**.   
  
2.  Sulla barra di navigazione scegliere **nuovo**. Assegnare un nome al processo e scegliere la categoria del **flusso di lavoro** .  
  
 È stato creato un flusso di lavoro che richiama l'azione personalizzata del **processo di approvazione** ogni volta che è necessaria l'approvazione del responsabile per uno sconto oltre il 20%.  
  
 ![Impostare le proprietà dell'azione dal flusso di lavoro](media/enable-custom-action-from-workflow.png "Impostare le proprietà dell'azione dal flusso di lavoro")  
  
 È possibile impostare le proprietà di input dell'azione scegliendo **Imposta proprietà**. È stato aggiunto un nome dell'account correlato all'opportunità nelle note speciali. In **form Assistant**, in **Cerca**, scegliere **account** nel primo elenco a discesa, scegliere **nome account** nel secondo elenco a discesa, quindi scegliere **OK**. La proprietà di **destinazione** è obbligatoria e viene popolata dal sistema. Il **{opportunity (opportunity)}** nella proprietà di **destinazione** è la stessa opportunità di esecuzione del flusso di lavoro chiamante. In alternativa, è possibile scegliere un'opportunità specifica per la proprietà di destinazione usando Lookup.  
  
 ![Imposta i parametri di input per l'azione ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Imposta i parametri di input per l'azione ApprovalProcess")  
  



