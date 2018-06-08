---
title: Creare un flusso dal telefono | Microsoft Docs
description: Creare un flusso da un modello che, ad esempio, invia una notifica push quando si riceve posta da un indirizzo specificato
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
ms.openlocfilehash: 27a2001e3fa154f9354ef5ad888e194f30b3d6ab
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440299"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Creare un flusso dal telefono usando Microsoft Flow
Creare un flusso dal telefono usando un modello che è possibile trovare cercando in un elenco di servizi, esplorando categorie o specificando parole chiave. Seguire i passaggi descritti in questo argomento per creare un flusso che invii una notifica push al telefono dell'utente quando si riceve posta dal responsabile.

Se non si ha familiarità con Microsoft Flow, [vedere una panoramica](getting-started.md).

## <a name="prerequisites"></a>Prerequisiti
* Un [account per Microsoft Flow](sign-up-sign-in.md).
* L'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows) in un [dispositivo supportato](getting-started.md#use-the-mobile-app). Le figure in questo argomento riflettono la versione dell'app per iPhone, ma l'interfaccia di un dispositivo Android o Windows Phone è simile.
* Per usare il modello illustrato in questo argomento, saranno anche necessari:
  
  * Credenziali di Office 365
  * Notifiche push abilitate sul telefono

## <a name="find-a-template"></a>Trovare un modello
1. Aprire l'app per dispositivi mobili e quindi toccare **Sfoglia** nella parte inferiore della schermata.
   
    ![Icona Sfoglia](./media/mobile-create-flow/browse-icon.png)
   
    È possibile trovare un modello in uno dei modi seguenti:
   
   * Specificare una parola chiave nella casella di ricerca nella parte superiore della schermata.
   * Toccare un'opzione nell'elenco dei servizi.
   * Scorrere verso il basso per visualizzare un'ampia gamma di categorie e quindi toccare un modello in qualsiasi categoria.
     
       ![Scheda Sfoglia](./media/mobile-create-flow/browse-tab.png)
     
     Per questa esercitazione, è necessario aprire il modello che invii una notifica push quando si riceve posta dal responsabile.
2. Nell'elenco dei servizi, toccare **Vedi tutto**.
   
    ![Visualizzare l'elenco dei servizi](./media/mobile-create-flow/list-services.png)
3. Toccare l'icona per **Notifica push**.
   
    ![Notifiche push](./media/mobile-create-flow/push-notifications.png)
4. Nella barra di ricerca, digitare **Posta elettronica** e quindi toccare il modello per inviare una notifica push quando si riceve un messaggio dal responsabile.
   
    ![Scegliere un modello](./media/mobile-create-flow/choose-template.png)
5. Nella schermata che fornisce informazioni dettagliate sul modello selezionato, toccare **Usa questo modello**.
   
    ![Confermare il modello](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Terminare il flusso
1. Se richiesto, toccare **Accedi**, e fornire le credenziali per Office 365 Outlook, Utenti di Office 365 o entrambi.
   
    ![Accedere a Office 365](./media/mobile-create-flow/office-signin.png)
   
    È possibile usare le stesse connessioni quando si creano altri flussi.
2. In alto a destra, toccare **Avanti**.
   
    ![Toccare Avanti](./media/mobile-create-flow/next.png)
   
    La schermata successiva mostra l'evento trigger e tutte le azioni risultanti.
   
    ![Evento trigger e azioni](./media/mobile-create-flow/flow-structure.png)
   
    Per questo modello, i nuovi messaggi di posta attivano il flusso, che recupera le informazioni (incluso l'indirizzo del responsabile) e invia una notifica push quando si riceve posta da tale indirizzo. Determinati modelli richiedono alcune personalizzazioni per il corretto funzionamento, ma non questo modello.
3. (facoltativo) Nella parte superiore della schermata, digitare un nome diverso per il flusso.
   
    ![Rinominare il flusso](./media/mobile-create-flow/rename-flow.png)
4. In alto a destra, toccare **Crea**.
   
    ![Creare il flusso](./media/mobile-create-flow/create-flow.png)
   
    Il flusso è stato creato e controllerà la posta elettronica dal responsabile finché non si sospende o elimina il flusso.

## <a name="next-steps"></a>Passaggi successivi
* [Monitorare l'attività del flusso](mobile-monitor-activity.md).
* [Gestire i flussi](mobile-manage-flows.md).

