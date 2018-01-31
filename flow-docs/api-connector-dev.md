---
title: Sviluppare un connettore API | Microsoft Docs
description: Descrivere l'API, specificare il tipo di autenticazione, creare trigger e azioni ed eseguire test.
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 8731e8a90a62bac4a05068386d23d2449952860b
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2018
---
# <a name="develop-an-api-connector-microsoft-flow"></a>Sviluppare un connettore delle API (Microsoft Flow)
La creazione di un connettore prevede più passaggi. Per iniziare, in [Microsoft Flow](https://flow.microsoft.com/) scegliere o toccare il pulsante **Impostazioni** (l'icona a forma di ingranaggio) in alto a destra della pagina. Quindi scegliere o toccare **Connettori personalizzati**.

![Ricerca di connettori delle API](./media/api-connectors-dev/finding-custom-apis.png)

## <a name="describe-your-api"></a>Descrivere l'API
I connettori delle API vengono descritti usando lo [standard OpenAPI](https://swagger.io/) per definire l'interfaccia di un'API HTTP. È possibile iniziare a creare con un file OpenAPI esistente oppure è possibile importare un file [Postman Collection](https://www.getpostman.com/docs/collections), che genera automaticamente il file OpenAPI. 

![Definire il diagramma delle API](./media/api-connectors-dev/build-your-api-updated.png)

Se si inizia da una di queste descrizioni delle API, i campi di metadati nella procedura guidata vengono popolati automaticamente. È possibile modificarli in qualsiasi momento.  

## <a name="build-security"></a>Creare la sicurezza
Selezionare il tipo di autenticazione supportato dal servizio e fornire dettagli aggiuntivi per abilitare il flusso dell'identità in modo appropriato tra il servizio e i client. 

![Diagramma di sicurezza](./media/api-connectors-dev/security.png)

[Altre informazioni](register-custom-api.md) sulla sicurezza del connettore.

## <a name="build-triggers-and-actions"></a>Creare trigger e azioni
1. Per creare i trigger e le azioni per il connettore, passare alla scheda **Definizione**. 
   
    ![Diagramma di definizione](./media/api-connectors-dev/definition.png)
2. Usando la procedura guidata, è possibile aggiungere nuove operazioni o modificare lo schema e la risposta per quelle esistenti. Le proprietà **generali** per ciascuna operazione consentono di controllare l'esperienza utente finale per il connettore. Per altre informazioni sui diversi tipi di operazioni, vedere i collegamenti seguenti:
   
   * [Trigger](customapi-webhooks.md) (non visibile in PowerApps)
   * [Azioni](register-custom-api.md)
     
     Per implementare funzionalità avanzate per Microsoft Flow, vedere le [estensioni OpenAPI per i connettori delle API](https://flow.microsoft.com/documentation/customapi-how-to-swagger/). 
3. Infine, scegliere o toccare **Crea connettore** per registrare il connettore delle API.

Per altre funzioni non disponibili nella procedura guidata, contattare [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com).

## <a name="test-the-connector"></a>Testare il connettore
Prima dell'invio, testare il connettore delle API in uno o più modi: 

* Usando la [procedura guidata di test](https://flow.microsoft.com/blog/new-updates-custom-api/) del connettore delle API, è possibile chiamare ogni operazione per verificare la relativa funzionalità e lo schema di risposta.
* Nella finestra di progettazione per Microsoft Flow, è possibile compilare visivamente flussi con il connettore delle API. Questo metodo di test offre visibilità sulla funzionalità dell'interfaccia utente e sulle caratteristiche del connettore.
* In PowerApps Studio, è possibile chiamare ogni operazione usando la barra della formula e associare la risposta ai controlli sullo schermo.

Questo argomento fornisce solo una panoramica. Per altre informazioni, vedere [Registrare e usare un connettore personalizzato](register-custom-api.md).

