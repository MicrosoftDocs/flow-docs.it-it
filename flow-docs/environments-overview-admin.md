---
title: Panoramica sugli ambienti per gli amministratori | Microsoft Docs
description: Uso, creazione e gestione degli ambienti in Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: f1c50e5d16d5b9fbbd3e6db3128947b0554e9a85
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="using-environments-within-microsoft-flow"></a>Uso di ambienti in Microsoft Flow
## <a name="benefits"></a>Vantaggi
Gli ambienti sono nuove funzionalità di Microsoft Flow e includono i seguenti vantaggi: 

* **Località dei dati**: gli ambienti possono essere creati in aree geografiche differenti, a cui sono vincolati. Quando si crea un flusso in un ambiente, tale flusso viene indirizzato a tutti i data center in quella posizione geografica, offrendo un miglioramento delle prestazioni. 
  
    Se gli utenti si trovano in Europa, creare e usare l'ambiente in quell'area geografica. Se, invece, gli utenti si trovano negli Stati Uniti, allora è opportuno creare e usare l'ambiente negli Stati Uniti. 
  
    Se si elimina l'ambiente, vengono eliminati anche tutti i flussi in tale ambiente. Questo vale per ogni elemento creato in tale ambiente, incluse le connessioni, i gateway, PowerApps e altro ancora.
* **Prevenzione della perdita di dati**: in qualità di amministratore, non si vuole che i flussi ottengano i dati da una posizione interna (ad esempio *OneDrive for Business*), per poi distribuirli pubblicamente (ad esempio su *Twitter*). La funzione di prevenzione della perdita di dati permette di controllare quali servizi possono essere usati in un criterio per i soli dati aziendali. 
  
    Ad esempio, è possibile aggiungere servizi di *SharePoint* e *OneDrive for Business* a un criterio per i soli dati aziendali. I flussi creati in questo ambiente possono usare questi servizi di *SharePoint* e *OneDrive for Business*. Sono disponibili solo i servizi aggiunti. 
  
  > [!NOTE]
  > La prevenzione della perdita di dati è disponibile con alcuni SKU di licenza, tra cui la licenza P2. 
  > 
  > 
* **Limite di isolamento per tutte le risorse**: qualsiasi flusso, gateway, connessione, connettore personalizzato e così via che si trova in questo ambiente specifico non esiste in nessun altro ambiente. 
* **Common Data Service**: si supponga di voler creare un flusso che inserisca i dati da qualche parte. Le opzioni disponibili sono:
  
  * Inserire i dati in un file Excel e archiviarlo in un account di archiviazione cloud, ad esempio OneDrive.
  * Creare un nuovo database SQL e archiviarvi i dati.
  * Usare Common Data Service per archiviare i dati.
    
    Ogni ambiente può avere da zero a un'archiviazione database per i flussi in Common Data Service. L'accesso a Common Data Service varia a seconda della licenza acquistata e non è incluso con la licenza gratuita.

## <a name="limitations"></a>Limitazioni
Sebbene gli ambienti offrano numerosi vantaggi, è opportuno ricordare che presentano anche nuove limitazioni. Il fatto che gli ambienti siano un limite di isolamento significa che non è mai possibile avere risorse che fanno riferimento ad altre risorse *tra* gli ambienti. Ad esempio, è impossibile creare un connettore personalizzato in un ambiente e creare un flusso che usi questo connettore personalizzato e un gateway in un ambiente differente.

Pertanto, è importante creare gli ambienti solo se necessario. La creazione di troppi ambienti complica la condivisione delle risorse nell'organizzazione da parte dell'utente.

## <a name="use-the-default-environment"></a>Usare l'ambiente predefinito
L'ambiente **Predefinito** è disponibile per tutti gli utenti e viene condiviso da tutti gli utenti. Tutti gli utenti possono creare i flussi in questo ambiente.

> [!TIP]
> Per gli utenti di anteprima, tutti i flussi esistenti si trovano nell'ambiente predefinito. Un *utente di anteprima* è qualcuno che ha iniziato a usare Microsoft Flow prima del suo rilascio in disponibilità generale. 
> 
> 

## <a name="use-the-administrator-center"></a>Usare il centro di amministrazione
Gli amministratori usano il centro di amministrazione per creare ambienti, aggiungervi gli utenti e altre operazioni analoghe. Ci sono due modi per aprire il centro di amministrazione:

#### <a name="option-1-select-settings"></a>Opzione 1: selezionare le impostazioni
1. Accedere a [flow.microsoft.com](https://flow.microsoft.com).
2. Selezionare Impostazioni (icona a forma di ingranaggio) e scegliere **Interfaccia di amministrazione** dall'elenco:  
   ![Impostazioni e portale amministratore](./media/environments-overview-admin/settings.png)
3. Viene aperto il centro di amministrazione.

#### <a name="option-2-open-adminflowmicrosoftcom"></a>Opzione 2: aprire admin.flow.microsoft.com
Andare al sito [admin.flow.microsoft.com](https://admin.flow.microsoft.com) e accedere con l'account aziendale. Viene aperto il centro di amministrazione.

## <a name="create-an-environment"></a>Creare un ambiente
1. Nel[Microsoft Flow admin center](https://admin.flow.microsoft.com) (Centro di amministrazione di Microsoft Flow) selezionare **Ambienti**. Vengono visualizzati tutti gli ambienti esistenti:  
   ![](./media/environments-overview-admin/environments-list.png)
2. Selezionare **Nuovo ambiente**. Immettere le informazioni seguenti:
   
   | Proprietà | Descrizione |
   | --- | --- |
   | Nome ambiente |Immettere il nome del proprio ambiente, ad esempio `Human Resources` o `Europe flows`. |
   | Area |Scegliere la posizione in cui ospitare l'ambiente. Per ottenere prestazioni ottimali, è consigliabile usare l'area geografica più vicina agli utenti. Ad esempio, se gli utenti del flusso si trovano a Londra, scegliere l'area Europa. Se, invece, gli utenti del flusso sono a New York, scegliere l'area Stati Uniti. |
3. Selezionare **Create an environment** (Crea un ambiente). Viene elencato il nuovo ambiente. 

Successivamente, aggiungere utenti all'ambiente.

## <a name="manage-your-existing-environments"></a>Gestire gli ambienti esistenti
1. Nel[Microsoft Flow admin center](https://admin.flow.microsoft.com) (Centro di amministrazione di Microsoft Flow) selezionare **Ambienti**:  
   ![](./media/environments-overview-admin/select-environments.png)  
2. Selezionare un ambiente per visualizzare le relative proprietà. 
3. In **Dettagli** sono incluse le informazioni aggiuntive sull'ambiente, tra cui l'utente che ha creato l'ambiente, la sua posizione geografica e altre proprietà:  
   ![](./media/environments-overview-admin/open-environment.png)
4. Selezionare **Sicurezza**. In **Ruoli ambiente**, sono disponibili due opzioni: **Amministratore** e **Maker (Autore)**:  
   
    ![](./media/environments-overview-admin/environment-roles.png)
   
    Un **autore** può creare nuove risorse in un ambiente, ad esempio flussi, connessioni dati e gateway. 
   
   > [!NOTE]
   > Un utente non deve essere un **Autore** per poter *modificare* le risorse in un ambiente, ma deve esserlo per poter creare risorse *ex-novo*. Ciascun creatore di risorse può determinare chi può modificare una risorsa e ha la facoltà di concedere l'autorizzazione di modifica agli utenti dell'ambiente che non sono autori.
   > 
   > 
   
    Un **amministratore** può creare i criteri per la prevenzione della perdita di dati e anche completare attività amministrative, ad esempio la creazione di ambienti, l'aggiunta di utenti in un ambiente e l'assegnazione di privilegi di amministratore/autore.  
   
   1. Selezionare il ruolo di **autore di ambiente** e quindi selezionare **Utenti**:  
      ![](./media/environments-overview-admin/add-environment-maker.png)
   2. Immettere un nome, un indirizzo di posta elettronica o un gruppo di utenti a cui assegnare il ruolo di autore. Quando si inizia a digitare, Intellisense comincia a elencare gli utenti o i gruppi che corrispondono al testo digitato. 
   3. Selezionare **Salva** per completare l'aggiunta di utenti. 
5. In **Sicurezza** selezionare **Ruoli utente**:  
    ![](./media/environments-overview-admin/security-user-roles.png)
   
    vengono elencati tutti i ruoli esistenti, incluse le opzioni per modificare o eliminare un ruolo. 
   
    Selezionare **Nuovo ruolo** per creare un nuovo ruolo. 
6. In **Sicurezza**, selezionare **Set di autorizzazioni**:  
    ![](./media/environments-overview-admin/security-permission-set.png)
   
    vengono elencati tutti i set di autorizzazioni esistenti, incluse le opzioni per modificare o eliminare un ruolo. 
   
    Selezionare **Nuovo set di autorizzazioni** per crearne uno nuovo. 
7. In **Database** è possibile scegliere di creare un database per archiviare i dati. Questo database fa parte di Common Data Service.

## <a name="commonly-asked-questions"></a>Domande frequenti
##### <a name="can-i-migrate-a-microsoft-flow-in-my-us-environment-to-a-europe-environment"></a>È possibile migrare un flusso di Microsoft Flow da un ambiente negli Stati Uniti a un ambiente in Europa?
No. Non è possibile spostare i flussi tra gli ambienti. È possibile ricreare il flusso in un altro ambiente.

##### <a name="which-license-includes-the-common-data-service"></a>Quale licenza include Common Data Service?
Soltanto Microsoft PowerApps Piano 2 include i diritti per creare i database con Common Data Service. Tuttavia, tutti i piani a pagamento (Microsoft Flow Piano 1 e 2 e Microsoft PowerApps Piano 1 e 2) dispongono dei diritti di usare Common Data Service.

I [prezzi di Flow](https://flow.microsoft.com/pricing/) possono essere utili per scegliere il piano più adatto.  

Anche le [domande sulla fatturazione](billing-questions.md) possono aiutare a esplorare alcune delle domande che vengono poste più comunemente. 

##### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>È possibile usare Common Data Service all'esterno di un ambiente?
No. Common Data Service necessita di un ambiente. [Altre informazioni](common-data-model-intro.md).

##### <a name="what-regions-include-microsoft-flow"></a>Quali aree include Microsoft Flow?
Microsoft Flow supporta la maggior parte delle aree geografiche supportate da Office 365; per altre informazioni consultare la [panoramica sulle aree geografiche](regions-overview.md).

##### <a name="what-is-needed-to-create-my-own-custom-environment"></a>Cosa serve per creare un ambiente personalizzato?
Tutti gli utenti con licenza di Microsoft Flow Piano 2 possono creare i propri ambienti, che vanno ad aggiungersi all'ambiente predefinito. Tutti gli utenti di Microsoft Flow, inclusi quelli di Office 365 e della versione gratuita, possono usare gli ambienti creati dagli amministratori del Piano 2, ma non sono autorizzati a creare i loro ambienti. 

