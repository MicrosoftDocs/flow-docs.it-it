---
title: Domande frequenti | Microsoft Docs
description: Risposte a diverse domande frequenti su Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/15/2017
ms.author: stepsic
ms.openlocfilehash: af179e30c3b8b7c6d4200f10f122f0d928526f1b
ms.sourcegitcommit: 77aae180d972373d1f251fa6a5c8f484f08ffc15
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2018
ms.locfileid: "39718305"
---
# <a name="frequently-asked-questions"></a>Domande frequenti
## <a name="audience-and-strategy"></a>Destinatari e strategia
### <a name="what-is-microsoft-flow"></a>Che cos'è Microsoft Flow?
Microsoft Flow è un servizio basato sul cloud che consente agli utenti della line-of-business di creare in modo semplice e pratico flussi di lavoro che possono automatizzare processi e attività aziendali dispendiosi in termini di tempo all'interno di applicazioni e servizi.

### <a name="who-is-the-intended-audience-for-microsoft-flow"></a>Chi sono i destinatari di Microsoft Flow?
Microsoft Flow è rivolto a due gruppi distinti di destinatari:

* Citizen integrator della line-of-business nelle organizzazioni che collaborano con l'IT per trasferire la responsabilità delle soluzioni aziendali più vicino all'azienda stessa.
* Decision maker dell'IT che vogliono delegare ai partner della line-of-business la responsabilità di creare le loro soluzioni per consentire a professionisti IT ed esperti dell'integrazione di concentrarsi su strumenti di integrazione più avanzati, come App per la logica di Azure.

### <a name="how-do-microsoft-flow-and-logic-apps-relate-to-each-other"></a>Qual è la correlazione tra Microsoft Flow e App per la logica?
Microsoft Flow fornisce funzionalità che aiutano gli utenti della line-of-business a creare flussi di lavoro automatizzati. App per la logica è un servizio di Azure che fornisce le stesse utili funzionalità di Microsoft Flow, accanto a caratteristiche come l'integrazione con Azure Resource Manager e il portale di Azure, l'interfaccia della riga di comando di PowerShell e xPlat, Visual Studio e connettori aggiuntivi. [Altre informazioni su App per la logica](https://azure.microsoft.com/services/app-service/logic/).

### <a name="how-does-microsoft-flow-fit-in-microsofts-overall-business-application-platform-strategy"></a>Come si inserisce Microsoft Flow nella strategia aziendale globale di piattaforma di applicazioni Microsoft?
Microsoft Flow fa parte di una potente e flessibile piattaforma di applicazioni aziendali che include PowerApps, Common Data Service, Dynamics 365 e Office 365. Questa piattaforma consente a clienti, partner e partner ISV di creare soluzioni progettate appositamente per le loro aziende, per il loro settore, per ruoli funzionali o perfino per aree geografiche specifiche. Gli utenti della line-of-business, che comprendono meglio di tutti le esigenze della loro azienda, ora possono analizzare, comporre e semplificare dati e processi in totale semplicità. Gli sviluppatori professionisti possono estendere facilmente l'automazione, le analisi e le applicazioni della line-of-business per sfruttare servizi di Azure come Funzioni, Servizio app e App per la logica. Connettori delle API, gateway e Microsoft Common Data Service consentono di sfruttare al meglio i servizi o i dati già in uso, nel cloud o locali.

## <a name="functionality"></a>Funzionalità
### <a name="what-do-i-need-to-use-microsoft-flow"></a>Cosa è necessario per usare Microsoft Flow?
Per usare Microsoft Flow, servono un Web browser e un indirizzo e-mail.

### <a name="what-browsers-does-microsoft-flow-support"></a>Quali browser supporta Microsoft Flow?
Microsoft Flow supporta Microsoft Edge e le versioni correnti di Chrome e Safari.

### <a name="which-email-addresses-are-supported"></a>Quali indirizzi e-mail sono supportati?
Microsoft Flow supporta tutti gli indirizzi e-mail tranne quelli che terminano con GOV e MIL.  

### <a name="is-microsoft-flow-available-on-premises"></a>Microsoft Flow è disponibile in locale?
Microsoft Flow è un servizio cloud pubblico. Tuttavia, è possibile connettersi in modo sicuro ai servizi locali tramite il gateway dati locale.

### <a name="what-services-can-microsoft-flow-connect-to"></a>A quali servizi può connettersi Microsoft Flow?
Microsoft Flow si connette a oltre 100 origini dati predefinite, che sono in costante aumento. Alcuni esempi di servizi e origini dati includono:

* SharePoint
* Dynamics 365
* OneDrive
* OneDrive for Business
* Google Drive
* Fogli Google
* Trello
* Twitter
* Box
* Facebook
* SalesForce.com
* MailChimp
* API dei clienti

Un elenco completo di tutti i connettori disponibili è riportato [qui](https://go.microsoft.com/fwlink/?LinkId=832211).

È possibile accedere alle origini dati nella propria infrastruttura IT tramite il [gateway dati locale](gateway-manage.md).

### <a name="what-are-templates"></a>Cosa sono i modelli?
I modelli sono flussi predefiniti per scenari popolari e comuni. L'uso di un modello richiede solo l'accesso ai servizi nel modello e la compilazione di tutte le impostazioni richieste.

### <a name="what-data-sources-will-i-be-able-to-connect-to"></a>A quali origini dati sarà possibile connettersi?
È possibile connettersi a più di 100 servizi standard di Microsoft e terze parti, ad esempio Office 365, Twitter, SharePoint, OneDrive, Dropbox, SQL Server e altro ancora. È inoltre possibile connettersi a servizi di eccellenza, come Salesforce e Common Data Service per PowerApps.

### <a name="how-do-i-connect-to-a-rest-api-in-my-flow"></a>Come ci si connette a un'API REST nel flusso?
Per connettersi a un'API REST che usa JSON e supporta almeno uno degli oltre 10 metodi di autenticazione, è possibile creare [un connettore personalizzato](developer/register-custom-api.md).

### <a name="how-do-i-connect-to-sql-server-and-other-on-premises-data-sources"></a>Come ci si connette a SQL Server e ad altre origini dati locali?
È possibile connettersi ai servizi della rete locale tramite il [gateway dati locale](gateway-manage.md).

### <a name="can-i-share-the-flows-i-create"></a>È possibile condividere i flussi creati?
È possibile condividere i flussi in uno dei seguenti modi:

* È possibile aggiungere colleghi o gruppi all'interno dell'organizzazione come proprietari nei flussi, in modo che possano anche modificare e gestire il flusso.
* Per i flussi che possono essere eseguiti manualmente, è anche possibile concedere ad altre persone o gruppi nell'organizzazione l'autorizzazione a eseguire semplicemente il flusso.

### <a name="how-many-flows-can-i-have"></a>Quanti flussi è possibile avere?
Microsoft Flow comprende fino a 50 flussi. Se necessario, è possibile richiederne altri.

### <a name="where-do-i-get-started-with-microsoft-flow"></a>Come si può imparare a usare Microsoft Flow?
Inizia con le risorse seguenti:

* [Blog](https://flow.microsoft.com)
* [Canale YouTube](https://youtube.com/playlist?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF)
* [Argomento](getting-started.md)
* [Community](https://powerusers.microsoft.com)

### <a name="what-operating-systems-does-the-mobile-app-for-microsoft-flow-support"></a>Quali sono i sistemi operativi supportati dall'app per dispositivi mobili per Microsoft Flow?
L'app per dispositivi mobili Microsoft Flow è disponibile su [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="can-flows-be-turned-off-or-disabled"></a>È possibile disattivare o disabilitare i flussi?

Sì, ogni flusso prevede un'opzione di attivazione/disattivazione che consente di arrestare l'elaborazione delle richieste da parte del flusso.

Vedere la tabella seguente per comprendere come risponde il flusso quando viene nuovamente attivato.

Tipo di trigger|Descrizione
-------|--------
Polling, ad esempio il trigger di **ricorrenza**|Quando il flusso viene riattivato, tutti gli eventi non elaborati/in sospeso vengono elaborati.
Webhook|Quando il flusso viene riattivato, vengono elaborati solo i nuovi eventi generati dopo la riattivazione del flusso.

### <a name="what-regions-and-languages-does-microsoft-flow-support"></a>Quali lingue e aree geografiche supporta Microsoft Flow?
Microsoft Flow è disponibile in 42 lingue e [sei aree geografiche](regions-overview.md).

### <a name="how-does-microsoft-flow-compare-to-sharepoint-designer-2013"></a>Quali sono le differenze tra Microsoft Flow e SharePoint Designer 2013?
Microsoft Flow è il successore di SharePoint Designer per molti scenari aziendali comuni, come approvazioni, revisione di documenti e onboarding/offboarding. Da questo momento in poi, sarà lo strumento predefinito per creare l'automazione del business in SharePoint.

### <a name="how-does-microsoft-flow-ensure-that-corporate-data-isnt-accidentally-released-to-social-media-services"></a>Come fa Microsoft Flow a garantire che i dati aziendali non vengano accidentalmente divulgati ai servizi social media?
Gli amministratori possono creare [criteri di prevenzione della perdita dei dati](prevent-data-loss.md) per assicurarsi che in Microsoft Flow siano usati solo i servizi approvati.

## <a name="licensing"></a>Licenze
### <a name="will-microsoft-flow-still-have-a-free-or-trial-option"></a>Per Microsoft Flow continuerà a essere disponibile una versione gratuita o di valutazione?
Sì. Microsoft Flow è disponibile come opzione gratuita con diritti utente limitati oppure è possibile iscriversi a una valutazione di valutazione gratuita della durata di 90 giorni. Durante il periodo di valutazione, è possibile attivare la sottoscrizione in qualsiasi momento.

### <a name="what-pricing-plans-do-you-offer"></a>Quali piani tariffari offrite?
Microsoft Flow offre livelli di servizio sia gratuiti sia a pagamento. [Altre informazioni sui prezzi](billing-questions.md).

## <a name="learn-more"></a>Altre informazioni

* Visualizzare la [presentazione dell'Apprendimento guidato](guided-learning/index.yml) di Microsoft Flow
* Informazioni di base su Microsoft Flow nella [Guida introduttiva](getting-started.md)