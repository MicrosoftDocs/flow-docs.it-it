---
title: Inviare un connettore API per la certificazione | Microsoft Docs
description: Con la certificazione, un connettore diventa disponibile a tutti gli utenti di Microsoft Flow, PowerApps e App per la logica.
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
ms.openlocfilehash: 33283e1f682190f6aea02cb61a31cb43b42d5289
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2018
---
# <a name="submit-your-connectors-for-microsoft-certification"></a>Inviare i connettori per la certificazione Microsoft
Per rendere pubblicamente disponibili i connettori personalizzati a tutti gli utenti in Microsoft Flow, App per la logica di Azure e Microsoft PowerApps, inviare il connettore Microsoft per la revisione, la convalida e l'approvazione per la pubblicazione. 

## <a name="certification-criteria"></a>Criteri di certificazione
| Funzionalità | Dettagli | Obbligatorio o Consigliato |
| --- | --- | --- |
| App Software as a Service (SaaS) |Soddisfa uno scenario utente che si adatta perfettamente a App per la logica, Microsoft Flow e PowerApps |Obbligatorio |
| Tipo di autenticazione |L'API deve supportare OAuth2, la chiave API o l'autenticazione di base. |Obbligatorio |
| Supporto |È necessario fornire un contatto del supporto tecnico al quale i clienti potranno richiedere assistenza. |Obbligatorio |
| Disponibilità e tempo di attività |L'app ha un tempo di attività di almeno il 99,9%. |Consigliato |
|  | | |

Inoltre, se non si è un partner Microsoft o un Independent Software Vendor (ISV), ma se si vuole certificare e rilasciare pubblicamente un connettore, si deve essere il proprietario del servizio sottostante o presentare diritti espliciti per l'uso dell'API.

Per essere certificato, il connettore viene esaminato in due fasi: 

1. Convalida di funzionalità
   
    Il connettore personalizzato viene valutato per:
   
   * Errori di swagger o JSON non valido nella sezione Definizione della procedura guidata del connettore personalizzato
   * Errori di convalida dello schema e di runtime nella sezione Test della procedura guidata
     
     Di conseguenza, ogni operazione viene testata accuratamente in Flow, App per la logica di Azure e PowerApps per verificare la presenta di eventuali errori sul lato client.
2. Convalida del contenuto
   
    Un connettore ben scritto usa nomi descrittivi e descrizioni per ogni entità. È opportuno valutare lo swagger per garantire che ogni operazione, parametro di input e attributo di risposta contenga:
   
   * [Riepilogo](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#summary)
   * [Descrizione](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#description)
   * [Informazioni di visibilità](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#visibility)

## <a name="nominate-and-submit-your-connector-to-microsoft-for-certification"></a>Nominare e inviare il connettore a Microsoft per la certificazione
Per richiedere la certificazione, seguire questi passaggi:

1. **Candidare**
   
   1. [Inviare la candidatura](https://go.microsoft.com/fwlink/?linkid=848754).
   2. Firmare l'accordo di riservatezza reciproca e il contratto partner ricevuti. 
      Microsoft richiede questi contratti firmati prima di procedere. 
      A questo punto sarà possibile controllare se il connettore soddisfa i criteri di certificazione. 
   3. Se il connettore viene approvato, Microsoft invia una notifica con le istruzioni per l'onboarding.
2. **Revisione**
   
   1. Inviare queste informazioni al contatto di candidatura per la revisione:
      
      * File OpenAPI che descrive l'API
      * File icona (con estensione PNG o JPG) che rappresenta il connettore (l'icona dovrebbe avere un logo di circa 160 pixel all'interno di un quadrato di 230 pixel. È preferibile un logo bianco su sfondo colorato).
      * Colore del marchio dell'icona in formato esadecimale, corrispondente allo sfondo colorato nel file icona
      * Un account di prova per la convalida
      * Un contatto del supporto tecnico
   2. Se sono necessarie ulteriori informazioni, si verrà contattati.
3. **Pubblicazione**
   
    Dopo la convalida del contenuto e della funzionalità del connettore, ne viene preparata la distribuzione in tutti i prodotti e tutte le aree. In genere, sono necessarie fino a 3 settimane per il processo di certificazione e distribuzione.
   
    Per impostazione predefinita, tutti i connettori vengono pubblicati come "premium". 
    Se l'app viene compilata con Azure, è possibile richiedere di pubblicare il connettore come "standard", rendendolo disponibile a tutti gli utenti dei piani Office 365 Enterprise. 
    Per altre informazioni, rivolgersi al contatto di candidatura.

