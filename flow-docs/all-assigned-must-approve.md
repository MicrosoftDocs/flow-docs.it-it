---
title: Creare un flusso di approvazione che richieda a tutti gli utenti di approvare | Microsoft Docs
description: Creare un flusso di approvazione che richieda a tutti gli utenti di approvare o a una persona di rifiutare una richiesta.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/27/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 141eb19018e080191bf0fe2ba6f47f0739d347d7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456746"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Creare un flusso di approvazione che richieda a tutti gli utenti di approvare

Questa procedura dettagliata illustra come creare un flusso di lavoro che richieda a tutti (tutti i responsabili approvazione assegnati) di concordare sull'approvazione di una richiesta di ferie, ma permetta a qualsiasi responsabile approvazione di rifiutare l'intera richiesta.

Questo tipo di flusso di lavoro di approvazione è utile in un'organizzazione che richiede l'approvazione di una richiesta di ferie sia da parte del manager del richiedente sia dal manager del manager. Tuttavia, uno dei manager può rifiutare la richiesta senza l'input dell'altra persona.

> [!NOTE]
> Anche se questa procedura dettagliata è specifica di uno scenario di approvazione di permessi/ferie, è possibile usare questo tipo di flusso di approvazione in tutte le situazioni in cui più responsabili approvazione devono approvare una richiesta.
>
>

## <a name="prerequisites"></a>Prerequisiti

* Accesso a [Microsoft Flow](https://flow.microsoft.com), Microsoft Office 365 Outlook e Utenti di Microsoft Office 365.
* Un [elenco](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) di SharePoint.

    Questa procedura dettagliata presuppone che sia stato creato un elenco di SharePoint che viene usato per richiedere ferie. Vedere la procedura dettagliata sulle [approvazioni parallele](parallel-modern-approvals.md) per un esempio approfondito che illustra in dettaglio il possibile aspetto dell'elenco di SharePoint.
* Familiarità con le nozioni di base della creazione di flussi.

    È possibile esaminare come aggiungere [azioni, trigger](multi-step-logic-flow.md#add-another-action) e [condizioni](add-condition.md). I passaggi seguenti presuppongono che si sappia come eseguire queste azioni.

> [!NOTE]
> Quando si usano SharePoint e Office 365 Outlook in questa procedura dettagliata, è possibile usare altri servizi come Zendesk, Salesforce, Gmail o uno tra gli oltre [200 servizi](https://flow.microsoft.com/connectors/) supportati da Microsoft Flow.
>
>

## <a name="create-the-flow"></a>Creare il flusso

> [!NOTE]
> Se non è stata creata in precedenza una connessione a SharePoint o a Office 365, seguire le istruzioni quando viene chiesto di accedere.
>
>

Questa procedura dettagliata usa i token. Per visualizzare l'elenco di token, toccare o fare clic su qualsiasi controllo di input e quindi cercare il token nell'elenco **Contenuto dinamico** visualizzato.

Accedere a [Microsoft Flow](https://flow.microsoft.com) e quindi eseguire la procedura seguente per creare il flusso.

1. Selezionare **Flussi personali** > **Crea da zero** in alto a destra nella schermata.
1. Aggiungere il trigger **SharePoint - Quando viene creato o modificato un nuovo elemento**.
1. Immettere l'**indirizzo sito** per il sito di SharePoint che ospita l'elenco delle richieste di ferie e quindi selezionare l'elenco **Nome elenco**.
1. Aggiungere l'azione **Office 365 Users - Get manager V2** (Utenti di Office 365 - Recupera il responsabile V2), selezionare la casella **Utente (UPN)** e quindi aggiungervi il token **Creato da Posta elettronica**.

    Il token **Creato da Posta elettronica** si trova sotto la categoria **Quando viene creato o modificato un elemento** dell'elenco **Contenuto dinamico**. Questo token fornisce in modo dinamico l'accesso ai dati sul responsabile per la persona che ha creato l'elemento in SharePoint.

1. Aggiungere un'altra azione **Office 365 Users - Get manager V2** (Utenti di Office 365 - Recupera il responsabile V2) e quindi aggiungere il token **Posta** alla casella **Utente (UPN)**.

    Il token **Posta** si trova sotto la categoria **Get manager V2 2** (Recupera il responsabile V2 2) dell'elenco **Contenuto dinamico**. Questo token fornisce in modo dinamico l'accesso all'indirizzo di posta elettronica per il responsabile del responsabile.

    È anche possibile rinominare la scheda **Get manager V2 2** (Recupera il responsabile V2 2) in maniera più significativa, ad esempio "Ignora responsabile livello".
1. Aggiungere l'azione **Avviare un'approvazione**, quindi selezionare **Tutti dall'elenco assegnato** dall'elenco **Tipo di approvazione**.

   > [!IMPORTANT]
   > Se un responsabile approvazione rifiuta, la richiesta di approvazione viene considerata rifiutata per tutti i responsabili.
   >
   >
1. Usare la tabella seguente come guida per completare la scheda **Avviare un'approvazione**.

   | Campo | Descrizione |
   | --- | --- |
   |  Tipo di approvazione |Usare **Chiunque dall'elenco assegnato** per indicare che qualsiasi responsabile approvazione può approvare o rifiutare la richiesta. </p>Usare **Tutti dall'elenco assegnato** per indicare che una richiesta viene approvata solo se tutti concordano e rifiutata se una singola persona la rifiuta. |
   |  Titolo |Il titolo della richiesta di approvazione. |
   |  Assegnato a |Gli indirizzi di posta elettronica dei responsabili approvazione. |
   |  Dettagli |Eventuali informazioni aggiuntive da inviare ai responsabili approvazione elencati nel campo **Assegnato a**. |
   |  Collegamento all'elemento |URL dell'elemento di approvazione. In questo esempio, si tratta di un collegamento all'elemento di SharePoint. |
   |  Descrizione collegamento all'elemento |Descrizione testuale per il **Collegamento all'elemento**. |

   > [!TIP]
   > L'azione **Avviare un'approvazione** fornisce diversi token, tra cui **Risposta** e **Riepilogo della risposta**. Usare questi token nel flusso per fornire report avanzati dei risultati dell'esecuzione di un flusso di richiesta di approvazione.
   >
   >

    La scheda **Avviare un'approvazione** è un modello per la richiesta di approvazione inviata ai responsabili. Configurarla in modo che sia utile all'organizzazione. Di seguito è riportato un esempio.

    ![avviare un'approvazione](media/all-assigned-must-approve/start-an-approval-card.png)

1. Aggiungere l'azione **Office 365 Outlook - Invia un messaggio di posta elettronica**, quindi configurarla in modo da inviare un messaggio con i risultati della richiesta.

    Di seguito è riportato un esempio del possibile aspetto della scheda **Invia un messaggio di posta elettronica**.

    ![inviare un messaggio di posta elettronica](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Qualsiasi azione che segue l'azione **Avviare un'approvazione** viene eseguita in base alla selezione nell'elenco **Tipo di approvazione** nella scheda **Avviare un'approvazione**. La tabella seguente elenca il comportamento in base alla selezione.
>
>

| Tipo di approvazione | Comportamento |
| --- | --- |
| Chiunque dall'elenco assegnato |Le azioni che seguono l'azione **Avviare un'approvazione** vengono eseguite dopo che uno dei responsabili ha preso una decisione. |
| Tutti dall'elenco assegnato |Le azioni che seguono l'azione **Avviare un'approvazione** vengono eseguite dopo che un responsabile ha rifiutato la richiesta oppure dopo che tutti i responsabili hanno approvato la richiesta. |

Nella parte superiore della schermata immettere un nome nella casella **Nome flusso** e quindi selezionare **Crea flusso** per salvarlo.

Complimenti, il flusso è stato completato. Se tutti i passaggi sono stati eseguiti correttamente, il flusso sarà simile all'immagine seguente:

![immagine flusso generale](media/all-assigned-must-approve/overall-flow.png)

A questo punto, ogni volta che un elemento viene aggiunto all'elenco di SharePoint o se un elemento viene modificato, viene attivato il flusso che invia le richieste di approvazione a tutti i responsabili che sono elencati nella casella **Assegnato a** della scheda **Avviare un'approvazione**. Il flusso invia le richieste di approvazione attraverso l'app Microsoft Flow per dispositivi mobili e la posta elettronica. La persona che crea l'elemento in SharePoint riceve un messaggio di posta elettronica che riepiloga i risultati, indicando in modo chiaro se la richiesta è stata approvata o rifiutata.

Di seguito è riportato un esempio della richiesta di approvazione che viene inviata a ogni responsabile approvazione.

![richiesta di approvazione](media/all-assigned-must-approve/approval-request.png)

Di seguito è riportato un esempio del possibile aspetto di una risposta e di un riepilogo della risposta dopo l'esecuzione del flusso.

![token di risposta](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Altre informazioni sulle approvazioni

* [Approvazioni moderne di un unico responsabile approvazione](modern-approvals.md)
* [Approvazioni moderne sequenziali](sequential-modern-approvals.md)
* [Approvazioni moderne parallele](parallel-modern-approvals.md)
* [Approvazioni e Microsoft Common Data Service](common-data-model-approve.md)
* [Approvare le richieste in viaggio](mobile-approvals.md)
