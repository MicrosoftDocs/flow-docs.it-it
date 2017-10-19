---
title: Usare gli ambienti per gestire i flussi | Microsoft Docs
description: Informazioni sull'uso di ambienti per separare e gestire i flussi.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: wnScBLz7css
courseduration: 8m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 8ded06b5ffb08cf3cced1bf95e7e81415cdfe21b
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="use-environments-to-manage-flows"></a>Usare gli ambienti per gestire i flussi
## <a name="what-is-an-environment"></a>Che cos'è un ambiente:
Un ambiente è uno spazio virtuale usato per archiviare, gestire e condividere app, flussi e dati business in Common Data Service. Per gli ambienti è prevista la georilevazione, quindi anche tutte le app e tutti i dati archiviati nel database di un ambiente sono soggetti a georilevazione.  

## <a name="terms-you-should-get-familiar-with"></a>Terminologia da conoscere
| **Termine** | **Descrizione** |
| --- | --- |
| **Interfaccia di amministrazione** |L'interfaccia di amministrazione è un [portale Web](https://admin.flow.microsoft.com) per la gestione di tutti gli ambienti e dei criteri di prevenzione della perdita dei dati. |
| **Common Data Service** |Common Data Service consente di aggiungere funzionalità di archiviazione e modellazione dei dati alle app. |
| **Ruoli ambiente** |I due ruoli ambiente sono Amministratore di ambiente o Autore di ambiente. |
| **Ruoli utente** |I due ruoli utente predefiniti sono Utente dell'organizzazione e Proprietario del Database. È possibile aggiungere ruoli e associare le autorizzazioni a tali ruoli. |

## <a name="purposes-for-an-environment"></a>Scopi di un ambiente
È possibile usare gli ambienti per:  

* Separare app, flussi e business data in base a ruoli, requisiti di sicurezza o utenti diversi.  
* Separare app, flussi e dati business in base alla posizione dei team o dei reparti.
* Gestire ambienti di test e di produzione.  

## <a name="how-to-use-environments"></a>Come usare gli ambienti
Gli ambienti possono essere usati per vari scopi diversi, a seconda delle esigenze dell'organizzazione. Ecco alcuni esempi:  

* È possibile scegliere di compilare tutte le app e i flussi in un unico ambiente 
* Si potrebbe decidere di creare un ambiente per i diversi tipi di app e flussi. Ad esempio, è possibile creare un ambiente per il test e un altro ambiente per la produzione.  
* Si può anche scegliere di creare gli ambienti in base alla struttura dell'organizzazione o persino in base alla posizione geografica di team o reparti. Se l'organizzazione ha team in Australia, Messico e in Europa, ad esempio, si potrebbe creare un ambiente per ognuna di queste sedi e gestirli in modo indipendente.  

**Nota**: gli ambienti non sono visibili per gli utenti, che non devono quindi preoccuparsi di conoscere l'ambiente in cui sono inseriti. Gli ambienti sono uno strumento progettato per consentire agli amministratori di classificare, gestire e condividere le app e i flussi dell'organizzazione.  

## <a name="what-are-roles"></a>Cosa sono i ruoli?
A una persona con accesso a un ambiente deve essere assegnato il ruolo di **Amministratore dell'ambiente** o **Autore dell'ambiente**. Gli amministratori dell'ambiente possono eseguire tutte le attività amministrative per un ambiente. Un autore di ambiente può creare risorse in un ambiente esistente. Una singola persona può avere contemporaneamente entrambi i ruoli.  

**Nota**: tutti gli utenti avranno accesso a un ambiente predefinito quando viene loro concesso l'accesso a Microsoft Flow. Gli utenti possono avere accesso a più ambienti.  

## <a name="create-an-environment"></a>Creare un ambiente
È possibile creare l'ambiente dall'[interfaccia di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com) in solo due passaggi:  

1. Specificare un nome per l'ambiente.
2. Selezionare l'area geografica in cui verrà ospitato l'ambiente.
3. È possibile decidere facoltativamente di creare un database per l'ambiente. È possibile creare un database dopo aver creato un ambiente, se lo si desidera.
4. Selezionare facoltativamente chi avrà accesso al database. È possibile limitare l'accesso o consentire a chiunque di accedere al database. 

## <a name="add-users-to-an-environment"></a>Aggiungere utenti a un ambiente.
Dopo aver creato un ambiente, è possibile aggiungere utenti al ruolo di Amministratore o di Autore dell'ambiente. Come per tutte le altre attività amministrative, anche questa operazione deve essere eseguita dall'interfaccia di amministrazione.  

Dopo aver creato l'ambiente e aggiunto gli utenti, è anche possibile creare criteri di prevenzione della perdita dei dai (DLP) per agevolare l'uso dei dati business. Questa procedura verrà descritta nell'argomento successivo. 

