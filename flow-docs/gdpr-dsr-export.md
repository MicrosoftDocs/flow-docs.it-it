---
title: Richieste di esportazione del soggetto dei dati GDPR in Microsoft Flow | Microsoft Docs
description: Informazioni su come usare Microsoft Flow per rispondere alle richieste di esportazione del soggetto dei dati GPDR.
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
ms.date: 4/24/2018
ms.author: keweare
ms.openlocfilehash: 5b813bbd8ba9b4e5a778d9fa424704b61ed6dd31
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552066"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Risposta alle richieste di esportazione del soggetto dei dati GDPR per Microsoft Flow

Come parte dell'impegno di Microsoft a collaborare con i clienti per soddisfare i requisiti del Regolamento generale sulla protezione dei dati (GDPR), è stata redatta la documentazione per agevolare i preparativi. La documentazione non solo descrive cosa sta facendo Microsoft per prepararsi per il regolamento GDPR, ma include anche esempi delle misure che è possibile adottare sin da subito con Microsoft per il supporto della conformità a GDPR quando si usa Microsoft Flow.

## <a name="manage-export-requests"></a>Gestire le richieste di esportazione

Il *diritto alla portabilità dei dati* consente a un soggetto dei dati di richiedere una copia dei dati personali in formato elettronico (ovvero un "formato strutturato, di uso comune, leggibile da computer e interoperabile") che potrebbe essere trasmesso a un altro titolare del trattamento dei dati.

Microsoft Flow offre le esperienze seguenti per trovare o esportare i dati personali per un utente specifico:

* **Accesso ai siti Web:** accedere all'[interfaccia di amministrazione di PowerApps](https://admin.powerapps.com/) o all'[interfaccia di amministrazione di Microsoft Flow](https://admin.flow.microsoft.com/).

* **Accesso a PowerShell:**[cmdlet di PowerApps per l'amministrazione di PowerShell](https://go.microsoft.com/fwlink/?linkid=871804).

|**Dati dei clienti**|**Accesso ai siti Web**|**Accesso a PowerShell**|
|-----------------|------------------|-------------------|
|Log generati dal sistema|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|
|Cronologia di esecuzione|Portale per gli autori di Microsoft Flow||
|Flussi|Portale per gli autori di Microsoft Flow||
|Autorizzazioni per i flussi| Portale per gli autori di Microsoft Flow e Interfaccia di amministrazione di Microsoft Flow||
|Dettagli utente||Cmdlet per PowerApps|
|Connessioni|Portale per gli autori di Microsoft Flow|Cmdlet per PowerApps |
|Autorizzazioni per le connessioni|Portale per gli autori di Microsoft Flow|Cmdlet per PowerApps |
|Connettori personalizzati|Portale per gli autori di Microsoft Flow|Cmdlet per PowerApps |
|Autorizzazioni per i connettori personalizzati|Portale per gli autori di Microsoft Flow|Cmdlet per PowerApps |
|Gateway|Portale per gli autori di Microsoft Flow|Cmdlet di PowerShell per il gateway dati locale|
|Autorizzazioni per i gateway|Portale per gli autori di Microsoft Flow|Cmdlet di PowerShell per il gateway dati locale|

## <a name="export-a-flow"></a>Esportare un flusso

Un utente finale o un amministratore, con diritti di accesso al flusso, può esportare il flusso seguendo questa procedura:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com/).

1. Selezionare il collegamento **Flussi personali** e quindi selezionare il flusso da esportare.

1. Selezionare **Altro** e quindi selezionare **Esporta**.

    ![Esportare il flusso](./media/gdpr-dsr-export/export-flow.png)

1. Selezionare **Pacchetto (ZIP)**.

Il flusso sarà ora disponibile come pacchetto compresso. Per altre informazioni, vedere il post di blog su [come esportare e importare un flusso](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Esportare la cronologia di esecuzione

La cronologia di esecuzione include un elenco di tutte le esecuzioni di un flusso. Questi dati includono lo stato, l'ora di inizio, la durata e i dati di input/output per azioni e trigger del flusso.

Un utente finale o un amministratore, a cui è stato concesso l'accesso al flusso tramite l'interfaccia di amministrazione di Microsoft Flow, può seguire questa procedura per esportare questi dati:

1. Accedere a [Microsoft Flow](https://flow.microsoft.com/).
1. Selezionare il collegamento **Flussi personali** e quindi selezionare il flusso per il quale si vuole esportare la cronologia di esecuzione.
1. Nel riquadro **Cronologia esecuzioni** selezionare **Visualizza tutto**.

    ![Cronologia di esecuzione](./media/gdpr-dsr-export/run-history.png)

1. Selezionare **Scarica CSV**.

    ![Scarica CSV](./media/gdpr-dsr-export/download-csv.png)

La cronologia di esecuzione viene scaricata come file CSV in modo da poterlo aprire in Microsoft Excel o in un editor di testo e analizzare ulteriormente i risultati.

## <a name="export-a-users-activity-feed"></a>Esportare il feed attività di un utente

In [Microsoft Flow](https://flow.microsoft.com/) il feed attività mostra la cronologia di attività, errori e notifiche di un utente. Qualsiasi utente può visualizzare il feed attività personale seguendo questa procedura:

1. Accedere a [Microsoft Flow](http://flow.microsoft.com/), selezionare l'icona a forma di campanello nell'angolo superiore destro e quindi selezionare **Mostra tutta l'attività**.

    ![Visualizzare il feed attività](./media/gdpr-dsr-export/show-activity-feed.png)

1. Nella schermata **Attività** copiare i risultati e quindi incollarli in un editor di documenti, ad esempio Microsoft Word.

    ![Visualizzare il feed attività](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Esportare le connessioni di un utente

Le connessioni consentono ai flussi di connettersi ad API, applicazioni SaaS e altri sistemi di terze parti. Seguire questa procedura per visualizzare le connessioni:

1. Accedere a [Microsoft Flow](http://flow.microsoft.com/), selezionare l'icona a forma di ingranaggio in prossimità dell'angolo superiore destro e quindi selezionare **Connessioni**.

    ![Visualizzare le connessioni](./media/gdpr-dsr-export/show-connections.png)
1. Copiare i risultati e incollarli in un editor di documenti, ad esempio Microsoft Word.

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Esportare un elenco delle autorizzazioni di connessione dell'utente

Un utente può esportare le assegnazioni di ruolo per tutte le connessioni a cui ha accesso tramite la funzione Get-ConnectionRoleAssignment nei [cmdlet di PowerShell per PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

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

I connettori personalizzati integrano i connettori predefiniti e consentano la connettività ad altri sistemi SaaS, API e sistemi personalizzati. È possibile trasferire la proprietà di un connettore personalizzato o eliminarlo.

Seguire questa procedura per esportare un elenco di connettori personalizzati:

1. Passare a [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare l'icona a forma di **ingranaggio** delle impostazioni.
1. Selezionare **Connettori personalizzati**.
1. Copiare e incollare l'elenco di connettori personalizzati in un editor di testo, ad esempio Microsoft Word.

    ![Esportare connettori personalizzati](./media/gdpr-dsr-export/export-custom-connectors.png)

Oltre all'esperienza disponibile in Microsoft Flow, è possibile usare la funzione Get-Connector nei [cmdlet di PowerShell per PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) per esportare tutti i connettori personalizzati.

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

## <a name="export-a-users-custom-connector-permissions"></a>Esportare le autorizzazioni per i connettori personalizzati di un utente

Un utente può esportare tutte le autorizzazioni per i connettori personalizzati creati tramite la funzione Get-ConnectorRoleAssignment nei [cdmlet di PowerShell per PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

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

## <a name="export-approval-history"></a>Esportare la cronologia delle approvazioni

La cronologia delle approvazioni di Microsoft Flow raccoglie una registrazione cronologica delle approvazioni ricevute o inviate per un utente. Qualsiasi utente può visualizzare la cronologia delle approvazioni come indicato di seguito:

1. Accedere a [Microsoft Flow](http://flow.microsoft.com/), selezionare **Approvazioni** e quindi selezionare **Cronologia**.

    ![Visualizzare la cronologia delle approvazioni](./media/gdpr-dsr-export/view-approval-history.png)

1. Le approvazioni ricevute dall'utente vengono visualizzate in un elenco. Gli utenti possono visualizzare le approvazioni inviate selezionando la freccia in giù accanto a **Ricevute** e quindi selezionando **Inviate**.

    ![Visualizzare le approvazioni ricevute](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Esportare i dettagli utente
I dettagli utente offrono un collegamento tra un utente e un tenant specifico. L'amministratore può esportare queste informazioni chiamando il cmdlet **Get-AdminFlowUserDetails** e passando l'ID oggetto corrispondente all'utente.

Cmdlet di PowerShell per amministratori di PowerApps

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Esportare le impostazioni gateway
La procedura per rispondere alle richieste di esportazione oggetto dati per i gateway dati locali è disponibile [qui](https://docs.microsoft.com/en-us/power-bi/service-gateway-onprem#tenant-level-administration).

