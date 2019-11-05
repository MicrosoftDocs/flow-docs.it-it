---
title: Microsoft Flow app per dispositivi mobili supporta ora la gestione delle applicazioni mobili di Microsoft Intune. | Microsoft Docs
description: Microsoft Flow app per dispositivi mobili supporta ora la gestione delle applicazioni mobili di Microsoft Intune.
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
ms.openlocfilehash: d5709d7f98c3f4cc1dcf7d0da8fc5c9501adb84c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547388"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Microsoft Flow app per dispositivi mobili supporta Microsoft Intune
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Il Microsoft Flow app per dispositivi mobili per iOS e Android supporta la gestione di applicazioni mobili (MAM) di Intune senza registrazione del dispositivo. L'uso di MAM consente agli amministratori IT di creare e applicare criteri di dati per dispositivi mobili per salvaguardare i dati dell'organizzazione.

## <a name="why-intune-support-is-important"></a>Motivi per cui il supporto di Intune è importante

Le organizzazioni cercano un maggiore controllo sui dati che si trovano sui dispositivi mobili dei dipendenti. Le organizzazioni potrebbero voler limitare il modo in cui i dati vengono spostati nel dispositivo e assicurarsi che i dati vengano rimossi, qualora il dipendente lasci l'organizzazione.

## <a name="what-is-microsoft-application-management-mam"></a>Che cos'è Microsoft Application Management (MAM)

MAM consente alle organizzazioni di creare criteri che regolano il modo in cui le app vengono usate in un tenant. Questo include l'applicazione della crittografia dei dati dell'app, limitando la possibilità di copiare o estrarre i dati solo nelle applicazioni approvate o di applicare un PIN in un dispositivo.

### <a name="prerequisites"></a>Prerequisiti

- Criteri di [protezione delle app](https://docs.microsoft.com/intune/app-protection-policies)di Intune.
- Un gruppo Azure Active Directory (Azure AD).
- Portale aziendale. Un vantaggio fondamentale dell'uso di MAM è che i dispositivi non devono essere registrati in MAM di Intune. È necessario solo il Portale aziendale, disponibile dall'App Store e dall'archivio Google Play.
- Versione 2.31.0 dell'app Microsoft Flow mobile per iOS, Android o Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Creare un criterio di protezione delle app, assegnare le app al criterio, definire le impostazioni e aggiungere gli utenti a un gruppo di Azure AD

Per la gestione dell'app Microsoft Flow per dispositivi mobili, è necessario:

1. Creare un criterio di protezione delle app.
1. Assegnare l'app per dispositivi mobili Microsoft Flow ai criteri di protezione delle app.
1. Assegnare le impostazioni dei criteri. Ad esempio, è possibile assegnare il criterio per richiedere un PIN per accedere al dispositivo mobile che esegue l'app per dispositivi mobili Microsoft Flow.
1. Applicare i criteri di protezione delle app a un gruppo di Azure AD specifico.
1. Aggiungere tutti gli utenti a cui si applicano i criteri di protezione delle app al gruppo di Azure AD.

Seguire questa procedura per creare un [criterio di protezione delle app](https://docs.microsoft.com/intune/app-protection-policies) che richiede agli utenti di Microsoft Flow app per dispositivi mobili di immettere un PIN prima di poter accedere all'app. 


## <a name="test-the-app-protection-policy"></a>Testare i criteri di protezione delle app

Dopo aver creato i criteri di protezione delle app e gli utenti assegnati al gruppo di Azure AD, è possibile usare l'app Microsoft Flow per dispositivi mobili e verificare il funzionamento del criterio.

Per verificare il funzionamento del criterio, attenersi alla procedura seguente:

1. Installare l'app per dispositivi mobili Microsoft Flow in un dispositivo con piattaforma corrispondente a una delle piattaforme definite nei criteri di protezione delle app.
1. Accedere all'app per dispositivi mobili con un account che si trova nel gruppo Azure AD che limita l'uso dell'app per dispositivi mobili agli utenti che hanno un PIN.

Verrà quindi richiesto di:
1. Installare il Portale aziendale.
1. Impostare il PIN se non si ha già un PIN che soddisfi i criteri del criterio di protezione delle app.


## <a name="learn-more"></a>Ulteriori informazioni

Informazioni su come creare un [criterio di protezione delle app](https://docs.microsoft.com/intune/app-protection-policies).

