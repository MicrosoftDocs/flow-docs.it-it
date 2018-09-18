---
title: Informazioni su come connettersi ai dati con le connessioni e i gateway dati locali | Microsoft Docs
description: Aggiungere o gestire le connessioni di SharePoint, SQL Server, OneDrive for Business, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive e altro
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
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bdfa1072bca2afc7c608a4dbf68b8f598dff89f1
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689112"
---
# <a name="manage-connections-in-microsoft-flow"></a>Gestire le connessioni in Microsoft Flow
Se si crea una connessione in Microsoft Flow è possibile accedere facilmente ai dati durante la creazione di un flusso. Microsoft Flow include le connessioni di uso comune tra cui SharePoint, SQL Server, Office 365, OneDrive for Business, Salesforce, Excel, Dropbox, Twitter e altro. Le connessioni sono condivise con PowerApps, quindi quando si crea una connessione in un solo prodotto, verrà visualizzata anche nell'altro.

Ad esempio, è possibile usare una connessione per eseguire queste attività:

* Aggiornare un elenco di SharePoint.
* Ottenere dati da un file di Excel nell'account di OneDrive for Business o Dropbox.
* Inviare posta elettronica in Office 365.
* Inviare un tweet.

È possibile creare una connessione in più scenari, ad esempio:

* Creazione di un [flusso da un modello](get-started-logic-template.md)
* Creazione di un [flusso da zero](get-started-logic-flow.md) o eseguire l'aggiornamento di un flusso esistente
* Creazione di una connessione direttamente nel [sito Web di Microsoft Flow][1]

Questo argomento illustra come gestire le connessioni nel [sito Web di Microsoft Flow][1].

## <a name="add-a-connection"></a>Aggiungere una connessione
1. Nel [sito Web di Microsoft Flow][1], accedere con l'account aziendale o dell'organizzazione.
2. Accanto all'angolo in alto a destra, selezionare l'icona dell'ingranaggio e quindi **Connessioni**.
   
    ![Selezionare le connessioni](./media/add-manage-connections/connections-menu.png)
3. Selezionare **Crea connessione**.
4. Nell'elenco di **Connessioni disponibili**, selezionare la connessione che si vuole impostare, ad esempio SharePoint.
5. Selezionare il pulsante **Creare una connessione**, quindi immettere le credenziali per configurare la connessione.

Quando la connessione è configurata, verrà elencata in **Connessioni personali**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Connettersi ai dati attraverso un gateway dati locale
Al momento della stesura di questo documento, SQL Server e SharePoint Server supportano il gateway dati locale. Per creare una connessione che usi un gateway:

1. Seguire i passaggi descritti in precedenza in questo argomento per aggiungere una connessione.
2. Nell'elenco di **Connessioni disponibili**, selezionare **SQL Server**, quindi selezionare la casella di controllo **Connetti tramite il gateway dati locale**.
   
    ![Selezionare il gateway](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > I gateway di dati di Microsoft SharePoint supportano il traffico HTTP, ma non il traffico HTTPS.
   > 
   > 
3. Fornire le credenziali di connessione, quindi selezionare il gateway che si vuole usare.
   
    Per altre informazioni, vedere [Gestire i gateway](gateway-manage.md) e [Informazioni sui gateway](gateway-reference.md).
   
    Quando la connessione è configurata, verrà elencata in **Connessioni personali**.

## <a name="delete-a-connection"></a>Eliminare una connessione
1. Andare alla pagina **Connessioni personali** e quindi selezionare l'icona del cestino per la connessione che si vuole eliminare.
   
    ![Eliminare la connessione](./media/add-manage-connections/delete-connection.png)
2. Selezionare **OK** per confermare che si vuole eliminare la connessione.
   
    ![Confermare l'eliminazione](./media/add-manage-connections/delete-confirmation.png)

Quando si elimina una connessione, questa viene rimossa anche da PowerApps e Microsoft Flow.

## <a name="update-a-connection"></a>Aggiornare una connessione
È possibile aggiornare una connessione che non funziona perché la password o i dettagli dell'account sono stati modificati.

1. Nella pagina **Connessioni**, selezionare il collegamento **Verifica password** per la connessione che si vuole aggiornare.
   
    ![Verificare la password](./media/add-manage-connections/verify-password.png)
2. Quando richiesto, aggiornare la connessione con le nuove credenziali.

Quando si aggiorna una connessione, viene aggiornata sia per PowerApps che per Microsoft Flow.

## <a name="troubleshoot-a-connection"></a>Risolvere un problema di connessione
A seconda dei criteri dell'organizzazione, potrebbe essere necessario usare lo stesso account per l'accesso a Microsoft Flow e la creazione di una connessione a SharePoint, Office 365 o OneDrive for Business.

Ad esempio, si potrebbe accedere a Microsoft Flow con *yourname@outlook.com* ma essere bloccati quando si prova a connettersi a SharePoint con *yourname@contoso.com*. È possibile invece accedere a Microsoft Flow con *yourname@contoso.com* e connettersi a SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
