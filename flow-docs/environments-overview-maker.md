---
title: Passaggio da un ambiente all'altro durante la creazione di un flusso di Microsoft Flow | Microsoft Docs
description: Come usare ambienti diversi durante la creazione di un flusso di Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: bcbb566c20291da14881d771c538dd89689b6b1d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="choosing-an-environment"></a>Scelta di un ambiente
Con Microsoft Flow, è possibile lavorare in ambienti diversi e passare facilmente da uno all'altro. Questo articolo tratta i seguenti argomenti in materia di ambienti:

* Contesto di ciò che offrono gli ambienti
* Passaggio da un ambiente all'altro
* Come creare un flusso nell'ambiente appropriato

## <a name="environments-overview"></a>Panoramica degli ambienti
Gli ambienti offrono un limite di isolamento per i flussi, le connessioni, i gateway e altre risorse. Quando si crea un flusso, è possibile scegliere l'ambiente che dovrà ospitarlo e le risorse da usare. A seconda dello scenario d'uso è possibile scegliere l'ambiente da usare tra quelli disponibili.

Alcuni esempi:

* Nello scenario in cui si crea flusso che usa una connessione a Microsoft Common Data Service, il flusso e Microsoft Common Data Service si trovano entrambi nello stesso ambiente. Ciò garantisce l'isolamento di tutti i dati all'interno dell'ambiente (limite di isolamento).
* È in corso la creazione di un flusso per il reparto Risorse umane. Si vuole avere la certezza che tale flusso sia accessibile soltanto agli utenti di questo reparto. Ad esempio, si desidera impedire l'uso di questo flusso agli utenti del gruppo Vendite. In questo scenario, è possibile usare un ambiente separato (a cui hanno accesso solo gli utenti del reparto Risorse umane) per ospitare il flusso e tutte le risorse usate dal flusso stesso, come i gateway o le connessioni.
* In Europa ci sono alcuni utenti che usano un flusso per mostrare i dati di SharePoint. In questo scenario, è opportuno creare un ambiente in Europa che ospiti il flusso e la connessione di SharePoint. L'ambiente creato in Europa offre prestazioni migliori agli utenti in quest'area geografica, dal momento che tutte le risorse si trovano in Europa (principio di località dei dati).

Gli ambienti vengono creati dagli amministratori di Microsoft Flow, che controllano anche chi può accedere ai diversi ambienti.

Questo argomento illustra come spostarsi tra ambienti diversi. Per i dettagli su come creare e gestire gli ambienti, vedere la sezione [Gestire gli ambienti](environments-overview-admin.md).

## <a name="switching-environments"></a>Passaggio da un ambiente all'altro
Microsoft Flow facilita enormemente il passaggio da un ambiente all'altro. Quando si cambia ambiente, saranno visibili tutti gli elementi in tale ambiente specifico, ma non quelli appartenenti a qualsiasi altro ambiente.

Di seguito è riportato un esempio.

Creare un flusso denominato *Nuovo_dipendente* nell'ambiente *Risorse umane* . In [flow.microsoft.com](http://flow.microsoft.com), aprire l'ambiente *Vendite*. Il flusso *Nuovo_dipendente* non è elencato. Per visualizzare il flusso *Nuovo_dipendente*, aprire l'ambiente *Risorse umane*. Tenere presente che questo si applica a qualsiasi elemento creato nell'ambiente, vale a dire anche le connessioni, i gateway, PowerApps e altro ancora.

1. Aprire [flow.microsoft.com](http://flow.microsoft.com).
2. In alto a destra, sono visibili il proprio nome e l'ambiente corrente:  
   ![](./media/environments-overview-maker/default-environment.png)
   
    Nell'immagine, osservare le notifiche. Queste notifiche sono specifiche del flusso in questo ambiente predefinito.
3. Selezionare il proprio nome. Nell'elenco a discesa, sono elencati tutti gli ambienti disponibili. L'ambiente corrente è selezionato:  
   ![](./media/environments-overview-maker/all-environments.png)
4. Per passare a un altro ambiente, selezionarlo nell'elenco:  
   ![](./media/environments-overview-maker/select-europe.png)
5. Microsoft Flow passa automaticamente al nuovo ambiente:  
   ![](./media/environments-overview-maker/europe-environment.png)
   
    Nell'immagine, si noti che non sono presenti notifiche. Il nuovo ambiente Europa non contiene alcuna notifica.

## <a name="create-flows-in-the-right-environment"></a>Creare i flussi nell'ambiente appropriato
Prima di creare un flusso, assicurarsi sempre di aver selezionato l'ambiente desiderato, per evitare di dover eliminare il flusso creato e ricrearlo nell'ambiente corretto.

Quando si sceglie di creare i flussi in un determinato ambiente, considerare i fattori seguenti:

* I gateway vengono creati nell'ambiente predefinito. Dal momento che non è possibile creare i gateway in altri ambienti, per connettersi ai dati locali è necessario usare l'ambiente predefinito.
* I flussi possono usare solo le connessioni e altre risorse all'interno dello stesso ambiente. Le risorse presenti in altri ambienti non possono essere usate. Ad esempio, quando si crea un flusso che usa un connettore personalizzato, questo deve trovarsi nello stesso ambiente del flusso.
* Il database di Microsoft Common Data Service è sempre associato esattamente a un ambiente. Ciò significa che se si desidera usare i dati di Common Data Service è necessario selezionare lo stesso ambiente del database.
* Verranno visualizzati tutti gli ambienti in cui è possibile modificare le risorse. Tuttavia, ciò non si traduce nella facoltà di creare nuove risorse in tutti gli ambienti. Infatti, in alcuni ambienti potrebbe non essere consentito creare nuovi flussi. È necessario chiedere all'amministratore di venire aggiunti all'ambiente con il ruolo di **Autore**; in alternativa è possibile selezionare un altro ambiente in cui creare il flusso (i flussi potranno sempre essere creati nell'ambiente predefinito).

## <a name="what-you-did"></a>Risultati ottenuti
Questi passaggi permettono di spostarsi facilmente tra gli ambienti che si è autorizzati a usare. Ora è possibile iniziare a creare i propri flussi.

## <a name="next-steps"></a>Passaggi successivi
[Creare un flusso da un modello](get-started-logic-template.md)  
[Creare un flusso](get-started-logic-flow.md)  
[Panoramica sull'ambiente per gli amministratori](environments-overview-admin.md)

