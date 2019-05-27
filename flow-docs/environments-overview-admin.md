---
title: Panoramica sugli ambienti per gli amministratori | Microsoft Docs
description: Uso, creazione e gestione degli ambienti in Microsoft Flow
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
ms.openlocfilehash: 43f6f36cc32ec40088bd9b4c61e2895a7de78589
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035042"
---
# <a name="using-environments-within-microsoft-flow"></a>Uso di ambienti in Microsoft Flow

## <a name="benefits"></a>Vantaggi

Gli ambienti offrono i vantaggi seguenti:

* **Località dei dati**: Gli ambienti possono essere creati in aree diverse e di cui vengono associati a tale località geografica. Quando si crea un flusso in un ambiente, tale flusso viene indirizzato a tutti i data center in quella posizione geografica, offrendo un miglioramento delle prestazioni.

    Se gli utenti si trovano in Europa, creare e usare l'ambiente in quell'area geografica. Se, invece, gli utenti si trovano negli Stati Uniti, creare e usare l'ambiente in quell'area geografica. 

    > [!IMPORTANT]
    > Se si elimina l'ambiente, vengono eliminati anche tutti i flussi in tale ambiente. Questo vale per ogni elemento creato in tale ambiente, incluse le connessioni, i gateway, PowerApps e altro ancora.
* **Prevenzione della perdita dei dati**: Come amministratore, non si desidera che i flussi ottengano i dati da una posizione interna (ad esempio *OneDrive for Business* o un elenco di SharePoint che contiene informazioni sulle retribuzioni) e poi distribuirli pubblicamente che i dati (ad esempio su * Twitter*). La prevenzione della perdita dei dati consente di controllare i servizi che possono condividere dati all'interno della distribuzione di Microsoft Flow.

    Ad esempio, è possibile aggiungere i servizi *SharePoint* e *OneDrive for Business* a un criterio per i soli dati aziendali. Qualsiasi flusso creato in questo ambiente può usare i servizi *SharePoint* e *OneDrive for Business*. Tuttavia, questi flussi non consentiranno la condivisione di dati con altri servizi non inclusi nel criterio per i soli dati aziendali.

  > [!NOTE]
  > La prevenzione della perdita di dati è disponibile con alcuni SKU di licenza, tra cui la licenza P2.

* **Limite di isolamento per tutte le risorse**: Tutti i flussi, gateway, connessioni, connettori personalizzati e così via si trovano in un ambiente specifico. e non esiste in nessun altro ambiente.
* **Common Data Service**: Ecco le opzioni disponibili se si desidera creare un flusso che inserisce dati in un servizio:

  * Inserire i dati in un file Excel e archiviarlo in un account di archiviazione cloud, ad esempio OneDrive.
  * Creare un database SQL e quindi archiviarvi i dati.
  * Usare Common Data Service per archiviare i dati.

    Ogni ambiente può avere al massimo un database per i flussi in Common Data Service. L'accesso a Common Data Service varia a seconda della licenza acquistata e Common Data Service non è incluso con la licenza gratuita.

## <a name="limitations"></a>Limitazioni

Sebbene gli ambienti offrano numerosi vantaggi, è opportuno ricordare che introducono anche nuove limitazioni. Il fatto che gli ambienti siano un limite di isolamento significa che non è mai possibile avere risorse che fanno riferimento a risorse *tra* ambienti diversi. Ad esempio, non è possibile creare un connettore personalizzato in un ambiente e poi creare un flusso che usa questo connettore personalizzato in un ambiente diverso.

## <a name="use-the-default-environment"></a>Usare l'ambiente predefinito

L'ambiente **predefinito** è condiviso da tutti gli utenti e qualsiasi utente può creare flussi nell'ambiente **predefinito**.

> [!TIP]
> Per gli utenti di anteprima, tutti i flussi esistenti si trovano nell'ambiente predefinito. Un *utente di anteprima* è qualcuno che ha iniziato a usare Microsoft Flow prima del suo rilascio in disponibilità generale.

## <a name="the-admin-center"></a>Interfaccia di amministrazione

Gli amministratori usano l'interfaccia di amministrazione per creare e gestire ambienti. Esistono due modi per aprire l'interfaccia di amministrazione:

### <a name="option-1-select-settings"></a>Opzione 1: selezionare impostazioni

1. Accedere a [flow.microsoft.com](https://flow.microsoft.com).
1. Selezionare Impostazioni (icona a forma di ingranaggio) e scegliere **Interfaccia di amministrazione** nell'elenco:

   ![Impostazioni e Portale amministratore](./media/environments-overview-admin/settings.png)
1. Viene aperto il centro di amministrazione.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Opzione 2: Aprire admin.flow.microsoft.com

Andare al sito [admin.flow.microsoft.com](https://admin.flow.microsoft.com) e accedere con l'account aziendale.

## <a name="create-an-environment"></a>Creare un ambiente

1. Nel[Microsoft Flow admin center](https://admin.flow.microsoft.com) (Centro di amministrazione di Microsoft Flow) selezionare **Ambienti**. Si noterà che tutti gli ambienti esistenti: ![Ambienti](./media/environments-overview-admin/environments-list.png)
2. Selezionare **Nuovo ambiente** e quindi specificare le informazioni richieste:


   |     Proprietà     |                                                 Descrizione                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Nome ambiente |              Immettere il nome del proprio ambiente, ad esempio `Human Resources` o `Europe flows`.              |
   |      Area      | Scegliere la posizione in cui ospitare l'ambiente. Per ottenere prestazioni ottimali, è consigliabile usare l'area geografica più vicina agli utenti. |
   | Tipo di ambiente |                  Scegliere un tipo di ambiente in base alle licenza: Prova o produzione.                   |

     ![Impostazioni dell'ambiente](./media/environments-overview-admin/new-environment-dialog.png)
3. Fare clic su **Crea ambiente**.
4. È ora possibile scegliere **Crea database** oppure **Ignora**.
5. Se si sceglie **Crea database** verrà richiesto di specificare **Valuta** e **Lingua** per il database. Inoltre, è anche possibile scegliere di distribuire app e dati di esempio.

   ![Impostazioni di configurazione del database](./media/environments-overview-admin/create-database-dialog2.png)


È ora possibile aggiungere utenti all'ambiente.

## <a name="manage-your-existing-environments"></a>Gestire gli ambienti esistenti

1. Nel[Microsoft Flow admin center](https://admin.flow.microsoft.com) (Centro di amministrazione di Microsoft Flow) selezionare **Ambienti**:

   ![Voce di menu Ambienti](./media/environments-overview-admin/select-environments.png)
1. Selezionare un ambiente per visualizzare le relative proprietà.
1. Usare la scheda **Dettagli** per visualizzare informazioni aggiuntive sull'ambiente, tra cui l'utente che ha creato l'ambiente, la sua posizione geografica e altro:

   ![Scheda Dettagli](./media/environments-overview-admin/open-environment.png)
1. Selezionare **Sicurezza**.

    Se non è stato selezionato **Create Database** nei passaggi precedenti, in **ruoli ambiente**, si sono disponibili due opzioni: **Amministratore dell'ambiente** e **creatore dell'ambiente**:

    ![Ruoli amministrativi](./media/environments-overview-admin/environment-roles.png)

    Un **autore** può creare nuove risorse in un ambiente, ad esempio flussi, connessioni dati e gateway.

   > [!NOTE]
   > Un utente non deve necessariamente essere un **autore** per *modificare* le risorse in un ambiente. Ogni autore determina chi può modificare le relative risorse dalla concessione di autorizzazioni agli utenti che non sono gli sviluppatori di ambienti.
   > 
   > 

    Un **amministratore** può creare i criteri per la prevenzione della perdita di dati ed eseguire altre attività amministrative, ad esempio la creazione di ambienti, l'aggiunta di utenti agli ambienti e l'assegnazione di privilegi di amministratore/autore.

   1. Selezionare il ruolo di **Autore dell'ambiente** e quindi selezionare **Utenti**: ![ruolo autore](./media/environments-overview-admin/add-environment-maker.png)
   1. Immettere un nome, un indirizzo di posta elettronica o un gruppo di utenti a cui assegnare il ruolo di **autore**.
   1. Selezionare **Salva**.

1. In **Sicurezza** selezionare **Ruoli utente**:

    ![Ruoli utente](./media/environments-overview-admin/security-user-roles.png)

    vengono elencati tutti i ruoli esistenti, incluse le opzioni per modificare o eliminare un ruolo.

    Selezionare **Nuovo ruolo** per creare un nuovo ruolo.
1. In **Sicurezza**, selezionare **Set di autorizzazioni**:

    ![Impostazione delle autorizzazioni](./media/environments-overview-admin/security-permission-set.png)

    Verranno visualizzati tutti i set di autorizzazioni e le opzioni esistenti per modificare o eliminare i ruoli.

    Selezionare **Nuovo set di autorizzazioni** per creare un nuovo set di autorizzazioni.
1. Se si è scelto **Crea database**, per archiviare i dati, il database fa parte di Common Data Service. Quando si fa clic sulla scheda **Sicurezza** verrà richiesto di passare al **Centro di gestione istanze di Dynamics 365** in cui è possibile applicare la sicurezza basata sui ruoli.
![Impostazioni di sicurezza di Dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Selezionare l'utente nell'elenco di utenti nell'ambiente/istanza.
  ![Impostazioni di sicurezza di Dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Assegnare il ruolo all'utente.

   ![Assegnare il ruolo all'utente](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Agli utenti o ai gruppi assegnati a questi ruoli di ambiente non viene concesso automaticamente l'accesso al database dell'ambiente (se presente) e devono ricevere le autorizzazioni di accesso separatamente da un proprietario del database. 
>
>

### <a name="database-security"></a>Sicurezza del database
La possibilità di creare e modificare uno schema di database e di connettersi ai dati archiviati all'interno di un database di cui è stato eseguito il provisioning nell'ambiente in uso dipende dai ruoli utente e dai set di autorizzazioni del database. È possibile gestire i ruoli utente e i set di autorizzazioni per il database dell'ambiente dalla sezione **Ruoli utente** e **Set di autorizzazioni** della scheda **Sicurezza**. 

   ![Assegnare il ruolo all'utente](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="can-i-move-a-flow-between-environments"></a>È possibile spostare un flusso tra ambienti?

Sì, i flussi possono essere esportati da un ambiente e importati in un altro ambiente.

### <a name="which-license-includes-the-common-data-service"></a>Quale licenza include Common Data Service?

Soltanto Microsoft PowerApps Piano 2 include i diritti per creare i database con Common Data Service. Tuttavia, tutti i piani a pagamento (Microsoft Flow Piano 1 e 2 e Microsoft PowerApps Piano 1 e 2) dispongono dei diritti di usare Common Data Service.

Scegliere un piano adatto alle specifiche esigenze, visitando la pagina dei [prezzi di Microsoft Flow](https://flow.microsoft.com/pricing/).

Vedere il documento con le [domande sulla fatturazione](billing-questions.md) per le risposte alle domande frequenti sulla fatturazione.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>È possibile usare Common Data Service all'esterno di un ambiente?

No. Common Data Service necessita di un ambiente. [Altre informazioni](common-data-model-intro.md).

### <a name="what-regions-include-microsoft-flow"></a>Quali aree include Microsoft Flow?

Microsoft Flow supporta la maggior parte delle aree geografiche supportata da Office 365. Per altri dettagli, vedere la [panoramica delle aree geografiche](regions-overview.md).

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Cosa serve per creare un ambiente personalizzato?

Tutti gli utenti con licenza di Microsoft Flow Piano 2 possono creare i propri ambienti. Tutti gli utenti di Microsoft Flow possono usare gli ambienti creati dagli amministratori del Piano 2, ma non sono autorizzati a creare i loro ambienti.
