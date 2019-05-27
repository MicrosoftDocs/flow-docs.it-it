---
title: Introduzione ai criteri di prevenzione della perdita dei dati (DLP). | Microsoft Docs
description: Introduzione ai criteri di prevenzione della perdita dei dati di Microsoft Flow.
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
ms.date: 04/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: f019a6ca5856c0fb3c5360642b4f3fcb23594b16
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64950496"
---
# <a name="data-loss-prevention-dlp-policies"></a>Criteri di prevenzione della perdita dei dati (DLP)

Questo documento presenta i criteri di prevenzione della perdita dei dati, che consentono di impedire la condivisione dei dati dell'organizzazione con un elenco di connettori definito.

## <a name="whats-a-data-loss-prevention-policy"></a>Che cos'è un criterio di prevenzione della perdita dei dati?

I dati di un'organizzazione sono fondamentali per il suo successo. Devono essere immediatamente disponibili per consentire di elaborare decisioni, ma vanno anche protetti per impedire che vengano condivisi con destinatari non autorizzati ad accedervi. Per proteggerli, Microsoft Flow permette di creare e applicare criteri che stabiliscono quali connettori consumer possono accedere ai dati di business e condividerli. Questi criteri che definiscono le modalità di condivisione dei dati sono detti "criteri di prevenzione della perdita dei dati" (DLP).

## <a name="why-create-a-dlp-policy"></a>Perché creare criteri di prevenzione della perdita dei dati DLP?

La creazione dei criteri DLP consente di definire chiaramente quali connettori consumer possono accedere ai dati di business e condividerli. Ad esempio, un'organizzazione che usa Microsoft Flow potrebbe non volere che i dati aziendali in SharePoint vengano pubblicati automaticamente nel proprio feed di Twitter. Per impedirlo, si crea un criterio DLP che impedisca di usare i dati di SharePoint come origine per i tweet.

## <a name="benefits-of-a-dlp-policy"></a>I vantaggi dei criteri DLP

* Garantisce che i dati siano gestiti in modo uniforme in tutta l'organizzazione.
* Impedisce che importanti dati aziendali vengano accidentalmente pubblicati in connettori come i social media.

## <a name="managing-dlp-policies"></a>Gestione dei criteri DLP

### <a name="prerequisites-for-managing-dlp-policies"></a>Prerequisiti per la gestione dei criteri DLP

* Autorizzazioni di amministratore dell'ambiente o del tenant.

    Altre informazioni sulle autorizzazioni sono disponibili nell'[articolo sugli ambienti](environments-overview-admin.md).
* Una [licenza Microsoft Flow P2](billing-questions.md).

## <a name="create-a-dlp-policy"></a>Creare criteri DLP

### <a name="prerequisites-for-creating-dlp-policies"></a>Prerequisiti per la creazione dei criteri DLP

Per creare un criterio DLP, è necessario avere le autorizzazioni per almeno un ambiente.

Seguire questa procedura per creare criteri DLP che impediscano la pubblicazione su Twitter dei dati nel sito di SharePoint aziendale:

1. Accedere all'[interfaccia di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com) (interfaccia di amministrazione).

1. Selezionare la scheda Criteri dati e quindi fare clic sul collegamento **Nuovo criterio**:

    ![Accedi](./media/prevent-data-loss/create-policy-1.png)
1. Selezionare la scheda **Gruppi di dati**.

1. Nella pagina immettere il nome del criterio DLP come *Secure Data Access for Contoso* (Accesso protetto ai dati Contoso) nell'etichetta **Nome del criterio dati**:

    ![Accedi](./media/prevent-data-loss/create-policy-2.png)

1. Selezionare l'[ambiente](environments-overview-admin.md) nella scheda **Ambienti**.

    > [!NOTE]
    > L'amministratore dell'ambiente può creare criteri applicabili a un ambiente solo, l'amministratore del tenant invece può creare criteri applicabili a qualsiasi combinazione di ambienti:
    >
    >

    ![Selezionare l'ambiente](./media/prevent-data-loss/create-policy-3.png)

1. Selezionare la scheda **Data groups** (Gruppi di dati):

    ![Selezionare i gruppi di dati](./media/prevent-data-loss/create-policy-4.png)

1. Selezionare il collegamento **Aggiungi** nella casella di gruppo **Business data only** (Solo dati business):

    ![Selezionare Aggiungi](./media/prevent-data-loss/create-policy-5.png)

1. Selezionare i connettori **SharePoint** e **Salesforce** nella pagina **Aggiungi connettori**:

   ![Selezionare i connettori](./media/prevent-data-loss/create-policy-6.png)

1. Selezionare il pulsante **Aggiungi connettori** per aggiungere i connettori che possono condividere i dati di business.

1. Selezionare **Salva il criterio** nell'angolo in alto a destra della schermata.

1. Dopo qualche istante il nuovo criterio DLP comparirà nell'apposito elenco:

    ![Elenco DLP](./media/prevent-data-loss/create-policy-9.png)

1. **Facoltativo.** Inviare un'e-mail o un altro tipo di comunicazione al team per segnalare la disponibilità di nuovi criteri DLP.

A questo punto è stato creato un criterio DLP che consente all'app di condividere i dati fra SharePoint e Salesforce, impedendo invece di condividerli con altri servizi.

> [!NOTE]
> L'aggiunta di un servizio a un gruppo di dati ne comporta la rimozione automatica dall'altro gruppo. Ad esempio, se Twitter è incluso nel gruppo di dati **Business data only** e non si vuole consentire la condivisione dei dati business con Twitter, è sufficiente aggiungere il servizio Twitter al gruppo di dati **No Business data allowed**. Twitter verrà così rimosso dal gruppo Business data only.
>
>

## <a name="data-sharing-violations"></a>Violazioni relative alla condivisione dei dati

Presupponendo di aver creato i criteri DLP descritti in precedenza, se un utente crea un flusso che condivide i dati tra Salesforce (il gruppo contiene **solo dati di business**) e Twitter (nel gruppo in cui i **dati di business non sono consentiti**), l'utente verrà informato che il flusso è **sospeso** a causa di un conflitto con i criteri creati per la prevenzione della perdita dei dati.

![Creare il flusso](./media/prevent-data-loss/10.png)

Se si viene contattati da utenti che segnalano flussi sospesi, ecco alcuni aspetti da considerare:

1. In questo esempio, se esiste un motivo valido per condividere i dati di business tra SharePoint e Twitter, è possibile modificare i criteri DLP.

1. Chiedere all'utente di modificare il flusso conformemente ai criteri DLP.

1. Chiedere all'utente di lasciare sospeso il flusso finché non viene presa una decisione riguardo alla condivisione dei dati tra queste due entità.

## <a name="find-a-dlp-policy"></a>Cercare un criterio DLP

### <a name="admins"></a>Amministratori

Gli amministratori possono utilizzare la funzionalità di ricerca dell'interfaccia di amministrazione per cercare specifici criteri DLP.

> [!NOTE]
> È opportuno che gli amministratori pubblichino tutti i criteri DLP in modo che gli utenti dell'organizzazione ne siano a conoscenza prima di creare flussi.
>
>

### <a name="makers"></a>Responsabili operativi

Se non si dispone delle autorizzazioni di amministratore e si desidera saperne di più sui criteri DLP della propria organizzazione, contattare l'amministratore. Altre informazioni sono disponibili anche nell'[articolo sugli ambienti per responsabili operativi](environments-overview-maker.md).

> [!NOTE]
> Solo gli amministratori possono modificare o eliminare i criteri DLP.
>
>

## <a name="edit-a-dlp-policy"></a>Modificare un criterio DLP

1. Avviare l'[interfaccia di amministrazione](https://admin.flow.microsoft.com).

1. Nell'interfaccia di amministrazione che viene aperta fare clic sul collegamento **Data policies** (Criteri dati) a sinistra.

    ![Selezionare i criteri dati](./media/prevent-data-loss/2.png)

1. Nell'elenco dei criteri DLP esistenti fare clic sull'apposito pulsante accanto al criterio da modificare.

1. Apportare le modifiche necessarie al criterio. Ad esempio, è possibile modificare l'ambiente o i servizi nei gruppi di dati.

1. Fare clic su **Salva il criterio** per salvare le modifiche.

> [!NOTE]
> L'amministratore dell'ambiente può visualizzare i criteri DLP creati dall'amministratore del tenant, ma non modificarli.
>
>

## <a name="delete-a-dlp-policy"></a>Eliminare un criterio DLP

1. Avviare l'[interfaccia di amministrazione](https://admin.flow.microsoft.com).

1. Selezionare la scheda **Criteri dati**.

    ![Selezionare la scheda Criteri dati](./media/prevent-data-loss/2.png)

1. Nell'elenco dei criteri DLP esistenti fare clic sull'apposito pulsante accanto al criterio da eliminare:

    ![Selezionare il pulsante Elimina](./media/prevent-data-loss/3-delete.png)

1. Fare clic sul pulsante **Delete** (Elimina) per confermare l'eliminazione del criterio:

    ![Confermare l'eliminazione del criterio](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>Autorizzazioni relative ai criteri DLP

Solo gli amministratori del tenant e dell'ambiente possono creare e modificare i criteri DLP. Altre informazioni sulle autorizzazioni sono disponibili nell'articolo sugli [ambienti](environments-overview-admin.md).


## <a name="custom-and-http-connectors"></a>Connettori personalizzati e HTTP

I connettori personalizzati e HTTP devono essere aggiunto a DLPs usando un modello di Microsoft Flow o un di PowerShell.

> [!TIP]
> È possibile effettuare il downgrade dalla versione dello schema 2018-11-01. Supporto HTTP non può essere rimosso da un criterio. Se si prova a rimuovere il supporto HTTP, i criteri DLP potrebbero essere danneggiato. Inoltre, se un criterio DLP è aggiornato per supportare HTTP connettori, flussi correnti usando queste funzionalità HTTP potrebbero essere spenti.

Di seguito sono i connettori HTTP che è possibile aggiungere a un criterio:

- HTTP (e HTTP + Swagger)
- HTTP Webhook
- Richiesta HTTP

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Aggiungere i connettori personalizzati e HTTP con i modelli

Per aggiungere un connettore personalizzato in un criterio utilizzando un [modello](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/), immettere il nome del criterio, il gruppo a cui aggiungere il connettore e il nome del connettore, ID e tipo. Eseguire una sola volta il flusso per aggiungere il connettore personalizzato per il criterio e il gruppo specificato.

Per aggiungere i connettori HTTP a un criterio esistente tramite il [modello](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/), immettere il nome dei criteri si desidera aggiungerli a e quindi eseguire il flusso.

## <a name="add-custom-and-http-connectors-with-powershell"></a>Aggiungi personalizzato e i connettori HTTP con PowerShell

Per aggiungere il supporto per i connettori personalizzati e/o connettori HTTP a un criterio tramite PowerShell [scaricare](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) e importare gli script di PowerShell di PowerApps più recenti e quindi usare questi cmdlet:  'Nuovo AdminDlpPolicy', 'Set-AdminDlpPolicy', 'Add-CustomConnectorToPolicy' e 'Remove-CustomConnectorFromPolicy' per modificare il criterio. Usare il ' Get-Help-detailed' cmdlet come riferimento.


> [!IMPORTANT]
> Usare la versione dello schema 2018-11-01 durante la creazione o l'aggiornamento di un criterio DLP per includere i connettori HTTP. Aggiunta di HTTP supporta l'uso del modello o PowerShell influiranno solo i criteri specificati. Nuovi criteri creati tramite l'interfaccia di amministrazione non conterrà i connettori HTTP.



## <a name="next-steps"></a>Passaggi successivi

* [Altre informazioni sugli ambienti](environments-overview-admin.md)
* [Altre informazioni su Microsoft Flow](getting-started.md)
* [Altre informazioni sull'interfaccia di amministrazione](admin-center-introduction.md)
* [Altre informazioni sull'integrazione con i dati](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
