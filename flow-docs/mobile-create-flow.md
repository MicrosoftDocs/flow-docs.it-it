---
title: Creare un flusso dal telefono | Microsoft Docs
description: Creare un flusso da un modello che, ad esempio, invii una notifica push quando si riceve posta da un indirizzo specificato
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 095b3a7f6565afff0a944bb08aee8f3a06ea114b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549049"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Creare un flusso dal telefono usando Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Creare un flusso dal telefono usando un modello, che è possibile trovare cercando in un elenco di servizi, sfogliando categorie o specificando parole chiave. Eseguire la procedura descritta in questo argomento per creare un flusso che invii una notifica push al telefono quando si riceve la posta dal responsabile.

Se non si ha familiarità con Microsoft Flow, [ottenere una panoramica](getting-started.md).

## <a name="prerequisites"></a>Prerequisiti
* Un [account per Microsoft Flow](sign-up-sign-in.md).
* App per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows) su un [dispositivo supportato](getting-started.md#use-the-mobile-app). Le immagini in questo argomento riflettono la versione dell'app per iPhone, ma l'interfaccia in un dispositivo Android o Windows Phone è simile.
* Per usare il modello illustrato in questo argomento, è necessario anche:
  
  * Credenziali di Office 365.
  * Notifiche push abilitate sul telefono.

## <a name="find-a-template"></a>Trovare un modello
1. Aprire l'app per dispositivi mobili e quindi toccare **Sfoglia** nella parte inferiore della schermata.
   
    ![Icona Sfoglia](./media/mobile-create-flow/browse-icon.png)
   
    È possibile trovare un modello in uno dei modi seguenti:
   
   * Specificare una parola chiave nella casella di ricerca nella parte superiore della schermata.
   * Toccare un'opzione nell'elenco dei servizi.
   * Scorrere verso il basso per visualizzare un'ampia gamma di categorie e quindi toccare un modello in qualsiasi categoria.
     
       ![Scheda Sfoglia](./media/mobile-create-flow/browse-tab.png)
     
     Per questa esercitazione, si aprirà il modello che invia una notifica push quando si riceve posta dal responsabile.
2. Nell'elenco dei servizi toccare **Visualizza tutto**.
   
    ![Mostra l'elenco dei servizi](./media/mobile-create-flow/list-services.png)
3. Toccare l'icona per la **notifica push**.
   
    ![Notifiche push](./media/mobile-create-flow/push-notifications.png)
4. Nella barra di ricerca digitare **email**, quindi toccare il modello per inviare una notifica push quando si riceve un messaggio dal responsabile.
   
    ![Scegli modello](./media/mobile-create-flow/choose-template.png)
5. Nella schermata che fornisce i dettagli sul modello selezionato toccare **Usa questo modello**.
   
    ![Conferma modello](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Completare il flusso
1. Se richiesto, toccare **Accedi**e specificare le credenziali per Office 365 Outlook, utenti di Office 365 o entrambi.
   
    ![Accedere a Office 365](./media/mobile-create-flow/office-signin.png)
   
    È possibile utilizzare le stesse connessioni quando si creano altri flussi.
2. Nell'angolo in alto a destra toccare **Avanti**.
   
    ![Toccare avanti](./media/mobile-create-flow/next.png)
   
    La schermata successiva mostra l'evento trigger e tutte le azioni risultanti.
   
    ![Evento trigger e azioni](./media/mobile-create-flow/flow-structure.png)
   
    Per questo modello, la nuova posta attiva il flusso, che recupera le informazioni (incluso l'indirizzo del Manager) e invia una notifica push quando si riceve posta da tale indirizzo. Per il corretto funzionamento di alcuni modelli è necessaria una personalizzazione, ma questo modello non lo è.
3. opzionale Nella parte superiore della schermata digitare un nome diverso per il flusso.
   
    ![Rinomina flusso](./media/mobile-create-flow/rename-flow.png)
4. Nell'angolo in alto a destra toccare **Crea**.
   
    ![Crea flusso](./media/mobile-create-flow/create-flow.png)
   
    Il flusso viene creato e controllerà la posta dal responsabile fino a quando non si sospende o si elimina il flusso.

## <a name="next-steps"></a>Passaggi successivi
* [Monitorare l'attività del flusso](mobile-monitor-activity.md).
* [Gestire i flussi](mobile-manage-flows.md).

