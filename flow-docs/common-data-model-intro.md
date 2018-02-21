---
title: Common Data Service | Microsoft Docs
description: Creare un flusso per importare i dati, esportare i dati o creare approvazioni con Common Data Service.
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: e4e92bfdcf1ea65de272233b2056523641010cf2
ms.sourcegitcommit: f3261717768177e03e825c0dd2e3ba736dc9b94d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2018
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Creare un flusso che usi Common Data Service
Migliorare l'efficienza operativa con una vista unificata dei dati di business con la creazione di un flusso che usa [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Distribuire questo database aziendale protetto che comprende entità aziendali standard ben formate (ad esempio vendite, acquisti, servizio clienti e produttività) nell'organizzazione. Archiviare dati aziendali in una o più [entità personalizzate](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), che offrono diversi vantaggi rispetto alle origini dati esterne, ad esempio Microsoft Excel e Salesforce.

Ad esempio, è possibile sfruttare Common Data Service all'interno di Microsoft Flow in tre modi principali:

* Creare un flusso per importare i dati, esportare i dati o agire sui dati (ad esempio inviare una notifica). Si noti che questo approccio non è un servizio di sincronizzazione completa, ma consente semplicemente di spostare importare o esportare i dati in base a singole entità.
  
    Per informazioni dettagliate, vedere le procedure più avanti in questo argomento.
* Invece di [creare un ciclo di approvazione attraverso la posta elettronica](wait-for-approvals.md), creare un flusso che archivi lo stato di approvazione in un'entità e creare un'app personalizzata in cui gli utenti possono approvare o rifiutare gli elementi.
  
    Per la procedura dettagliata, vedere [Creare un ciclo di approvazione con Common Data Service](common-data-model-approve.md).

**Prerequisiti**

* Iscriversi a [Microsoft Flow](https://flow.microsoft.com) e [PowerApps](https://web.powerapps.com).
  
    Se si riscontrano problemi, verificare se [Microsoft Flow](sign-up-sign-in.md) e [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) supportano il tipo di account di cui si è in possesso e che l'organizzazione non abbia bloccato l'iscrizione.
* Se Common Data Service non è mai stato usato in precedenza, aprire la scheda **Entità** di [powerapps.com](https://web.powerapps.com/#/entities), quindi scegliere o toccare **Crea il database personale**.

## <a name="sign-in-to-your-environment"></a>Accedere al proprio ambiente
1. Aprire il [portale di Microsoft Flow](https://flow.microsoft.com) e quindi scegliere o toccare **Accedi** in alto a destra.
   
    **Nota**: per visualizzare il pulsante **Accedi**, potrebbe essere necessario aprire il menu in alto a sinistra.
   
    ![Accedi](./media/common-data-model-intro/signin-flow.png)
2. Su powerapps.com, nel menu in alto a destra selezionare l'ambiente in cui è stato creato il database.
   
    **Nota**: se non si seleziona lo stesso ambiente, non verranno visualizzate le entità.
   
    ![Selezionare l'ambiente](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Aprire un modello
1. Nella casella **Cerca modelli** nella parte superiore dello schermo, digitare o incollare **common**, quindi premere INVIO.
   
    ![Ricerca di modelli](./media/common-data-model-intro/template-search.png)
2. Nell'elenco dei modelli, scegliere o toccare il modello che importa i dati dall'origine desiderata nell'entità (o nell'*oggetto*) desiderata.
   
    Ad esempio, scegliere o toccare il modello che copia le informazioni sul contatto da Dynamics 365 in Common Data Service.
   
    ![Scegliere un modello](./media/common-data-model-intro/choose-template.png)
3. Scegliere o toccare **Usa questo modello**.
   
    ![Usare il modello](./media/common-data-model-intro/use-template.png)
4. Se non è già stata creata una connessione da Microsoft Flow a Dynamics 365, scegliere o toccare **Accedi**, quindi fornire le credenziali, se richieste.
   
    ![Accedere a Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Scegliere o toccare **Continua**.
   
    ![Verificare gli account](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Creare il flusso
1. Nella prima scheda, specificare l'evento che attiverà il flusso.
   
    Ad esempio, si sta creando un flusso che copierà i nuovi contatti da un'istanza di Dynamics 365 in Common Data Service. In **Quando un record viene creato**, specificare l'istanza scegliendo o toccando la freccia GIÙ e quindi scegliendo o toccando un'opzione nell'elenco visualizzato.
   
    ![Specificare l'istanza di Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. (facoltativo) Nella parte superiore della schermata, specificare un nome diverso per il flusso che si sta creando.
   
    **Nota**: se la finestra del browser non è ingrandita, l'interfaccia utente potrebbe essere leggermente diversa.
   
    ![Assegnare un nome al flusso](./media/common-data-model-intro/name-flow.png)
3. Scegliere o toccare **Crea flusso**.
   
    **Nota**: se la finestra del browser non è ingrandita, potrebbe essere visualizzato solo il segno di spunta.
   
    ![Creare il flusso](./media/common-data-model-intro/create-flow.png)

A questo punto, ogni volta che tale oggetto viene creato nel sistema di origine, verrà importato in Common Data Service. Se non è possibile trovare un modello che funzioni come richiesto, è possibile [creare un flusso da zero](get-started-logic-flow.md) che operi all'interno di Common Data Service.

È possibile agire sulle modifiche nel database. Ad esempio, è possibile inviare posta elettronica di notifica ogni volta che i dati vengono modificati.

