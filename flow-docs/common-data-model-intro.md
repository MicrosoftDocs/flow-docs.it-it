---
title: Common Data Service | Microsoft Docs
description: Creare un flusso per importare i dati, esportare i dati o creare approvazioni con la Common Data Service.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 60e076dadab17beb15ffaec289ec0a2937924668
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546956"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Creare un flusso che usi il Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Migliorare l'efficienza operativa con una vista unificata dei dati aziendali creando un flusso che usa la [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Distribuisci il database aziendale sicuro che comprende entità aziendali standard ben formate, ad esempio vendite, acquisti, assistenza clienti e produttività, nella tua organizzazione. Archiviare i dati aziendali in una o più [entità personalizzate](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), che offrono diversi vantaggi rispetto alle origini dati esterne, ad esempio Microsoft Excel e Salesforce.

Utilizzare, ad esempio, la Common Data Service all'interno di Microsoft Flow in questi modi principali:

* Creare un flusso per importare i dati, esportare i dati o intervenire sui dati, ad esempio inviando una notifica. Si noti che questo approccio non è un servizio di sincronizzazione completo. consente semplicemente di spostare i dati all'interno o all'esterno per ogni singola entità.
  
    Per i passaggi dettagliati, vedere le procedure più avanti in questo argomento.
* Invece di [creare un ciclo di approvazione tramite posta elettronica](wait-for-approvals.md), creare un flusso che archivia lo stato di approvazione in un'entità e creare un'app personalizzata in cui gli utenti possono approvare o rifiutare gli elementi.
  
    Per i passaggi dettagliati, vedere [creare un ciclo di approvazione con il Common Data Service](common-data-model-approve.md).

**Prerequisiti**

* Iscriversi a [Microsoft Flow](https://flow.microsoft.com) e [PowerApps](https://web.powerapps.com).
  
    In caso di problemi, verificare che [Microsoft Flow](sign-up-sign-in.md) e [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) supportino il tipo di account di cui si dispone e che l'organizzazione non abbia bloccato l'iscrizione.
* Se il Common Data Service non è mai stato usato in precedenza, aprire la scheda **entità** di [powerapps.com](https://web.powerapps.com/#/entities)e quindi fare clic o toccare **Crea database**.

## <a name="sign-in-to-your-environment"></a>Accedere al proprio ambiente
1. Aprire il [portale di Microsoft Flow](https://flow.microsoft.com)e quindi toccare o fare clic su **Accedi** nell'angolo superiore destro.
   
    **Nota**: potrebbe essere necessario aprire il menu in alto a sinistra per visualizzare il pulsante **Accedi** .
   
    ![Accedi](./media/common-data-model-intro/signin-flow.png)
2. Nel menu in alto a destra selezionare l'ambiente in cui è stato creato il database in powerapps.com.
   
    **Nota**: se non si seleziona lo stesso ambiente, le entità non vengono visualizzate.
   
    ![Seleziona ambiente](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Aprire un modello
1. Nella casella **Cerca modelli** nella parte superiore della schermata digitare o incollare **Common**, quindi premere INVIO.
   
    ![Ricerca di modelli](./media/common-data-model-intro/template-search.png)
2. Nell'elenco dei modelli toccare o fare clic sul modello che importa i dati dall'origine desiderata nell'entità o nell' *oggetto*desiderato.
   
    Ad esempio, fare clic o toccare il modello che copia le informazioni di contatto da Dynamics 365 nella Common Data Service.
   
    ![Scegliere un modello](./media/common-data-model-intro/choose-template.png)
3. Toccare o fare clic su **Usa questo modello**.
   
    ![Usa modello](./media/common-data-model-intro/use-template.png)
4. Se non è già stata creata una connessione da Microsoft Flow a Dynamics 365, toccare o fare clic su **Accedi**e quindi fornire le credenziali, se richiesto.
   
    ![Accedere a Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Toccare o fare clic su **continua**.
   
    ![Conferma account](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Creare il flusso
1. Nella prima scheda specificare l'evento che attiverà il flusso.
   
    Ad esempio, si sta creando un flusso che copierà i nuovi contatti da un'istanza di Dynamics 365 al Common Data Service. In **quando viene creato un record**, specificare l'istanza toccando o facendo clic sulla freccia rivolta verso il basso e quindi scegliendo o toccando un'opzione nell'elenco visualizzato.
   
    ![Specificare l'istanza di Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. opzionale Nella parte superiore della schermata specificare un nome diverso per il flusso che si sta creando.
   
    **Nota**: se la finestra del browser non è ingrandita, l'interfaccia utente potrebbe essere leggermente diversa.
   
    ![Flusso nome](./media/common-data-model-intro/name-flow.png)
3. Toccare o fare clic su **Crea flusso**.
   
    **Nota**: se la finestra del browser non è ingrandita, potrebbe essere visualizzato solo il segno di spunta.
   
    ![Crea flusso](./media/common-data-model-intro/create-flow.png)

A questo punto, ogni volta che l'oggetto viene creato nel sistema di origine, verrà importato nel Common Data Service. Se non si riesce a trovare un modello che esegue le operazioni necessarie, è possibile [creare un flusso da zero](get-started-logic-flow.md) che operi sopra la Common Data Service.

È possibile eseguire azioni sulle modifiche nel database. Ad esempio, è possibile inviare notifiche di posta elettronica ogni volta che i dati cambiano.

