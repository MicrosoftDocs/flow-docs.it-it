---
title: Domande frequenti sul connettore API | Microsoft Docs
description: Trovare le risposte alle domande su requisiti, trigger e altre aree.
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
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 1715700fa6a94bb35733865556a2c9be0ba3ce9f
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="api-connector-faq-microsoft-flow"></a>Domande frequenti sul connettore delle API (Microsoft Flow)
## <a name="requirements"></a>Requisiti
**D:** È possibile creare un connettore senza le API REST? </br>
**R:** No. Per creare un connettore è necessario supportare le API REST HTTP stabili per il servizio. 

**Q:** Quali strumenti è possibile usare per creare un connettore? </br>
**R:** Azure offre funzionalità e servizi che è possibile usare per l'esposizione di qualsiasi servizio come un'API, ad esempio il Servizio App di Azure per l'hosting, la Gestione API e altro ancora.

**D:** Quali tipi di autenticazione sono supportati? </br>
**R:** è possibile usare questi standard di autenticazione supportati:

* [OAuth 2.0](https://oauth.net/2/), tra cui [Azure Active Directory](https://azure.microsoft.com/develop/identity/) o servizi specifici, ad esempio GitHub, Dropbox e SalesForce
* OAuth 2.0 generica
* [Autenticazione di base](https://swagger.io/docs/specification/authentication/basic-authentication/)
* [Chiave API](https://swagger.io/docs/specification/authentication/api-keys/)

## <a name="triggers"></a>Trigger
**D:** È possibile creare trigger senza webhook? </br>
**R**: No. I connettori personalizzati per App per la logica di Azure e Microsoft Flow supportano solo i trigger basati su webhook. Se si vogliono richiedere altri criteri per l'implementazione, contattare [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) fornendo altri dettagli sull'API.

## <a name="certification"></a>Certificazione
**D**: Se non si è partner Microsoft né Independent Software Vendor (ISV) è comunque possibile creare dei connettori? </br>
**R**: Sì, è possibile registrare questi connettori per l'uso interno nell'organizzazione, ma se si vuole certificare e rilasciare pubblicamente un connettore, si deve essere il proprietario del servizio sottostante o presentare diritti espliciti per l'uso dell'API.

## <a name="other"></a>Altro
**D:** Le API usano un host dinamico. Come implementarle con OpenAPI? </br>
**R:** I connettori personalizzati non supportano gli host dinamici, ma usano invece un host statico per scopi di sviluppo e test. Se si vuole certificare il connettore, è possibile chiedere al proprio contatto Microsoft a proposito dell'implementazione dinamica.

**Q:** I file Postman Collection V2 sono supportati? </br>
**R:** No, solo Postman Collection V1 è attualmente supportato.

**D:** I file OpenAPI 3.0 sono supportati? </br>
**R:** No, solo OpenAPI 2.0 è attualmente supportato.

