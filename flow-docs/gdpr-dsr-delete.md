---
title: Richieste di eliminazione del soggetto dei dati GDPR in Microsoft Flow | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di eliminazione del soggetto dei dati GPDR.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 70206e0ed6c2b59d0dfffa0c4608ba47e0fac1dc
ms.sourcegitcommit: ca875127f607034d7ef6a3fe270fc48e4f7eeee6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2018
ms.locfileid: "39175133"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Risposta alle richieste di eliminazione del soggetto dei dati GDPR per Microsoft Flow

Il "diritto alla cancellazione" con la rimozione dei dati personali dai dati del clienti di un'organizzazione è una protezione chiave nel regolamento GDPR. La rimozione dei dati personali include la rimozione di tutti i dati personali e dei log generati dal sistema, tranne le informazioni sul log di controllo.

Microsoft Flow consente agli utenti di creare flussi di lavoro di automazione che rappresentano una parte cruciale delle attività operative quotidiane dell'organizzazione. Quando un utente lascia l'organizzazione, un amministratore deve verificare manualmente determinati dati e risorse creati dall'utente e stabilire se eliminarli o meno. Esistono altri dati personali che vengono eliminati automaticamente ogni volta che l'account di un utente viene eliminato da Azure Active Directory.

La tabella seguente mostra i dati personali che vengono eliminati automaticamente e quelli che devono essere verificati ed eliminati manualmente da un amministratore:

|Verifica ed eliminazione manuali|Eliminazione automatica dopo l'eliminazione dell'utente da Azure Active Directory|
|------|------|
|Ambiente*|Log generati dal sistema|
|Autorizzazioni per l'ambiente**|Cronologia di esecuzione|
|Flussi|Feed attività|
|Autorizzazioni per i flussi|Gateway |
|Dettagli utente|Autorizzazioni per i gateway|
|Connessioni*||
|Autorizzazioni per le connessioni||
|Connettore personalizzato*||
|Autorizzazioni per i connettori personalizzati||

*Ognuna di queste risorse contiene record "Autore modifica" e "Modificato da" che includono dati personali. Per motivi di sicurezza, questi record vengono mantenuti fino a quando la risorsa viene eliminata.

**Per gli ambienti che includono un database Common Data Service per le app, le autorizzazioni per l'ambiente (ad esempio, quali utenti vengono assegnati ai ruoli Autore dell'ambiente e Amministratore dell'ambiente) vengono archiviate come record nel database di Common Data Service. Vedere [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Esecuzione di richieste DSR sui dati dei clienti di Common Data Service) per indicazioni su come rispondere alle richieste DSR per gli utenti che usano Common Data Service.

Per i dati e le risorse che richiedano una verifica manuale, Microsoft Flow offre le esperienze seguenti per individuare o modificare i dati personali per un utente specifico:

* **Accesso ai siti Web:** accedere all'[interfaccia di amministrazione di PowerApps](https://admin.powerapps.com/) o all'[interfaccia di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/)

* **Accesso a PowerShell:**[cmdlet di PowerShell per l'amministrazione di PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) 

Di seguito è riportata una suddivisione delle esperienze disponibili per un amministratore per l'eliminazione di ogni tipo di dati personali all'interno di ogni tipo di risorsa:

|Risorse contenenti dati personali|Accesso ai siti Web|Accesso a PowerShell|Eliminazione automatica|
|-----|----|----|----|
|Log generati dal sistema|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|||
|Ambiente|Interfaccia di amministrazione di Microsoft Flow|Cmdlet per PowerApps||
|Autorizzazioni per l'ambiente*|Interfaccia di amministrazione di Microsoft Flow|Cmdlet per PowerApps||
|Cronologia di esecuzione||| Eliminati tramite criteri di conservazione di 28 giorni|
|Feed attività |||Eliminati tramite criteri di conservazione di 28 giorni|
|Processi utente|| ||
|Flussi|Portale per gli autori di Microsoft Flow**|||
|Autorizzazioni per i flussi|Portale per gli autori di Microsoft Flow|||
|Dettagli utente||Cmdlet per PowerApps||
|Connessioni|Portale per gli autori di Microsoft Flow| ||
|Autorizzazioni per le connessioni|Portale per gli autori di Microsoft Flow| ||
|Connettore personalizzato|Portale per gli autori di Microsoft Flow| ||
|Autorizzazioni per i connettori personalizzati|Portale per gli autori di Microsoft Flow| ||
|Cronologia di approvazione|Portale per gli autori di Microsoft PowerApps*|||

*Con l'introduzione di Common Data Service per le app, se viene creato un database all'interno dell'ambiente, le autorizzazioni per l'ambiente e le autorizzazioni per le app basate su modello vengono archiviate come record all'interno dell'istanza del database di Common Data Service per le app. Vedere [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Esecuzione di richieste DSR sui dati dei clienti di Common Data Service) per indicazioni su come rispondere alle richieste DSR per gli utenti che usano Common Data Service.

**Un amministratore sarà in grado di accedere a queste risorse dal portale per gli autori di Microsoft Flow solo se gli è stato assegnato l'accesso dall'interfaccia di amministrazione di Microsoft Flow.

## <a name="manage-delete-requests"></a>Gestire le richieste di eliminazione

La procedura seguente descrive le funzioni amministrative esistenti per gestire le richieste di eliminazione per il regolamento GDPR. Questa procedura deve essere eseguita nell'ordine indicato di seguito.

> [!IMPORTANT]
> Per evitare il danneggiamento dei dati, seguire questi passaggi nell'ordine.
>
>

## <a name="list-and-re-assign-flows"></a>Elencare e assegnare nuovamente i flussi

Questi passaggi copiano i flussi esistenti per un utente che lascia l'organizzazione. Se si assegna una nuova proprietà alle copie, questi flussi possono continuare a supportare i processi aziendali esistenti. Quando si copiano questi flussi è importante eliminare i collegamenti a elementi di identificazione personale dell'utente precedente e stabilire nuove connessioni per consentire al flusso di connettersi ad altre API e applicazioni SaaS.

1. Accedere all'[interfaccia di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/) e quindi selezionare l'ambiente che contiene i flussi di proprietà dell'utente eliminato.

    ![Visualizzare gli ambienti](./media/gdpr-dsr-delete/view-environments.png)

1. Selezionare **Risorse** > **Flussi** e quindi selezionare il titolo per il flusso che si vuole riassegnare.

    ![Visualizzare i flussi](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Selezionare **Gestisci condivisione**.

    ![Gestire la condivisione](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Nel pannello **Condividi** visualizzato vicino al bordo destro aggiungersi come proprietario e quindi selezionare **Salva**.

    ![Condividere il flusso](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Accedere a [Microsoft Flow](https://flow.microsoft.com/), selezionare **Flussi personali** e quindi selezionare **Flussi del team**:

1. Selezionare i puntini di sospensione **(...)**  per il flusso che si vuole copiare e quindi selezionare **Salva con nome**.

    ![Salvare il flusso con un nome diverso](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configurare le connessioni come richiesto e quindi selezionare **Continua**.

1. Specificare un nuovo nome e quindi selezionare **Salva**.

    ![Creare una copia del flusso](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Questa nuova versione del flusso viene visualizzata in **Flussi personali**, in cui è possibile condividerla con altri utenti.

    ![Flussi del team](./media/gdpr-dsr-delete/team-flows.png)

1. Eliminare il flusso originale. A tale scopo selezionare i puntini di sospensione **(...)** , selezionare **Elimina** e quindi selezionare di nuovo **Elimina** quando richiesto. Questo passaggio rimuoverà anche gli identificatori personali sottostanti inclusi nelle dipendenze di sistema tra l'utente e Microsoft Flow.

    ![Conferma di eliminazione del flusso](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Abilitare la copia del flusso aprendo **Flussi personali** e quindi impostare il controllo di attivazione/disattivazione su **Attivato**.

    ![Abilitare il flusso](./media/gdpr-dsr-delete/toggle-on.png)

1. La copia esegue ora la stessa logica del flusso di lavoro della versione originale.

## <a name="delete-approval-history-from-microsoft-flow"></a>Eliminare la cronologia delle approvazioni da Microsoft Flow

 I dati di approvazione per Microsoft Flow vengono archiviati all'interno della versione precedente o corrente di Common Data Service per le app. All'interno di un'approvazione, le informazioni personali esistono sotto forma di assegnazioni di approvazione e commenti inclusi in una risposta di approvazione. Gli amministratori possono accedere a tali dati seguendo questa procedura:

1. Accedere a [PowerApps](https://web.powerapps.com/).

1. Selezionare **Dati** e quindi selezionare **Entità**.

1. Selezionare i puntini di sospensione **(...)**  per l'entità **Flow Approval** (Approvazione flusso) e quindi aprire i dati in Microsoft Excel.

1. In Microsoft Excel, cercare, filtrare e quindi eliminare i dati di approvazione come richiesto.

Vedere [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Esecuzione di richieste DSR sui dati dei clienti di Common Data Service) per indicazioni aggiuntive su come rispondere alle richieste DSR per gli utenti che usano Common Data Service.


## <a name="delete-connections-created-by-a-user"></a>Eliminare le connessioni create da un utente

Le connessioni vengono usate in combinazione con i connettori per stabilire la connettività con altre API e altri sistemi SaaS.  Le connessioni includono riferimenti all'utente che li ha creati e di conseguenza possono essere eliminate per rimuovere eventuali riferimenti all'utente.

Cmdlet di PowerShell per autori di PowerApps

Un utente può eliminare tutte le connessioni usando la funzione Remove-Connection dai [cmdlet di PowerShell per autori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```
## <a name="delete-the-users-permissions-to-shared-connections"></a>Eliminare le autorizzazioni dell'utente per le connessioni condivise

Cmdlet di PowerShell per autori di PowerApps

Un utente può eliminare tutte le relative assegnazioni di ruolo per le connessioni condivise usando la funzione Remove-ConnectionRoleAssignment nei [cmdlet di PowerShell per autori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

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
> Le assegnazioni di ruolo del proprietario non possono essere eliminate senza eliminare la risorsa di connessione.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Eliminare i connettori personalizzati creati dall'utente

I connettori personalizzati integrano i connettori predefiniti esistenti e consentono la connettività ad altri sistemi SaaS, API e sistemi personalizzati. I connettori personalizzati includono riferimenti all'utente che li ha creati e di conseguenza possono essere eliminati per rimuovere eventuali riferimenti all'utente.

Cmdlet di PowerShell per autori di PowerApps

Un utente può eliminare tutti i suoi connettori personalizzati usando la funzione Remove-Connector nei [cmdlet di PowerShell per autori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

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

Cmdlet di PowerShell per autori di PowerApps

Un utente può eliminare tutte le assegnazioni di ruolo per il connettore personalizzato condiviso con la funzione Remove-ConnectorRoleAssignment nei [cmdlet di PowerShell per autori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

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
> Le assegnazioni di ruolo del proprietario non possono essere eliminate senza eliminare la risorsa di connessione.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Eliminare o riassegnare tutti gli ambienti creati dall'utente

Un amministratore deve prendere due decisioni durante l'elaborazione di una richiesta di eliminazione DSR per un utente per ognuno degli ambienti creati dall'utente:

1. Se si determina che l'ambiente non viene usato da altri utenti nell'organizzazione, è possibile scegliere di eliminare l'ambiente
1. Se si determina che l'ambiente è ancora necessario, è possibile scegliere di non eliminare l'ambiente e aggiungere se stessi (o un altro utente nell'organizzazione) come Amministratore dell'ambiente.
> [!IMPORTANT]
> L'eliminazione di un ambiente eliminerà definitivamente tutte le risorse all'interno dell'ambiente, inclusi tutti i flussi, le app, le connessioni e così via. Assicurarsi quindi di verificare il contenuto di un ambiente prima dell'eliminazione.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Consentire l'accesso agli ambienti di un utente dall'interfaccia di amministrazione di Microsoft Flow

Un amministratore può concedere l'accesso amministrativo a un ambiente creato da un utente specifico dall'[interfaccia di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/). Per altre informazioni sull'amministrazione degli ambienti, vedere [Uso di ambienti in Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Eliminare le autorizzazioni dell'utente per tutti gli altri ambienti

È possibile assegnare autorizzazioni agli utenti in un ambiente (ad esempio Amministratore dell'ambiente, Autore dell'ambiente e così via), che vengono archiviate nel servizio Microsoft Flow come "assegnazione di ruolo".

Con l'introduzione di Common Data Service per le app, se viene creato un database all'interno dell'ambiente, queste "assegnazioni di ruolo" vengono archiviate come record all'interno dell'istanza del database di Common Data Service per le app.

Per altre informazioni sulla rimozione delle autorizzazioni dell'utente in un ambiente, vedere [Uso di ambienti in Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Eliminare le impostazioni gateway
La procedura per rispondere alle richieste di eliminazione oggetto dati per i gateway dati locali è disponibile [qui](https://docs.microsoft.com/en-us/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Eliminare i dettagli utente
I dettagli utente offrono un collegamento tra un utente e un tenant specifico. Prima di eseguire questo comando verificare che tutti i flussi per questo utente siano stati riassegnati e/o eliminati. Dopo aver completato questa operazione, un amministratore può eliminare i dettagli dell'utente chiamando il cmdlet **Remove-AdminFlowUserDetails** e passando l'ID oggetto corrispondente all'utente.


Cmdlet di PowerShell per amministratori di PowerApps
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Se un utente è ancora titolare di flussi individuali o del team, questo comando restituisce un errore. Per risolvere il problema eliminare tutti i flussi o i flussi del team rimanenti per l'utente ed eseguire di nuovo comando.
>
>
## <a name="delete-the-user-from-azure-active-directory"></a>Eliminare l'utente da Azure Active Directory
Dopo il completamento dei passaggi precedenti, il passaggio finale è l'eliminazione dell'account utente per Azure Active Directory seguendo la procedura descritta nella documentazione di Azure per le richieste dei soggetti interessati in base al GDPR, disponibile nel [Service Trust Portal di Office 365](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>Eliminare l'utente dal tenant non gestito
Se si appartiene a un tenant non gestito, è necessario eseguire un'operazione **Account close** (Chiusura account) nel [portale Work and School Privacy ](https://go.microsoft.com/fwlink/?linkid=873123) (Privacy per l'azienda e l'istituto di istruzione).

Per determinare se si appartiene a un tenant gestito o non gestito, seguire questa procedura:
1. Aprire l'URL seguente in un browser, assicurandosi di sostituire il proprio indirizzo di posta elettronica nell'URL: [ https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Se si appartiene a un **tenant non gestito** la risposta include `"IsViral": true`.

    {

     "Login": "foobar@unmanagedcontoso.com",

    "DomainName": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. In caso contrario, si appartiene a un tenant gestito.

