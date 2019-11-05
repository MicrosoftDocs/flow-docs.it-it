---
title: Introduzione ai token di attivazione del pulsante | Microsoft Docs
description: Introduzione ai token per attivare i pulsanti per i flussi dei pulsanti Microsoft.
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
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1b439a972393f800ea550480b883945664e17e53
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547472"
---
# <a name="get-started-with-button-trigger-tokens"></a>Introduzione ai token di attivazione dei pulsanti
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-trigger-tokens"></a>Che cosa sono i token di attivazione del pulsante?
I token di attivazione del pulsante sono punti dati noti e disponibili per il dispositivo in cui è in esecuzione il flusso di un [pulsante](introduction-to-button-flows.md) . Questi token cambiano in base a fattori quali l'ora corrente o la posizione geografica del dispositivo in un determinato momento.  

Se, ad esempio, si esegue un flusso di un pulsante su uno smartphone, è probabile che il **telefono conosca la** data e l'ora della posizione corrente, nonché la data e l'indirizzo corrente. In questo contesto, l'ora, la data e l'indirizzo in cui si trova il telefono sono tutti determinati al momento dell'esecuzione del flusso del pulsante. Sono automaticamente disponibili per l'uso in tutti i flussi di pulsanti eseguiti sul dispositivo. È possibile usare questi token di trigger per creare flussi utili per ridurre al minimo le attività ripetitive, ad esempio fornire la propria posizione a un utente o tenere traccia del tempo impiegato per una particolare chiamata a un processo/servizio.

### <a name="list-of-button-trigger-tokens"></a>Elenco di token di attivazione dei pulsanti
Ecco l'elenco dei token di attivazione del pulsante che è possibile usare quando si creano i flussi di un pulsante.

| Parametro | Descrizione |
| --- | --- |
| Città |Città in cui si trova il dispositivo che esegue il flusso. |
| Paese/area geografica |Il paese/area geografica in cui si trova il dispositivo che esegue il flusso. |
| Indirizzo completo |Indirizzo completo in cui si trova il dispositivo che esegue il flusso. |
| Latitudine |La latitudine in cui si trova il dispositivo che esegue il flusso. |
| Longitudine |Longitudine in cui si trova il dispositivo che esegue il flusso. |
| PostalCode |Il codice postale in cui si trova il dispositivo che esegue il flusso. |
| Stato |Stato in cui si trova il dispositivo che esegue il flusso. |
| Strada |La strada in cui si trova il dispositivo che esegue il flusso. |
| timestamp |Tempo nell'area in cui si trova il dispositivo che esegue il flusso. |
| Data |Data nell'area in cui si trova il dispositivo che esegue il flusso. |
| Nome utente |Nome utente della persona che ha eseguito l'accesso al dispositivo che esegue il flusso. |
| Posta elettronica dell'utente |Indirizzo di posta elettronica della persona che ha eseguito l'accesso al dispositivo che esegue il flusso. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Creare un flusso di un pulsante che usa i token di attivazione
Quando si crea un pulsante, è possibile usare i token di attivazione per aggiungere funzionalità avanzate al pulsante.

In questa procedura dettagliata verrà creato un flusso di un pulsante in un dispositivo Android. Il flusso del pulsante userà i token di attivazione per inviare la data e l'indirizzo completo in un messaggio di posta elettronica di**lavoro da casa**al responsabile.

In questa procedura dettagliata verranno visualizzati screenshot da un dispositivo Android, ma l'esperienza è simile anche per i dispositivi iOS e Windows Phone.

### <a name="prerequisites"></a>Prerequisiti
* Un indirizzo di posta elettronica aziendale o dell'Istituto di istruzione o un [account Microsoft](https://account.microsoft.com/about?refd=www.microsoft.com) con accesso a Microsoft Flow.
* App per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).

Iniziamo:

1. Avviare Flow e selezionare **browse**   
   ](./media/introduction-to-button-trigger-tokens/1.png) token di attivazione del pulsante ![  
2. Selezionare il **messaggio Invia un messaggio di lavoro da casa al servizio di gestione** nella categoria **pulsante**   
   ](./media/introduction-to-button-trigger-tokens/2.png) token di attivazione del pulsante ![  
3. Selezionare **Usa questo modello**  
   ](./media/introduction-to-button-trigger-tokens/3.png) token di attivazione del pulsante ![  
4. Selezionare **modifica** nella scheda **Invia un messaggio di posta elettronica**  
   ](./media/introduction-to-button-trigger-tokens/3-5.png) token di attivazione del pulsante ![  
5. Toccare la casella di testo **oggetto** e immettere: " **Today-** " nella casella di testo dopo il testo "WFH". Si noti che quando si tocca la casella di testo, viene aperto anche un elenco di parametri/token. Nel passaggio successivo verrà usato uno di questi token per aggiungere la data all'oggetto del messaggio di posta elettronica.  
   ](./media/introduction-to-button-trigger-tokens/4.png) token di attivazione del pulsante ![  
6. Con il cursore ancora nella casella di testo oggetto, scorrere fino all'elenco **manuale** dei parametri e toccare **Data**. Si noti che il parametro date è ora presente nella casella di testo **Subject** :  
   ](./media/introduction-to-button-trigger-tokens/6.png) token di attivazione del pulsante ![  
7. Scorrere fino alla casella di testo **corpo** e toccare dopo il messaggio predefinito in modo che sia possibile includere token aggiuntivi.  
   ](./media/introduction-to-button-trigger-tokens/7.png) token di attivazione del pulsante ![  
8. Toccare il parametro **indirizzo completo** , quindi toccare **Crea** .  
   ](./media/introduction-to-button-trigger-tokens/8.png) token di attivazione del pulsante ![  
9. Toccare **fine**. Il flusso del pulsante è stato creato.  
   ](./media/introduction-to-button-trigger-tokens/9.png) token di attivazione del pulsante ![  

## <a name="run-the-button-flow"></a>Eseguire il flusso del pulsante
**Nota**: questo flusso del pulsante invierà il percorso corrente tramite posta elettronica.  

1. Toccare la categoria **pulsanti** nella parte inferiore della schermata. Viene visualizzato un elenco dei pulsanti per i quali si dispone delle autorizzazioni per l'utilizzo. Toccare il pulsante che rappresenta il flusso del pulsante appena creato:  
   ](./media/introduction-to-button-trigger-tokens/10.png) token di attivazione del pulsante ![  
2. Toccare **Consenti** per indicare che è OK per il flusso del pulsante per accedere alle informazioni sulla posizione del dispositivo:  
   ](./media/introduction-to-button-trigger-tokens/11.png) token di attivazione del pulsante ![  
3. Entro pochi istanti, si noti che il messaggio di posta elettronica è stato inviato al capo:  
   ![token di attivazione del pulsante](./media/introduction-to-button-trigger-tokens/12.png)  

Si è appena creato un flusso di un pulsante che usa i token di attivazione della data e dell'indirizzo completo. 

## <a name="next-steps"></a>Passaggi successivi
* [Condividere i flussi di un pulsante](share-buttons.md)
* [Informazioni sui flussi dei pulsanti](introduction-to-button-flows.md)
