---
title: Richieste di eliminazione del soggetto dei dati Microsoft Flow GDPR | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di eliminazione del soggetto dei dati alle GPDR.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 53e33d1c202b05854401573ca16040f17eb138c9
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548087"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Risposta alle richieste di eliminazione del soggetto dei dati GDPR per Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Il "diritto alla cancellazione" tramite la rimozione dei dati personali dai dati dei clienti di un'organizzazione è una protezione chiave nella GDPR. La rimozione dei dati personali include la rimozione di tutti i dati personali e i log generati dal sistema, eccetto le informazioni del log di controllo.

Microsoft Flow consente agli utenti di creare flussi di lavoro di automazione che rappresentano una parte fondamentale delle operazioni quotidiane dell'organizzazione. Quando un utente lascia l'organizzazione, è necessario che un amministratore riveda manualmente e determini se eliminare determinati dati e risorse creati dall'utente. Sono presenti altri dati personali che vengono eliminati automaticamente ogni volta che l'account dell'utente viene eliminato da Azure Active Directory.

Nella tabella seguente vengono indicati i dati personali che vengono eliminati automaticamente e i dati necessari a un amministratore per rivedere ed eliminare manualmente:

|Richiede la revisione e l'eliminazione manuali|Eliminato automaticamente quando l'utente viene eliminato da Azure Active Directory|
|------|------|
|Ambiente|Log generati dal sistema|
|Autorizzazioni per l'ambiente * *|cronologia di esecuzione|
|Flussi|Feed attività|
|Autorizzazioni per il flusso|Gateway |
|Dettagli utente|Autorizzazioni del gateway|
|Connessioni||
|Autorizzazioni per la connessione||
|Connettore personalizzato *||
|Autorizzazioni connettore personalizzato||

\* Ognuna di queste risorse contiene record "creato da" e "modificato da" che includono dati personali. Per motivi di sicurezza, questi record vengono conservati finché la risorsa non viene eliminata.

\* * Per gli ambienti che includono un database di Common Data Service, le autorizzazioni di ambiente (ad esempio gli utenti assegnati ai ruoli di amministratore e autore dell'ambiente) vengono archiviate come record nel database di Common Data Service. Per indicazioni su come rispondere a DSRs per gli utenti che usano il Common Data Service, vedere [esecuzione di DSRs su dati del cliente Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251).

Per i dati e le risorse che richiedono una revisione manuale, Microsoft Flow offre le seguenti esperienze per trovare o modificare i dati personali per un utente specifico:

* **Accesso al sito Web:** accedere all'interfaccia di [amministrazione di PowerApps](https://admin.powerapps.com/)o all'interfaccia di [amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/)

* **Accesso a PowerShell:**  [cmdlet di PowerShell per amministratori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) 

Ecco la suddivisione delle esperienze disponibili per un amministratore per eliminare ogni tipo di dati personali all'interno di ogni tipo di risorsa:

|Risorse contenenti dati personali|Accesso al sito Web|Accesso a PowerShell|Eliminazione automatica|
|-----|----|----|----|
|Log generati dal sistema|[Service Trust Portal di Office 365](https://servicetrust.microsoft.com/)|||
|Ambiente|Interfaccia di amministrazione di Microsoft Flow|Cmdlet PowerApps||
|Autorizzazioni per l'ambiente *|Interfaccia di amministrazione di Microsoft Flow|Cmdlet PowerApps||
|cronologia di esecuzione||| Eliminati con i criteri di conservazione di 28 giorni|
|Feed attività |||Eliminati con i criteri di conservazione di 28 giorni|
|Processi utente|| ||
|Flussi|Portale di Microsoft Flow Maker * *|||
|Autorizzazioni per il flusso|Portale di Microsoft Flow Maker|||
|Dettagli utente||Cmdlet PowerApps||
|Connessioni|Portale di Microsoft Flow Maker| ||
|Autorizzazioni per la connessione|Portale di Microsoft Flow Maker| ||
|Connettore personalizzato|Portale di Microsoft Flow Maker| ||
|Autorizzazioni connettore personalizzato|Portale di Microsoft Flow Maker| ||
|Cronologia delle approvazioni|Portale di Microsoft PowerApps Maker *|||

\* Con l'introduzione del Common Data Service, se viene creato un database all'interno dell'ambiente, le autorizzazioni dell'ambiente e le autorizzazioni per le app basate su modelli vengono archiviate come record all'interno dell'istanza di database Common Data Service. Per indicazioni su come rispondere a DSRs per gli utenti che usano il Common Data Service, vedere [esecuzione di DSRs su dati del cliente Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251).

\*\* un amministratore sarà in grado di accedere a queste risorse solo dal portale Microsoft Flow Maker se all'amministratore è stato assegnato l'accesso dall'interfaccia di amministrazione di Microsoft Flow.

## <a name="manage-delete-requests"></a>Gestisci richieste di eliminazione

La procedura seguente descrive come esistono le funzioni amministrative per gestire le richieste di eliminazione per GDPR. Questi passaggi devono essere eseguiti nell'ordine indicato di seguito.

> [!IMPORTANT]
> Per evitare il danneggiamento dei dati, attenersi alla seguente procedura nell'ordine.
>
>

## <a name="list-and-re-assign-flows"></a>Elencare e riassegnare i flussi

Questi passaggi copiano i flussi esistenti per un utente di cui è stato ripartito. Se si assegna una nuova proprietà alle copie, questi flussi possono continuare a supportare i processi aziendali esistenti. La copia di questi flussi è importante per eliminare i collegamenti degli identificatori personali all'utente che ha avviato la separazione e le nuove connessioni devono essere stabilite per la connessione del flusso ad altre API e applicazioni SaaS.

1. Accedere al [centro di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/), quindi selezionare l'ambiente che contiene i flussi di proprietà dell'utente eliminato.

    ![Visualizza ambienti](./media/gdpr-dsr-delete/view-environments.png)

1. Selezionare **risorse**, > **flussi**, quindi selezionare il titolo del flusso che si vuole riassegnare.

    ![Visualizza flussi](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Selezionare **Gestisci condivisione**.

    ![Gestisci condivisione](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Nel pannello **Condividi** visualizzato vicino al bordo destro aggiungere se stessi come proprietario, quindi selezionare **Salva**.

    ![Flusso di condivisione](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Accedere [Microsoft Flow](https://flow.microsoft.com/), selezionare **flussi personali**e quindi selezionare flussi del **Team**.

1. Selezionare i puntini di sospensione **(...)** per il flusso che si vuole copiare e quindi selezionare **Salva con nome**.

    ![Salva con nome per il flusso](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configurare le connessioni come richiesto e quindi selezionare **continue (continua**).

1. Specificare un nuovo nome e quindi fare clic su **Salva**.

    ![Crea copia di flusso](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Questa nuova versione del flusso viene visualizzata in **flussi personali**, dove è possibile condividerla con altri utenti, se lo si desidera.

    ![Flussi del team](./media/gdpr-dsr-delete/team-flows.png)

1. Eliminare il flusso originale selezionando i puntini di sospensione **(...)** , selezionare **Elimina**, quindi selezionare di nuovo **Elimina** quando richiesto. Con questo passaggio verranno rimossi anche gli identificatori personali sottostanti inclusi nelle dipendenze di sistema tra l'utente e Microsoft Flow.

    ![Conferma di eliminazione del flusso](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Abilitare la copia del flusso aprendo i **flussi personali** e quindi attivando il **controllo di attivazione**/disattivazione.

    ![Abilita flusso](./media/gdpr-dsr-delete/toggle-on.png)

1. La copia esegue ora la stessa logica del flusso di lavoro della versione originale.

## <a name="delete-approval-history-from-microsoft-flow"></a>Elimina la cronologia delle approvazioni da Microsoft Flow

 I dati di approvazione per Microsoft Flow vengono archiviati nella versione corrente o precedente di Common Data Service. All'interno di un'approvazione, le informazioni personali esistono sotto forma di assegnazioni di approvazione e commenti inclusi in una risposta di approvazione. Gli amministratori possono accedere a tali dati attenendosi alla procedura seguente:

1. Accedere a [PowerApps](https://web.powerapps.com/).

1. Selezionare **dati**, quindi selezionare **entità**.

1. Selezionare i puntini di sospensione **(...)** per l'entità **approvazione flusso** , quindi aprire i dati in Microsoft Excel.

1. In Microsoft Excel, cercare, filtrare e quindi eliminare i dati di approvazione come richiesto.

Per altre istruzioni su come rispondere a DSRs per gli utenti che usano il Common Data Service, vedere [esecuzione di DSRs su dati del cliente Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251).


## <a name="delete-connections-created-by-a-user"></a>Elimina le connessioni create da un utente

Le connessioni vengono usate insieme ai connettori per stabilire la connettività con altre API e sistemi SaaS.  Le connessioni includono riferimenti all'utente che le ha create e, di conseguenza, possono essere eliminate per rimuovere eventuali riferimenti all'utente.

Cmdlet di PowerShell per PowerApps Maker

Un utente può eliminare tutte le relative connessioni usando la funzione Remove-Connection dei cmdlet di [PowerShell per PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Elimina le autorizzazioni dell'utente per le connessioni condivise

Cmdlet di PowerShell per PowerApps Maker

Un utente può eliminare tutte le assegnazioni di ruolo di connessione per le connessioni condivise Remove-Connectionroleassignment nei Function nei [cmdlet di PowerShell per PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Non è possibile eliminare le assegnazioni di ruolo di proprietario senza eliminare la risorsa di connessione.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Elimina i connettori personalizzati creati dall'utente

I connettori personalizzati integrano i connettori predefiniti esistenti e consentono la connettività ad altre API, SaaS e sistemi personalizzati. I connettori personalizzati includono riferimenti all'utente che li ha creati e di conseguenza possono essere eliminati per rimuovere eventuali riferimenti all'utente.

Cmdlet di PowerShell per PowerApps Maker

Un utente può eliminare tutti i connettori personalizzati con la funzione Remove-Connector nei [cmdlet di PowerShell per PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Cmdlet di PowerShell per amministratori di PowerApps
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Eliminare le autorizzazioni dell'utente per i connettori personalizzati condivisi

Cmdlet di PowerShell per PowerApps Maker

Un utente può eliminare tutte le assegnazioni di ruolo del connettore per il connettore personalizzato condiviso con la funzione Remove-Connectorroleassignment nei nei [cmdlet di PowerShell per PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

Cmdlet di PowerShell per amministratori di PowerApps
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Non è possibile eliminare le assegnazioni di ruolo di proprietario senza eliminare la risorsa di connessione.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Eliminare o riassegnare tutti gli ambienti creati dall'utente

In qualità di amministratore, è necessario prendere due decisioni quando si elabora una richiesta di eliminazione DSR per un utente per ogni ambiente creato dall'utente:

1. Se si determina che l'ambiente non viene usato da altri utenti nell'organizzazione, è possibile scegliere di eliminare l'ambiente
1. Se si determina che l'ambiente è ancora necessario, è possibile scegliere di non eliminare l'ambiente e aggiungere se stessi (o un altro utente dell'organizzazione) come amministratore dell'ambiente.
> [!IMPORTANT]
> L'eliminazione di un ambiente eliminerà definitivamente tutte le risorse all'interno dell'ambiente, incluse tutte le app, i flussi, le connessioni e così via. esaminare quindi il contenuto di un ambiente prima dell'eliminazione.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Concedere l'accesso agli ambienti di un utente dall'interfaccia di amministrazione di Microsoft Flow

Un amministratore può concedere l'accesso amministrativo a un ambiente creato da un utente specifico dall'interfaccia di [amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/). Per ulteriori informazioni sugli ambienti di amministrazione, passare a [utilizzo di ambienti all'interno Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Elimina le autorizzazioni dell'utente per tutti gli altri ambienti

Agli utenti possono essere assegnate autorizzazioni (ad esempio amministratore dell'ambiente, autore dell'ambiente e così via) in un ambiente, archiviato nel servizio Microsoft Flow come "assegnazione di ruolo".

Con l'introduzione del Common Data Service, se viene creato un database all'interno dell'ambiente, queste "assegnazioni di ruolo" vengono archiviate come record all'interno dell'istanza di database Common Data Service.

Per ulteriori informazioni sulla rimozione dell'autorizzazione di un utente in un ambiente, passare a [using environments in Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Elimina impostazioni gateway

La risposta alle richieste di eliminazione del soggetto dati per i gateway dati locali è disponibile [qui](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Elimina dettagli utente

I dettagli dell'utente forniscono un collegamento tra un utente e un tenant specifico. Prima di eseguire questo comando, verificare che tutti i flussi per questo utente siano stati riassegnati e/o eliminati. Una volta completata l'operazione, un amministratore può eliminare i dettagli dell'utente chiamando il cmdlet **Remove-AdminFlowUserDetails** e passando l'ID oggetto per l'utente.

Cmdlet di PowerShell per amministratori di PowerApps
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Se un utente è ancora proprietario di flussi individuali o del team, questo comando restituirà un errore. Per risolvere il problema, eliminare tutti i flussi rimanenti o i flussi del team per questo utente ed eseguire di nuovo il comando.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Elimina l'utente dalla Azure Active Directory

Una volta completati i passaggi precedenti, il passaggio finale consiste nell'eliminare l'account dell'utente per Azure Active Directory attenendosi alla procedura descritta nella documentazione relativa alla richiesta di un oggetto dati di Azure GDPR che si trova nel [portale di attendibilità del servizio Office 365](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>Eliminare l'utente dal tenant non gestito

Nel caso in cui l'utente sia membro di un tenant non gestito, è necessario eseguire un'azione di **chiusura dell'account** dal portale per la privacy aziendale e dell' [Istituto di istruzione](https://go.microsoft.com/fwlink/?linkid=873123).

Per determinare se si è un utente di un tenant gestito o non gestito, eseguire le azioni seguenti:

1. Aprire l'URL seguente in un browser, assicurandosi di sostituire l'indirizzo di posta elettronica nell'URL:[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Se si è membri di un **tenant non gestito** , verrà visualizzato un `"IsViral": true` nella risposta.

    {

     "Login": "foobar@unmanagedcontoso.com",

    "DomainName": "unmanagedcontoso.com",

    "Virale": **true**,
    
    }

1. In caso contrario, si appartiene a un tenant gestito.
