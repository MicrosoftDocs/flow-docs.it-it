---
title: Descrivere un connettore personalizzato con Postman | Microsoft Docs
description: Creare un file Postman Collection per la registrazione di connettori personalizzati
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/28/2017
ms.author: sunayv
ms.openlocfilehash: fe98999ea307367c7f3b032974fef9be6ca3f388
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2018
---
# <a name="describe-a-custom-connector-with-postman"></a>Descrivere un connettore personalizzato con Postman
[Postman](https://www.getpostman.com/) è uno strumento che velocizza e semplifica lo sviluppo delle API. Questa esercitazione illustra come creare un file Postman Collection, che è quindi possibile usare per creare facilmente [connettori personalizzati](register-custom-api.md) in Microsoft Flow.

## <a name="prerequisites"></a>Prerequisiti
* Installare l'[app Postman](https://www.getpostman.com/apps).

## <a name="create-a-postman-collection"></a>Creare un file Postman Collection
Verrà ora creato un file Postman Collection per l'[API Analisi del testo](https://www.microsoft.com/cognitive-services/text-analytics-api) di Servizi cognitivi di Azure. Questa API identifica il linguaggio, la valutazione e le frasi chiave nel testo che le viene passato.

1. Il primo passaggio nella creazione di un file Postman Collection consiste nel creare una richiesta. Quando si crea la richiesta, è possibile impostare il verbo HTTP, l'URL della richiesta, query o parametri del percorso, intestazioni e corpo. Per altre informazioni, vedere [Invio di richieste](https://www.getpostman.com/docs/requests) nella documentazione di Postman. Per l'endpoint API Rileva lingua, impostare i valori come segue:
   
    ![Richiesta Postman](./media/postman-collection/request.png)
   
    Dettagli dei parametri e valori usati:
   
   | Parametro | Valore |
   | --- | --- |
   | Verbo |POST |
   | URL della richiesta |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | Parametri |numberOfLanguagesToDetect |
   | Autorizzazione |"No Auth" |
   | Intestazioni |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | Corpo |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. Fare clic su **Invia** per effettuare la richiesta e ottenere la risposta.
3. Fare clic su **Salva** per salvare la richiesta in un file Postman Collection.
   
    ![Risposta Postman](./media/postman-collection/request-response-save.png)
4. Fornire un **Nome richiesta** e **Descrizione richiesta** nella finestra di dialogo **Salva richiesta**. Usare quindi questi valori nel connettore personalizzato.
   
    ![Salva Postman Collection](./media/postman-collection/save-request-note.png)
   
    È anche possibile salvare la risposta alla richiesta. I connettori personalizzati supportano attualmente solo una singola risposta per ogni richiesta. Se si salvano più risposte per ogni richiesta, viene usata solo la prima.
   
    ![Salva risposta Postman](./media/postman-collection/save-response.png)
5. Continuare a compilare il file Postman Collection creando e salvando altre richieste e risposte.
6. Dopo aver completato la creazione del file Postman Collection per tutte le richieste e risposte, esportarlo.
   
    ![Esportazione Postman](./media/postman-collection/export.png)
7. Scegliere **Collection v1** come formato di esportazione.
   
    ![Esportazione Postman](./media/postman-collection/export2.png)

È ora possibile usare questo file Postman Collection per creare un connettore personalizzato in Microsoft Flow.

> [!IMPORTANT]
> Quando si crea un connettore personalizzato da un file Postman Collection, assicurarsi di rimuovere l'intestazione `Content-type` dalle azioni e dai trigger, perché verrà aggiunta automaticamente da Microsoft Flow. Le intestazioni di autenticazione, ad esempio `Ocp-Apim-Subscription-Key`, devono essere definite nella sezione **Security** e devono essere rimossi da azioni e trigger. 
> 
> 

Per altre informazioni, vedere [Registrare e usare i connettori personalizzati in Microsoft Flow](register-custom-api.md).

