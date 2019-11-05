---
title: Eseguire i flussi in base alle proprietà della posta elettronica | Microsoft Docs
description: Avviare un flusso in base a proprietà quali l'oggetto, l'indirizzo del mittente o l'indirizzo del destinatario di un messaggio di posta elettronica.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1dcb98d5bb99c9eaf2843ec75a8bdfaf03fa913
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544945"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Attivare un flusso in base alle proprietà di posta elettronica
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Usare il trigger **quando arriva un nuovo messaggio di posta elettronica** per creare un flusso che viene eseguito quando una o più delle seguenti proprietà di posta elettronica corrispondono ai criteri forniti:

| Proprietà | Quando usare |
| --- | --- |
| Cartella |Attivare un flusso ogni volta che i messaggi di posta elettronica arrivano in una cartella specifica. Questa proprietà può essere utile se si dispone di regole che instradano i messaggi di posta elettronica a cartelle diverse. |
| A |Attivare un flusso in base all'indirizzo a cui è stato inviato un messaggio di posta elettronica. Questa proprietà può essere utile se si riceve un messaggio di posta elettronica inviato a diversi indirizzi di posta elettronica nella stessa posta in arrivo. |
| Da |Attivare un flusso in base all'indirizzo di posta elettronica del mittente. |
| Importanza |Attivare un flusso in base alla priorità con cui sono stati inviati i messaggi di posta elettronica. È possibile inviare messaggi di posta elettronica con priorità alta, normale o bassa. |
| Con allegato |Attivare un flusso in base alla presenza di allegati nei messaggi di posta elettronica in arrivo. |
| Filtro oggetto |Ricercare la presenza di parole specifiche nell'oggetto di un messaggio di posta elettronica. Il flusso esegue quindi *azioni* basate sui risultati della ricerca. |

> [!IMPORTANT]
> Ogni [piano di Microsoft Flow](https://flow.microsoft.com/pricing/) include una quota di esecuzione. Controllare sempre le proprietà nel trigger del flusso, quando possibile. In questo modo si evita di usare inutilmente la quota di esecuzione. Se si seleziona una proprietà in una condizione, ogni esecuzione viene conteggiata in base alla quota di esecuzione del piano, anche se non viene soddisfatta la condizione di filtro definita. 

Ad esempio, se si seleziona un indirizzo di posta elettronica in una condizione, ogni esecuzione viene conteggiata in base alla quota di esecuzione del piano, anche se non è *dall'* indirizzo a cui *si è interessati* .
> 
> 

Nelle procedure dettagliate seguenti si controllano tutte le proprietà nel trigger all' **arrivo di un nuovo messaggio di posta elettronica** . Per altre informazioni, visita le [domande frequenti sulla fatturazione](billing-questions.md#what-counts-as-a-run) e la pagina dei [prezzi](https://ms.flow.microsoft.com/pricing/) .

## <a name="prerequisites"></a>Prerequisiti
* Un account con accesso a [Microsoft Flow](https://flow.microsoft.com)
* Un account Office 365 Outlook
* App per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows)
* Connessioni a Office, Outlook e al servizio di notifica push

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Attivare un flusso in base all'oggetto di un messaggio di posta elettronica
In questa procedura dettagliata viene creato un flusso che invia una notifica push al telefono cellulare se l'oggetto di un nuovo messaggio di posta elettronica contiene la parola "lotteria". Il flusso contrassegna quindi il messaggio di posta elettronica come *letto*.

>[!NOTE]
>Mentre questa procedura dettagliata invia una notifica push, è possibile usare qualsiasi altra azione che soddisfi le esigenze del flusso di lavoro. Ad esempio, è possibile archiviare il contenuto di posta elettronica in un altro repository, ad esempio fogli Google o un file di Microsoft Excel archiviato in Dropbox.

Ok, inizia subito:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Nella casella **filtro oggetto** immettere il testo usato dal flusso per filtrare i messaggi di posta elettronica in arrivo.
   
     In questo esempio si è interessati a tutti i messaggi di posta elettronica con la parola "lotteria" nell'argomento.
   
    ![Opzioni avanzate](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Immettere i dettagli per la notifica mobile che si vuole ricevere quando si riceve un messaggio di posta elettronica che corrisponde al **filtro oggetto** specificato in precedenza.
   
    ![Dettagli notifica](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Assegnare un nome al flusso. Quindi salvarlo selezionando **Crea flusso** nella parte superiore della pagina.
   
    ![Salva flusso](./media/email-triggers/email-triggers-subject-notification.png)

Congratulazioni! È ora possibile ricevere una notifica push ogni volta che si riceve un messaggio di posta elettronica contenente la parola "lotteria" nell'oggetto.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Attivare un flusso in base al mittente di un messaggio di posta elettronica
In questa procedura dettagliata viene creato un flusso che invia una notifica push al telefono cellulare se un nuovo messaggio di posta elettronica proviene da un mittente specifico (indirizzo di posta elettronica). Il flusso contrassegna anche il messaggio di posta elettronica come *letto*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Nella casella **da** immettere l'indirizzo di posta elettronica del mittente. 
   
     Il flusso esegue azioni su tutti i messaggi di posta elettronica inviati da questo indirizzo.
   
    ![Proprietà posta elettronica](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Immettere i dettagli per la notifica mobile che si vuole ricevere ogni volta che un messaggio arriva dall'indirizzo di posta elettronica immesso in precedenza.
   
    ![Dettagli notifica](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Assegnare un nome al flusso e quindi salvarlo selezionando **Crea flusso** nella parte superiore della pagina.
   
    ![Salva flusso](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Attiva un flusso quando i messaggi di posta elettronica arrivano in una cartella specifica
Se si dispone di regole che instradano la posta elettronica a cartelle diverse in base a determinate proprietà, ad esempio l'indirizzo, è possibile che si desideri questo tipo di flusso.

Iniziamo:

> [!NOTE]
> Se non si ha già una regola che instrada la posta elettronica a una cartella diversa dalla posta in arrivo, creare una regola di questo tipo e confermarne il funzionamento inviando un messaggio di posta elettronica di prova.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Selezionare la cartella a cui si desidera indirizzare i messaggi di posta elettronica specifici. Per visualizzare tutte le cartelle di posta elettronica, selezionare prima di tutto l'icona **Mostra selezione** , che si trova sul lato destro della casella **cartella** nella scheda all' **arrivo di un nuovo messaggio di posta elettronica** .
   
    ![Seleziona cartella](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Immettere i dettagli per la notifica mobile che si vuole ricevere all'arrivo di un messaggio di posta elettronica nella cartella selezionata in precedenza. Se non è già stato fatto, immettere le credenziali per il servizio di notifica.
   
    ![Dettagli notifica](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Assegnare un nome al flusso e quindi salvarlo selezionando **Crea flusso** nella parte superiore della pagina.
   
    ![Salva flusso](./media/email-triggers/email-triggers-7.png)

Testare il flusso inviando un messaggio di posta elettronica che viene indirizzato alla cartella selezionata in precedenza in questa procedura dettagliata.

