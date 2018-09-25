---
title: Introduzione ai token di attivazione dei pulsanti | Microsoft Docs
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
ms.openlocfilehash: dc1b93553938221c3f1c995b63b984cfff913c06
ms.sourcegitcommit: ffed9f02092fbd19fc4108aee05dd40d1a2a3755
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711612"
---
# <a name="get-started-with-button-trigger-tokens"></a>Introduzione ai token per attivare i pulsanti
## <a name="what-are-button-trigger-tokens"></a>Cosa sono i token per attivare i pulsanti?
I token per attivare i pulsanti sono punti dati noti e disponibili per il dispositivo che esegue il [flusso di un pulsante](introduction-to-button-flows.md). Questi token cambiano in base a fattori come l'ora o la posizione geografica del dispositivo in un determinato momento.  

Ad esempio, se si esegue il flusso di un pulsante su uno smartphone, con ogni probabilità il **telefono conosce l'ora** della posizione corrente, nonché la data e l'indirizzo dell'utente. In questo contesto l'ora, la data e l'indirizzo in cui si trova il telefono sono determinati al momento dell'esecuzione del flusso del pulsante. Queste informazioni sono automaticamente disponibili per l'uso in tutti i flussi dei pulsanti eseguiti nel dispositivo. Questi token per l'attivazione consentono di generare flussi utili a ridurre al minimo le attività ripetitive, come la segnalazione della propria posizione a un altro utente o il rilevamento dei tempi dedicati a una chiamata di lavoro/assistenza.

### <a name="list-of-button-trigger-tokens"></a>Elenco dei token per attivare i pulsanti
Quello che segue è un elenco dei token di attivazione che è possibile usare durante la creazione dei flussi dei pulsanti.

| Parametro | Descrizione |
| --- | --- |
| Città |La città in cui si trova il dispositivo che esegue il flusso. |
| Paese/area geografica |Il paese o l'area geografica in cui si trova il dispositivo che esegue il flusso. |
| Indirizzo completo |L'indirizzo completo in cui si trova il dispositivo che esegue il flusso. |
| Latitudine |La latitudine in cui si trova il dispositivo che esegue il flusso. |
| Longitudine |La longitudine in cui si trova il dispositivo che esegue il flusso. |
| CAP |Il codice postale in cui si trova il dispositivo che esegue il flusso. |
| Stato |Lo stato in cui si trova il dispositivo che esegue il flusso. |
| Via |La via in cui si trova il dispositivo che esegue il flusso. |
| Timestamp |L'ora della località in cui si trova il dispositivo che esegue il flusso. |
| Data |La data della località in cui si trova il dispositivo che esegue il flusso. |
| Nome utente |Il nome utente della persona che ha eseguito l'accesso al dispositivo che esegue il flusso. |
| E-mail utente |L'e-mail della persona che ha eseguito l'accesso al dispositivo che esegue il flusso. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Creare il flusso di un pulsante che usa token per l'attivazione
Quando si crea un pulsante, è possibile usare i token per l'attivazione per aggiungere al pulsante funzionalità avanzate.

In questa procedura dettagliata viene creato il flusso di un pulsante in un dispositivo Android. Il flusso del pulsante userà token per l'attivazione per inviare la data e l'indirizzo completo al proprio superiore in un messaggio e-mail con oggetto "**Lavoro da casa**".

Le schermate incluse nella procedura dettagliata saranno prese da un dispositivo Android e Windows Phone, ma l'esperienza è simile anche sui dispositivi iOS.

### <a name="prerequisites"></a>Prerequisiti
* Un indirizzo di posta elettronica aziendale o dell'istituto di istruzione oppure un [account Microsoft](https://account.microsoft.com/about?refd=www.microsoft.com) che accede a Microsoft Flow.
* L'app per dispositivi mobili Microsoft Flow per [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

Ora si può iniziare:

1. Avviare Flow e selezionare **Sfoglia**   
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/1.png)  
2. Selezionare il servizio **Send a "Working from home today" email to your manager** (Invia un messaggio e-mail con oggetto "Oggi lavoro da casa" al tuo superiore) nella categoria **Button** (Pulsante)   
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/2.png)  
3. Selezionare **USE THIS TEMPLATE** (USA QUESTO MODELLO)  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/3.png)  
4. Selezionare **Edit** (Modifica) nella scheda **Send an email** (Invia un messaggio)  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. Toccare la casella di testo dell'**oggetto** e digitarvi " **oggi -** " dopo il testo "lavoro da casa". Quando si tocca la casella di testo, viene anche aperto un elenco di parametri/token. Uno di questi token servirà nel prossimo passaggio per aggiungere la data all'oggetto dell'e-mail.  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/4.png)  
6. Mantenendo il cursore nella casella di testo dell'oggetto, scorrere fino all'elenco dei parametri **manuali** e toccare **Date** (Data). A questo punto, il parametro della data si trova nella casella di testo dell'**oggetto**:  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/6.png)  
7. Scorrere fino alla casella del **corpo del messaggio** e toccare dopo il messaggio predefinito, in modo da poter includere token aggiuntivi.  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/7.png)  
8. Toccare il parametro relativo all'**indirizzo completo**, quindi toccare **Create** (Crea)  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/8.png)  
9. Toccare **Done** (Fine). Il flusso del pulsante è stato creato.  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Eseguire il flusso del pulsante
**NOTA**: il flusso di questo pulsante invierà nell'e-mail la posizione corrente.  

1. Toccare la categoria **Buttons** (Pulsanti) in fondo alla schermata. Verrà visualizzato un elenco dei pulsanti che si è autorizzati a usare. Toccare il pulsante che rappresenta il flusso del pulsante appena creato:  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/10.png)  
2. Toccare **ALLOW** (CONSENTI) per consentire al flusso del pulsante di accedere alle informazioni sulla posizione del dispositivo:  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/11.png)  
3. Dopo qualche istante l'e-mail sarà stata inviata al superiore:  
   ![token per attivare il pulsante](./media/introduction-to-button-trigger-tokens/12.png)  

A questo punto è stato creato il flusso di un pulsante che usa i token per l'attivazione relativi a data e indirizzo completo. 

## <a name="next-steps"></a>Passaggi successivi
* [Condividere i flussi dei pulsanti](share-buttons.md)
* [Informazioni sui flussi dei pulsanti](introduction-to-button-flows.md)
