---
title: Richiamare azioni personalizzate da un flusso di lavoro | MicrosoftDocs
description: Informazioni su come richiamare un'azione personalizzata da un flusso di lavoro
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
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
ms.openlocfilehash: 8b2904632f4b3bf097275906d917e686cace67ba
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688516"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Richiamare azioni personalizzate da un flusso di lavoro

I flussi di lavoro includono numerose funzionalità che supportano scenari aziendali. La chiamata di azioni SDK di base per un record, ad esempio Crea, Aggiorna ed Elimina, dall'interno di un flusso di lavoro risolve alcuni scenari aziendali. Tuttavia, se si usano in combinazione le funzionalità dei flussi di lavoro e le azioni personalizzate richiamate direttamente dall'interno di un flusso di lavoro si aggiungono numerosi nuovi scenari aziendali all'applicazione senza la necessità di scrivere codice.  
  
 Si osservi lo scenario in cui un'azione personalizzata viene richiamata da un flusso di lavoro. Verrà richiamata un'azione personalizzata per richiedere l'approvazione del manager quando lo sconto per una determinata opportunità supera il 20%.  
  
<a name="action"></a>   
## <a name="dynamics-365-customer-engagement-example-create-a-custom-action-using-the-opportunity-entity"></a>Esempio di Dynamics 365 Customer Engagement: Creare un'azione personalizzata usando l'entità dell'opportunità
  
1. In [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) selezionare **Processi**.  
  
2.  Nella barra di spostamento scegliere **Nuovo**. Assegnare un nome al processo e scegliere la categoria **Azione**.  
  
 Per richiedere un'approvazione per lo sconto, viene usata un'azione personalizzata denominata **Approval Process** (Processo approvazione). È stato aggiunto un parametro di input, **SpecialNotes** (Note speciali) e un passaggio **Send email** (Invio messaggio di posta elettronica) per creare un nuovo messaggio e inviare una richiesta per l'approvazione del manager, come illustrato di seguito.  
  
 ![Aggiungere un passaggio &#45; send email (invio messaggio di posta elettronica)](media/enable-custom-action-approval-proces-sadd-email.png "Aggiungere un passaggio - send email (invio messaggio di posta elettronica)")  
  
 Per configurare il messaggio di posta elettronica, scegliere **Imposta proprietà**. All'apertura del modulo, usare **Informazioni e selezione rapida** per aggiungere note speciali e altre informazioni al messaggio di posta elettronica, come illustrato nello screenshot. Per aggiungere note speciali, posizionare il cursore nella posizione in cui si vuole visualizzarle nel messaggio e quindi in **Informazioni e selezione rapida** in **Cerca** scegliere **Argomenti** nel primo elenco a discesa e scegliere **SpecialNotes** (Note speciali) nel secondo elenco a discesa e quindi scegliere **OK**.  
  
 ![Configurare la posta elettronica](media/enable-custom-action-approval-process-setup-email.png "Configurare la posta elettronica")  
  
 Per poter richiamare l'azione da un flusso di lavoro, è necessario prima attivarla. Dopo aver attivato l'azione, è possibile visualizzarne le proprietà scegliendo **Visualizza proprietà**.  
  
 ![Attivare l'azione personalizzata &#45; approval process (processo approvazione)](media/enable-custom-action-approval-process-activate-action.png "Attivare l'azione personalizzata - approval process (processo approvazione)")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Richiamare un'azione personalizzata da un flusso di lavoro  
  
1. In [Esplora soluzioni](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) selezionare **Processi**.   
  
2.  Nella barra di spostamento scegliere **Nuovo**. Assegnare un nome al processo e scegliere la categoria **Flusso di lavoro**.  
  
 È stato creato un flusso di lavoro che richiama l'azione personalizzata **Approval Process** (Processo approvazione) ogni volta che è richiesta l'approvazione del manager per uno sconto superiore al 20% per un'opportunità.  
  
 ![Impostare le proprietà dell'azione dal flusso di lavoro](media/enable-custom-action-from-workflow.png "Impostare le proprietà dell'azione dal flusso di lavoro")  
  
 È possibile impostare le proprietà di input dell'azione scegliendo **Imposta proprietà**. È stato aggiunto un nome dell'account correlato all'opportunità nelle note speciali. In **Informazioni e selezione rapida** in **Cerca** scegliere **Account** nel primo elenco a discesa, scegliere **Account Name** (Nome account) nel secondo elenco a discesa e quindi scegliere **OK**. La proprietà **Destinazione** è obbligatoria e viene popolata dal sistema. **{Opportunity(Opportunity)}** nella proprietà **Destinazione** corrisponde all'opportunità in cui viene eseguito il flusso di lavoro che effettua la chiamata. In alternativa, è possibile scegliere un'opportunità specifica per la proprietà di destinazione usando la ricerca.  
  
 ![Impostare i parametri di input per l'azione ApprovalProcess (Processo approvazione)](media/enable-customaction-workflow-set-properties.png "Impostare i parametri di input per l'azione ApprovalProcess (Processo approvazione)")  
  



