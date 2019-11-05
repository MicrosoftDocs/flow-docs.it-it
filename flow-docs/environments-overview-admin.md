---
title: Panoramica dell'ambiente per gli amministratori | Microsoft Docs
description: Utilizzo, creazione e gestione di ambienti in Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: eb3e1050d22b8f672f47214952428b86186ba145
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547969"
---
# <a name="using-environments-within-microsoft-flow"></a>Uso di ambienti in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="benefits"></a>Vantaggi

Gli ambienti offrono i vantaggi seguenti:

* **Località dei dati**: gli ambienti possono essere creati in aree diverse e sono associati alla posizione geografica. Quando si crea un flusso in un ambiente, tale flusso viene indirizzato a tutti i Data Center nella posizione geografica. Questo offre anche un vantaggio in merito alle prestazioni.

    Se gli utenti si trovano in Europa, creare e usare l'ambiente nell'area Europa. Se gli utenti si trovano nella Stati Uniti, creare e usare l'ambiente negli Stati Uniti 

    > [!IMPORTANT]
    > Se si elimina l'ambiente, vengono eliminati anche tutti i flussi all'interno dell'ambiente. Questo vale per qualsiasi elemento creato in quell'ambiente, incluse le connessioni, i gateway, PowerApps e altro ancora.
* **Prevenzione della perdita dei dati**: come amministratore, non si vuole che i flussi ottengano i dati da una posizione interna (ad esempio *OneDrive for business* o un elenco di SharePoint che contiene informazioni sugli stipendi), quindi pubblicano i dati pubblicamente (ad esempio  *Twitter*). Usare la prevenzione della perdita dei dati per controllare quali servizi possono condividere i dati all'interno della distribuzione di Microsoft Flow.

    Ad esempio, è possibile aggiungere i servizi *SharePoint* e *OneDrive for business* a un criterio di business data only. Tutti i flussi creati in questo ambiente possono usare i servizi *SharePoint* e *OneDrive for business* . Tuttavia, non saranno in grado di condividere i dati con altri servizi che non sono inclusi nei criteri di solo dati aziendali.

  > [!NOTE]
  > La prevenzione della perdita dei dati è disponibile con alcuni SKU di licenza, inclusa la licenza P2.

* **Limite di isolamento per tutte le risorse**: qualsiasi flusso, gateway, connessione, connettore personalizzato e così via si trova in un ambiente specifico. Non esistono in nessun altro ambiente.
* **Common Data Service**: di seguito sono riportate le opzioni disponibili se si vuole creare un flusso che inserisce i dati in un servizio:

  * Inserire i dati in un file di Excel e archiviare il file di Excel in un account di archiviazione cloud, ad esempio OneDrive.
  * Creare un database SQL e quindi archiviarvi i dati.
  * Usare il Common Data Service per archiviare i dati.

    Ogni ambiente può avere un massimo di un database per i flussi nel Common Data Service. L'accesso al Common Data Service dipende dalla licenza acquistata; il Common Data Service non è incluso con la licenza gratuita.

## <a name="limitations"></a>Limitazioni

Sebbene gli ambienti offrano molti vantaggi, introducono anche nuove limitazioni. Il fatto che gli ambienti siano un limite di isolamento significa che non è mai possibile avere risorse che fanno riferimento a risorse *tra* gli ambienti. Ad esempio, non è possibile creare un connettore personalizzato in un ambiente e quindi creare un flusso che usa tale connettore personalizzato in un ambiente diverso.

## <a name="use-the-default-environment"></a>Usa l'ambiente predefinito

L'ambiente **predefinito** è condiviso da tutti gli utenti e qualsiasi utente può creare flussi nell'ambiente **predefinito** .

> [!TIP]
> Se si è un utente di anteprima, tutti i flussi esistenti si trovano nell'ambiente predefinito. Un *utente di anteprima* è un utente che ha usato Microsoft flow prima del rilascio in disponibilità generale (GA).

## <a name="the-admin-center"></a>Interfaccia di amministrazione

Gli amministratori usano l'interfaccia di amministrazione per creare e gestire gli ambienti. Ecco i due modi per aprire il centro di amministrazione:

### <a name="option-1-select-settings"></a>Opzione 1: selezionare le impostazioni

1. Accedere a [Flow.Microsoft.com](https://flow.microsoft.com).
1. Selezionare l'ingranaggio impostazioni e scegliere interfaccia di **Amministrazione** nell'elenco:

   ![Impostazioni e portale di amministrazione](./media/environments-overview-admin/settings.png)
1. Si apre il centro di amministrazione.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Opzione 2: aprire admin.flow.microsoft.com

Passare a [admin.Flow.Microsoft.com](https://admin.flow.microsoft.com)e accedere con l'account aziendale.

## <a name="create-an-environment"></a>Creazione di un ambiente

1. Nell'interfaccia di [amministrazione di Microsoft Flow](https://admin.flow.microsoft.com)selezionare **ambienti**. Verranno visualizzati tutti gli ambienti esistenti: ![ambienti](./media/environments-overview-admin/environments-list.png)
2. Selezionare **nuovo ambiente** e quindi specificare le informazioni necessarie:


   |     Proprietà     |                                                 Descrizione                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Nome ambiente |              Immettere il nome dell'ambiente, ad esempio `Human Resources`o `Europe flows`.              |
   |      Area      | Scegliere il percorso in cui ospitare l'ambiente. Per ottenere prestazioni ottimali, usare un'area più vicina agli utenti. |
   | Tipo di ambiente |                  Scegliere un tipo di ambiente in base alla licenza: produzione o versione di valutazione.                   |

     ![Impostazioni dell'ambiente](./media/environments-overview-admin/new-environment-dialog.png)
3. Fare clic su **Crea ambiente**.
4. È ora disponibile un'opzione per **creare un database** o **ignorare**.
5. Se si sceglie di **creare il database**, verrà richiesta una **valuta** e una **lingua** per il database. Inoltre, è anche possibile scegliere di distribuire le app e i dati di esempio.

   ![impostazioni di configurazione del database](./media/environments-overview-admin/create-database-dialog2.png)


È ora possibile aggiungere utenti all'ambiente.

## <a name="manage-your-existing-environments"></a>Gestisci gli ambienti esistenti

1. Nell'interfaccia di [amministrazione di Microsoft Flow](https://admin.flow.microsoft.com)selezionare **ambienti**:

   ![voce di menu ambienti](./media/environments-overview-admin/select-environments.png)
1. Selezionare un ambiente per aprirne le proprietà.
1. Usare la scheda **Dettagli** per visualizzare informazioni aggiuntive su un ambiente, tra cui l'autore dell'ambiente, la posizione geografica e altro ancora:

   ![scheda Dettagli](./media/environments-overview-admin/open-environment.png)
1. Selezionare **sicurezza**.

    Se non è stato selezionato **Crea database** nei passaggi precedenti, in **ruoli ambiente**sono disponibili due opzioni: **amministratore dell'ambiente** e **autore dell'ambiente**:

    ![ruoli di amministratore](./media/environments-overview-admin/environment-roles.png)

    Un **produttore** può creare nuove risorse, ad esempio flussi, connessioni dati e gateway in un ambiente.

   > [!NOTE]
   > Un utente non deve necessariamente essere un **creatore** per *modificare* le risorse in un ambiente. Ogni autore determina chi può modificare le proprie risorse concedendo autorizzazioni agli utenti che non sono responsabili dell'ambiente.
   > 
   > 

    Un **amministratore** può creare criteri di prevenzione della perdita dei dati ed eseguire altre attività amministrative, quali la creazione di ambienti, l'aggiunta di utenti negli ambienti e l'assegnazione di privilegi di amministratore/autore.

   1. Selezionare il ruolo di **autore dell'ambiente** e quindi selezionare **utenti**: ![ruolo di autore](./media/environments-overview-admin/add-environment-maker.png)
   1. Immettere un nome, un indirizzo di posta elettronica o un gruppo di utenti che si vuole assegnare al ruolo di **autore** .
   1. Selezionare **Salva**.

1. In **sicurezza**selezionare **ruoli utente**:

    ![ruoli utente](./media/environments-overview-admin/security-user-roles.png)

    Vengono elencati tutti i ruoli esistenti, incluse le opzioni per modificare o eliminare il ruolo.

    Selezionare **nuovo ruolo** per creare un nuovo ruolo.
1. In **sicurezza**selezionare **set di autorizzazioni**:

    ![impostazione delle autorizzazioni](./media/environments-overview-admin/security-permission-set.png)

    Verranno visualizzati tutti i set di autorizzazioni e le opzioni esistenti per modificare o eliminare i ruoli.

    Selezionare **nuovo set di autorizzazioni** per creare un nuovo set di autorizzazioni.
1. Se si è scelto di **creare il database**, per archiviare i dati, questo database fa parte del Common Data Service. Quando si fa clic sulla scheda **sicurezza** , viene richiesto di passare al centro di **gestione dell'istanza di Dynamics 365** , in cui è possibile applicare la sicurezza basata sui ruoli.
impostazioni di sicurezza di ![Dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Selezionare l'utente dall'elenco di utenti nell'ambiente o nell'istanza.
  impostazioni di sicurezza di ![Dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Assegnare il ruolo all'utente.

   ![assegnare il ruolo all'utente](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Agli utenti o ai gruppi assegnati a questi ruoli di ambiente non viene automaticamente concesso l'accesso al database dell'ambiente (se esistente) e l'accesso deve essere concesso separatamente dal proprietario del database. 
>
>

### <a name="database-security"></a>Sicurezza del database
La possibilità di creare e modificare uno schema di database e di connettersi ai dati archiviati all'interno di un database di cui è stato effettuato il provisioning nell'ambiente di è controllata dai ruoli utente del database e dai set di autorizzazioni. È possibile gestire i ruoli utente e i set di autorizzazioni per il database dell'ambiente dalla sezione **ruoli utente** e **set di autorizzazioni** della scheda **sicurezza** . 

   ![assegnare il ruolo all'utente](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="can-i-move-a-flow-between-environments"></a>È possibile spostare un flusso tra ambienti?

Sì, i flussi possono essere esportati da un ambiente e importati in un altro ambiente.

### <a name="which-license-includes-the-common-data-service"></a>Quale licenza include la Common Data Service?

Solo Microsoft PowerApps piano 2 include i diritti per la creazione di database con l'Common Data Service. Tuttavia, tutti i piani a pagamento (Microsoft Flow piani 1 e 2 e i piani di Microsoft PowerApps 1 e 2) dispongono dei diritti per utilizzare il Common Data Service.

Scegli un piano adatto alle tue aspettative visitando la pagina dei [prezzi Microsoft Flow](https://flow.microsoft.com/pricing/) .

Per le risposte alle domande frequenti sulla fatturazione, vedere il documento [domande sulla fatturazione](billing-questions.md) .

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Il Common Data Service può essere usato all'esterno di un ambiente?

No. Il Common Data Service richiede un ambiente. Scopri di [più](common-data-model-intro.md) .

### <a name="what-regions-include-microsoft-flow"></a>Quali aree includono Microsoft Flow?

Microsoft Flow supporta la maggior parte delle aree supportate da Office 365, vedere [Panoramica delle aree](regions-overview.md) per altri dettagli.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Cosa è necessario per creare un ambiente personalizzato?

Tutti gli utenti con la licenza Microsoft Flow piano 2 possono creare i propri ambienti. Tutti gli utenti Microsoft Flow possono usare gli ambienti creati dagli amministratori del piano 2, ma non possono creare ambienti personalizzati.
