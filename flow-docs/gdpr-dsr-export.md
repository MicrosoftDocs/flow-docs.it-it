---
title: Richieste di esportazione del soggetto dei dati Microsoft Flow GDPR | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di esportazione del soggetto dei dati alle GPDR.
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 15eff70b8996e5ea130142a1c01699906e199642
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548186"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Risposta alle richieste di esportazione del soggetto dei dati GDPR per Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Nell'ambito del nostro impegno per collaborare con il tuo viaggio verso la Regolamento generale sulla protezione dei dati (GDPR), abbiamo sviluppato la documentazione per aiutarti a prepararti. La documentazione non solo descrive cosa si sta preparando per la GDPR, ma condivide anche esempi di passaggi che è possibile eseguire oggi con Microsoft per supportare la conformità GDPR quando si usa Microsoft Flow.

## <a name="manage-export-requests"></a>Gestire le richieste di esportazione

Il *diritto di portabilità dei dati* consente a un soggetto interessato di richiedere una copia dei dati personali in formato elettronico, ovvero un formato "strutturato, comunemente utilizzato, leggibile da computer e interoperabile", che può essere trasmesso a un altro controller di dati.

Microsoft Flow offre le seguenti esperienze per trovare o esportare i dati personali per un utente specifico:

* **Accesso al sito Web:** accedere all'interfaccia di [amministrazione di PowerApps](https://admin.powerapps.com/)o all'interfaccia di [amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/).

* **Accesso a PowerShell:**  [cmdlet di PowerShell per amministratori di PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

|**Dati del cliente**|**Accesso al sito Web**|**Accesso a PowerShell**|
|-----------------|------------------|-------------------|
|Log generati dal sistema|[Service Trust Portal di Office 365](https://servicetrust.microsoft.com/)|
|cronologia di esecuzione|Portale di Microsoft Flow Maker||
|Flussi|Portale di Microsoft Flow Maker||
|Autorizzazioni per il flusso| Portale di Microsoft Flow Maker e interfaccia di amministrazione di Microsoft Flow||
|Dettagli utente||Cmdlet PowerApps|
|Connessioni|Portale di Microsoft Flow Maker|Cmdlet PowerApps |
|Autorizzazioni per la connessione|Portale di Microsoft Flow Maker|Cmdlet PowerApps |
|Connettori personalizzati|Portale di Microsoft Flow Maker|Cmdlet PowerApps |
|Autorizzazioni connettore personalizzato|Portale di Microsoft Flow Maker|Cmdlet PowerApps |
|Gateway|Portale di Microsoft Flow Maker|Cmdlet di PowerShell per il gateway dati locale|
|Autorizzazioni del gateway|Portale di Microsoft Flow Maker|Cmdlet di PowerShell per il gateway dati locale|

## <a name="export-a-flow"></a>Esportare un flusso

Un utente finale o un amministratore, che ha concesso l'accesso al flusso, può esportare il flusso attenendosi alla procedura seguente:

1. Accedere [Microsoft Flow](https://flow.microsoft.com/).

1. Selezionare il collegamento **flussi personali** e quindi selezionare il flusso da esportare.

1. Seleziona **... Altro**, quindi selezionare **Esporta**.

    ![Esporta flusso](./media/gdpr-dsr-export/export-flow.png)

1. Selezionare **pacchetto (zip)** .

Il flusso sarà ora disponibile come pacchetto compresso. Per altre informazioni, vedere il post di Blog su [come esportare e importare un flusso](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Esporta cronologia di esecuzione

La cronologia di esecuzione include un elenco di tutte le esecuzioni che si sono verificate per un flusso. Questi dati includono lo stato del flusso, l'ora di inizio, la durata e i dati di input/output per i trigger e le azioni.

Un utente finale o un amministratore, a cui è stato concesso l'accesso al flusso tramite il centro di amministrazione di Microsoft Flow, può seguire questa procedura per esportare i dati:

1. Accedere [Microsoft Flow](https://flow.microsoft.com/).
1. Selezionare il collegamento **flussi personali** e quindi selezionare il flusso per il quale si vuole esportare la cronologia di esecuzione.
1. Nel riquadro **cronologia di esecuzione** selezionare **Visualizza tutto**.

    ![cronologia di esecuzione](./media/gdpr-dsr-export/run-history.png)

1. Selezionare **Scarica CSV**.

    ![Scarica CSV](./media/gdpr-dsr-export/download-csv.png)

La cronologia di esecuzione viene scaricata come file con estensione CSV in modo che sia possibile aprirla in Microsoft Excel o in un editor di testo e analizzare ulteriormente i risultati.

## <a name="export-a-users-activity-feed"></a>Esportare il feed attività di un utente

In [Microsoft Flow](https://flow.microsoft.com/)il feed attività Mostra la cronologia di un utente di attività, errori e notifiche. Qualsiasi utente può visualizzare il proprio feed attività attenendosi alla procedura seguente:

1. Accedere [Microsoft Flow](https://flow.microsoft.com/), selezionare l'icona a forma di campana nell'angolo in alto a destra, quindi selezionare **Mostra tutte le attività**.

    ![Mostra feed attività](./media/gdpr-dsr-export/show-activity-feed.png)

1. Nella schermata **Activity (attività** ) copiare i risultati e quindi incollarli in un editor di documenti, ad esempio Microsoft Word.

    ![Mostra feed attività](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Esportare le connessioni di un utente

Le connessioni consentono ai flussi di connettersi alle API, alle applicazioni SaaS e ad altri sistemi di terze parti. Per visualizzare le connessioni, attenersi alla procedura seguente:

1. Accedere [Microsoft Flow](https://flow.microsoft.com/), selezionare l'icona a forma di ingranaggio nell'angolo in alto a destra e quindi selezionare **connessioni**.

    ![Mostra connessioni](./media/gdpr-dsr-export/show-connections.png)
1. Copiare i risultati e quindi incollarli in un editor di documenti, ad esempio Microsoft Word.

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Esportare un elenco delle autorizzazioni di connessione di un utente

Un utente può esportare le assegnazioni di ruolo di connessione per tutte le connessioni a cui ha accesso tramite la funzione Get-Connectionroleassignment nei in [PowerApps PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Esportare i connettori personalizzati di un utente

I connettori personalizzati integrano i connettori predefiniti e consentono la connettività ad altre API, SaaS e sistemi personalizzati. È possibile trasferire la proprietà di un connettore personalizzato o eliminarlo.

Per esportare un elenco di connettori cliente, attenersi alla procedura seguente:

1. Passare a [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare l'icona dell' **ingranaggio** impostazioni.
1. Selezionare **connettori personalizzati**.
1. Copiare e incollare l'elenco di connettori personalizzati in un editor di testo, ad esempio Microsoft Word.

    ![Esportare connettori personalizzati](./media/gdpr-dsr-export/export-custom-connectors.png)

Oltre all'esperienza disponibile in Microsoft Flow, è possibile usare la funzione Get-Connector dai [cmdlet di PowerShell per PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) per esportare tutti i connettori personalizzati.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Esportare le autorizzazioni del connettore personalizzato di un utente

Un utente può esportare tutte le autorizzazioni del connettore personalizzato create tramite la funzione Get-Connectorroleassignment nei in [PowerApps PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Esporta cronologia di approvazione

Microsoft Flow la cronologia delle approvazioni acquisisce un record cronologico di approvazioni ricevute o inviate per un utente. Qualsiasi utente può visualizzare la cronologia delle approvazioni per:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com/), selezionare **approvazioni**e quindi selezionare **cronologia**.

    ![Visualizzare la cronologia delle approvazioni](./media/gdpr-dsr-export/view-approval-history.png)

1. Un elenco Mostra le approvazioni ricevute dall'utente. Gli utenti possono visualizzare le approvazioni inviate selezionando la freccia verso il basso accanto a **received** e quindi selezionando **sent**.

    ![Visualizza approvazioni ricevute](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Esporta dettagli utente
I dettagli dell'utente forniscono un collegamento tra un utente e un tenant specifico. Un amministratore può esportare queste informazioni chiamando il cmdlet **Get-AdminFlowUserDetails** e passando l'ID oggetto per l'utente.

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Esportare le impostazioni del gateway
La risposta alle richieste di esportazione del soggetto dati per i gateway dati locali è disponibile [qui](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

