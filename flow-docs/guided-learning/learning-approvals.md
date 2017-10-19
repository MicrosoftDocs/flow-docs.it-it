---
title: Richieste di approvazione con Microsoft Flow | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per gestire un flusso di lavoro di approvazione.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: o-pgEBW3fOI
courseduration: 14m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 049b713ed653ab5555e5f48f63e46cce7f3207ee
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="approval-requests"></a>Richieste di approvazione
Oltre alla possibilità di **ricevere notifiche**, **copiare i file** e **raccogliere i dati**, Microsoft Flow offre anche la possibilità di **ottimizzare i processi di approvazione**.

## <a name="vacation-scenario"></a>Scenario relativo alle ferie
Immaginare di essere il **responsabile** di un team e di chiedere ai propri dipendenti di creare **richieste di ferie** in un **elenco SharePoint**. A questo punto si desidera realizzare un **processo di approvazione** attorno a questi elementi in elenco in modo che le nuove richieste di ferie vengano **elaborate rapidamente** e il richiedente riceva **una notifica automatica**.  

## <a name="sharepoint-and-microsoft-flow"></a>SharePoint e Microsoft Flow
Microsoft Flow è **integrato** in **SharePoint**.  Dall'**elenco di SharePoint** fare clic sul menu a discesa **Flusso** e selezionare **Create a flow** (Creare un flusso).

![Creare il flusso](./media/learning-approvals/new-flow.png)   

Nel **menu a destra** cercare un **modello** come questo.

![Modello di approvazione](./media/learning-approvals/approval-template.png)

## <a name="using-the-template"></a>Uso del modello
Il trigger **SharePoint** nel modello viene **pre-popolato** con le informazioni dell'elenco.  È sufficiente aggiungere un **indirizzo e-mail** per il **responsabile approvazione**.  Si noti che  **l'elemento di SharePoint originale non viene modificato**.  Per farlo è necessario aggiungere l'azione **SharePoint - Aggiorna elemento**.

![Aggiorna elemento](./media/learning-approvals/update-item.png)

Per impostazione predefinita, il ramo **Se no** di *Inviare emailScope*  non esegue alcuna operazione.  Si potrebbe voler aggiungere un'azione per inviare un messaggio all'autore della richiesta per informarlo che la sua richiesta è stata respinta. 

![Se no](./media/learning-approvals/if-no.png)

## <a name="next-lesson"></a>Lezione successiva
Ora è tempo di ripassare quanto appreso in questa sezione.

