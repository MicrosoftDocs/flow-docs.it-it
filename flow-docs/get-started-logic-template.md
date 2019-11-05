---
title: Creare un flusso da un modello | Microsoft Docs
description: Creare un flusso da uno dei diversi modelli predefiniti.
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
ms.date: 02/07/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 874a942c4422fb402bc564609aff6ea06449ef78
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548247"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Creare un flusso da un modello in Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Creare un flusso da uno dei numerosi modelli predefiniti che possono, ad esempio, inviare un messaggio Slack quando il responsabile invia un messaggio di posta elettronica in Office 365.

**Nota:** [creare un flusso da zero](get-started-logic-flow.md) se si ha già un processo in mente e non si riesce a trovare un modello.

**Prerequisiti**

* Un account in [Flow.Microsoft.com](https://flow.microsoft.com)
* Un account Slack
* Credenziali di Office 365

## <a name="choose-a-template"></a>Scegliere un modello
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. In [Flow.Microsoft.com](https://flow.microsoft.com)selezionare **modelli** nella barra di spostamento superiore.
2. Nella barra di ricerca digitare **Slack**, quindi selezionare l'icona di ricerca.
3. Verranno visualizzati solo i modelli correlati a slack, quindi è ora possibile selezionare **Invia un messaggio in slack quando il mio responsabile mi invia un messaggio di posta elettronica**.
   
    ![Nuova opzione nella barra di spostamento a sinistra](./media/get-started-logic-template/select-template.png)
4. Verificare che il modello esegua le operazioni desiderate e quindi selezionare **utilizza questo modello**.
5. Se non è stato eseguito l'accesso a Office o Slack, selezionare **Accedi** e quindi seguire le istruzioni.
   
    ![Elenco di connessioni richieste dal modello](./media/get-started-logic-template/confirm-connections.png)
6. Dopo aver confermato le connessioni, selezionare **continua**.
   
    Viene visualizzato il flusso, che mostra ogni azione con una barra del titolo arancione.
   
    ![Eventi e azioni predefiniti dal modello](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Personalizzare il flusso
1. Selezionare la barra del titolo per un evento per espanderla, quindi personalizzarla (ad esempio, specificando un filtro per il messaggio di posta elettronica di interesse).
2. Le azioni che richiedono l'input dall'utente verranno espanse automaticamente.
   
    Ad esempio, l'azione **pubblica messaggio** viene espansa perché è necessario immettere un canale, ad esempio il *nome utente\@* . È inoltre possibile personalizzare il contenuto del messaggio. Per impostazione predefinita, il messaggio conterrà solo l'oggetto, ma è possibile includere altre informazioni.
   
    ![Specificare il canale per Slack](./media/get-started-logic-template/specify-keyword.png)
3. Nella parte superiore della schermata, specificare un nome per il flusso e quindi selezionare **Crea flusso**.
4. Infine, se si è soddisfatti del flusso **, selezionare fine**.
   
    ![Pulsante fine](./media/get-started-logic-template/done.png)

A questo punto, quando il responsabile invia un messaggio di posta elettronica, si riceverà un messaggio Slack contenente le informazioni specificate.

## <a name="next-steps"></a>Passaggi successivi
* [Controllare il flusso in azione](see-a-flow-run.md)
* [Pubblicare un modello personalizzato](publish-a-template.md)
* [Usare un modello per il Common Data Service](common-data-model-intro.md)
* [Inizia a usare i flussi del team](create-team-flows.md) e invita altri utenti a collaborare con te per progettare i flussi.

