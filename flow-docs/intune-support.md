---
title: App per dispositivi mobili Microsoft Flow supporta ora MAM di Microsoft Intune. | Microsoft Docs
description: App per dispositivi mobili Microsoft Flow supporta ora MAM di Microsoft Intune.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 7cc2b37eb27ed0e2107eeaada02afb072d9a0098
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65060492"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>App per dispositivi mobili Microsoft Flow supporta Microsoft Intune

L'app per dispositivi mobili Microsoft Flow per iOS e Android supporta Mobile Application Management (MAM di Intune) senza registrazione del dispositivo. Con MAM consente agli amministratori IT di creare e applicare i criteri di dati per dispositivi mobili per proteggere i dati dell'organizzazione.

## <a name="why-intune-support-is-important"></a>Perché è importante il supporto di Intune

Le organizzazioni cercano maggiore controllo sui dati che risiedono sui dispositivi mobili dei dipendenti. Le organizzazioni potrebbero voler limitare tali spostamento dei dati con il dispositivo e verificare che i dati vengono rimossi, dovrebbe il dipendente lascia l'organizzazione.

## <a name="what-is-microsoft-application-management-mam"></a>Che cos'è gestione (MAM) di Microsoft Application

MAM consente alle organizzazioni di creare criteri che determinano come le app vengono usate all'interno di un tenant. Ciò include l'applicazione della crittografia dei dati di app, limitando la possibilità di copiare o estrarre i dati soltanto applicazioni approvati o applicare un PIN in un dispositivo.

### <a name="prerequisites"></a>Prerequisiti

- Una di Intune [criteri di protezione delle app](https://docs.microsoft.com/intune/app-protection-policies).
- Un gruppo di Azure Active Directory (Azure AD).
- Portale aziendale. Uno dei principali vantaggi dell'uso di MAM è che i dispositivi non devono essere registrati in MAM di Intune. Tutto ciò che ha richiesto è il portale aziendale di cui è disponibile da Google Play store e l'App Store.
- Versione 2.31.0 dell'app per dispositivi mobili Microsoft Flow per iOS, Android o Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Creare un criterio di protezione delle app, assegnare App ai criteri, definire le impostazioni e aggiungere utenti a un gruppo di Azure AD

Per l'app per dispositivi mobili Microsoft Flow da gestire, è necessario:

1. Creare un criterio di protezione delle app.
1. Assegnare l'app per dispositivi mobili Microsoft Flow per i criteri di protezione delle app.
1. Assegnare le impostazioni dei criteri. Ad esempio, è possibile assegnare i criteri per richiedere un PIN accedere al dispositivo mobile che esegue l'app per dispositivi mobili Microsoft Flow.
1. Applicare i criteri di protezione delle app a uno specifico gruppo di Azure AD.
1. Aggiungere tutti gli utenti a cui si applica i criteri di protezione delle app al gruppo di Azure AD.

Seguire questi passaggi per creare un [criteri di protezione delle app](https://docs.microsoft.com/intune/app-protection-policies) che richiede agli utenti di app per dispositivi mobili Microsoft Flow immettere un PIN prima di poter accedere all'app. 


## <a name="test-the-app-protection-policy"></a>Testare i criteri di protezione delle app

Dopo aver creato i criteri di protezione delle app e utenti assegnati al gruppo di Azure AD, è possibile usare l'app per dispositivi mobili Microsoft Flow e verificare il funzionamento dei criteri.

Per verificare il funzionamento dei criteri, seguire questa procedura:

1. Installare l'app per dispositivi mobili Microsoft Flow in un dispositivo cui piattaforma corrisponde a una delle piattaforme che è definito nei criteri di protezione delle app.
1. Accedere all'app per dispositivi mobili con un account che si trova in gruppo di Azure AD che limita l'uso dell'app per dispositivi mobili per gli utenti che dispongono di un PIN.

Verrà quindi chiesto:
1. Installare l'App portale aziendale.
1. Se si ha già un PIN che soddisfa i criteri di criteri di protezione app, impostare il PIN.


## <a name="learn-more"></a>Altre informazioni

Informazioni su come creare un [criteri di protezione delle app](https://docs.microsoft.com/intune/app-protection-policies).

