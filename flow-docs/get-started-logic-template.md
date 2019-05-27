---
title: Creare un flusso da un modello | Microsoft Docs
description: Creare un flusso da uno dei diversi modelli incorporati.
services: ''
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
ms.author: anneta
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 52aae570f65eaae537f548e686f437592eb5ef03
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461236"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Creare un flusso da un modello in Microsoft Flow
Creare un flusso da uno dei numerosi modelli predefiniti che possono, ad esempio, inviare un messaggio Slack quando il proprio responsabile invia un messaggio di posta elettronica in Office 365.

**Nota**: [Creare un flusso da zero](get-started-logic-flow.md) se si ha già un processo presente e non è possibile trovare un modello adatto.

**Prerequisiti**

* Un account in [flow.microsoft.com](https://flow.microsoft.com)
* Un account Slack
* Credenziali di Office 365

## <a name="choose-a-template"></a>Scegliere un modello
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. In [flow.microsoft.com](https://flow.microsoft.com) selezionare **Modelli** nella barra di spostamento in alto.
2. Nella barra di ricerca digitare **Slack**, quindi fare clic sull'icona di ricerca.
3. Verranno visualizzati solo i modelli correlati a Slack, quindi è ora possibile selezionare **Invia un messaggio a Slack per ogni messaggio di posta elettronica del mio responsabile**.
   
    ![Nuova opzione nella barra di spostamento a sinistra](./media/get-started-logic-template/select-template.png)
4. Controllare che il modello consenta di eseguire l'operazione desiderata, quindi fare clic su **Use this template** (Utilizza questo modello).
5. Se non è stato eseguito l'accesso a Office o a Slack, selezionare **Accedi** e quindi seguire le istruzioni.
   
    ![Elenco delle connessioni richieste dal modello](./media/get-started-logic-template/confirm-connections.png)
6. Dopo aver controllato le connessioni, fare clic su **Continua**.
   
    Verrà visualizzato il flusso, con ogni azione indicata con una barra del titolo di colore arancione.
   
    ![Eventi e azioni predefiniti dal modello](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Personalizzare il flusso
1. Selezionare la barra del titolo di un evento per espanderla e quindi personalizzarlo (ad esempio, specificando un filtro nel messaggio di posta elettronica che interessa).
2. Le azioni che richiedono l'input da parte dell'utente verranno espanse automaticamente.
   
    Ad esempio, l'azione **Pubblica messaggio** viene espansa perché è necessario immettere un canale, ad esempio il proprio *\@nomeutente*. È anche possibile personalizzare il contenuto del messaggio. Per impostazione predefinita, il messaggio conterrà solo l'oggetto, ma è possibile includere altre informazioni.
   
    ![Specificare il canale per Slack](./media/get-started-logic-template/specify-keyword.png)
3. Nella parte superiore della schermata specificare un nome da assegnare al flusso e quindi selezionare **Crea flusso**.
4. Infine, se si è soddisfatti del flusso creato, selezionare **Fine**.
   
    ![Pulsante Fine](./media/get-started-logic-template/done.png)

A questo punto, quando il responsabile invia un messaggio di posta elettronica, si riceverà un messaggio di Slack che contiene le informazioni specificate.

## <a name="next-steps"></a>Passaggi successivi
* [Osservare il proprio flusso in azione](see-a-flow-run.md)
* [Pubblicare un modello personalizzato](publish-a-template.md)
* [Usare un modello per Common Data Service](common-data-model-intro.md)
* [Introduzione ai flussi del team](create-team-flows.md) e invio di inviti ad altri utenti per collaborare alla progettazione dei flussi.

