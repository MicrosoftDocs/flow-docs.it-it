---
title: Configurare i flussi dell'interfaccia utente nel dispositivo | Microsoft Docs
description: Configurare i flussi dell'interfaccia utente nel dispositivo
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9e5029189df9807ba727efbe377392f87ef20884
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589690"
---
# <a name="set-up-ui-flows"></a>Configurare i flussi dell'interfaccia utente

[Questo argomento è una versione preliminare della documentazione ed è soggetto a modifiche.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Prima di poter usare il dispositivo per creare flussi dell'interfaccia utente, è necessario verificare che soddisfi i requisiti descritti qui.

> [!TIP]
> Prima di creare un flusso dell'interfaccia utente, controllare l' [elenco dei connettori](https://flow.microsoft.com/connectors/) per verificare se l'applicazione che si vuole automatizzare dispone già di un connettore. In tal caso, è consigliabile creare un flusso anziché un flusso dell'interfaccia utente. È anche possibile creare [un connettore personalizzato](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Prerequisiti

- Un piano di risparmio energia automatico a [pagamento](https://flow.microsoft.com/pricing/) o di [valutazione](https://flow.microsoft.com/manage/) .

- Un account aziendale o dell'Istituto di istruzione per accedere sia a Power automatici che al dispositivo Windows.

- Un dispositivo che esegue Windows 10, Windows Server 2016 o Windows Server 2019.
- Una tastiera US (QWERTY) collegata.

- La [prossima versione di Microsoft Edge](https://www.microsoftedgeinsider.com) o Google Chrome.

- Un [ambiente](https://docs.microsoft.com/power-platform/admin/environments-overview) con un [database Common Data Service](https://docs.microsoft.com/power-platform/admin/create-database).

> [!IMPORTANT]
> I flussi dell'interfaccia utente sono attualmente in fase di implementazione tra le aree. Se la funzionalità di anteprima non è visibile o non è possibile creare nuovi flussi dell'interfaccia utente, riprovare più tardi.


## <a name="limitations"></a>Limitazioni

Flussi dell'interfaccia utente (anteprima) è disponibile in lingua inglese.

Gli elementi seguenti non sono supportati:

-   Flussi dell'interfaccia utente desktop

    -   Più monitoraggi
    -   Macchine virtuali
    -   Doppio clic, passaggio del mouse, input tocco/penna
    -   Interazioni in Windows (Esplora file, menu di avvio, barra delle applicazioni e così via)

-   Flussi dell'interfaccia utente Web

    -   Clic con il pulsante destro del mouse
    -   Le informazioni sulla sessione utente (ad esempio, cookie) non verranno riutilizzate durante la riproduzione. Sarà necessario modificare lo script per incorporare le informazioni di accesso quando richiesto dai siti Web.

Sono disponibili limitazioni specifiche per le funzionalità incluse nella documentazione per ogni funzionalità.

## <a name="get-your-device-ready"></a>Preparare il dispositivo

Installare i componenti seguenti per creare ed eseguire flussi dell'interfaccia utente:

|  | **Nome**                             | **Utilizzo**  |                                                        
|---|--------------------------------------|----------------------------------------------------------------------|
|   | [App flussi dell'interfaccia utente](https://go.microsoft.com/fwlink/?linkid=2102613)                         | Registrare applicazioni Windows Desktop                                  |          |
|   | Estensione del browser flussi interfaccia utente           | Registrare e testare applicazioni Windows desktop. Registrare le applicazioni Web. |                                                                                              |
|   | WebDriver                            | Testare ed eseguire applicazioni desktop di Windows                            |                                                                                              |
|   | [IDE Selenium](https://go.microsoft.com/fwlink/?linkid=2107665) | Registrare e riprodurre applicazioni Web                                 |  |
|   | [Gateway](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)                              | Usato per abilitare gli eventi, i flussi pianificati o i flussi di pulsanti a cui connettersi, attivare i flussi dell'interfaccia utente (in esecuzione all'interno dell'organizzazione) ed eseguirli.              |  | 

## <a name="install-the-ui-flows-app"></a>Installare l'app flussi dell'interfaccia utente

Il programma di installazione dei flussi dell'interfaccia utente contiene tutti i componenti necessari per registrare, modificare e testare i flussi dell'interfaccia utente per il desktop. 

>[!IMPORTANT]
>Il programma di installazione dei flussi dell'interfaccia utente installa il componente WebDriver e l'estensione del browser flussi dell'interfaccia utente. Entrambi sono necessari per registrare, testare ed eseguire flussi dell'interfaccia utente per il desktop.

Per installare l'app flussi dell'interfaccia utente, seguire questa procedura:

1. [Scaricare il programma di installazione dell'app flussi dell'interfaccia utente](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Aprire il file **Setup. Microsoft. Flow. UIflow. exe** . È probabile che questo file sia presente nella cartella **Downloads** dopo che è stato scaricato nel passaggio precedente.
1. Per completare l'installazione, seguire le istruzioni nel programma di installazione del programma di installazione dei **flussi dell'interfaccia utente (anteprima)** .

## <a name="activate-the-ui-flows-browser-extension"></a>Attivare l'estensione del browser flussi dell'interfaccia utente 

Al termine del programma di installazione dei flussi dell'interfaccia utente, verrà richiesto dal browser di attivare l'estensione.

- In Microsoft Edge (cromo) selezionare ogni icona di avviso nella parte superiore destra del browser e quindi selezionare **Abilita estensione**.
-   In Google Chrome selezionare **Abilita estensione** quando richiesto.  


## <a name="install-selenium-ide"></a>Installare l'IDE Selenium

L'IDE Selenium è uno strumento open source che consente di registrare e riprodurre interazioni umane nei siti Web.

Con i flussi dell'interfaccia utente, è possibile eseguire gli script di selenio IDE da Power automatici e mantenerli archiviati in modo sicuro (con governance IT appropriata) in Common Data Service.

Per installare l'IDE selenio, seguire questa procedura:

1. [Scaricare e installare](https://go.microsoft.com/fwlink/?linkid=2107665) l'IDE selenio per la prossima versione di Microsoft Edge o Google Chrome.

1. In Microsoft Edge (cromo) selezionare **Consenti estensioni da altri archivi**e quindi selezionare **Aggiungi a Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Installare il gateway dati locale

Sarà necessario il gateway per attivare il flusso dell'interfaccia utente da un [evento, una pianificazione o un flusso di un pulsante.](../getting-started.md/#types-of-flows)

>[!TIP]
>Il gateway non è necessario se si vuole solo creare, modificare e testare i flussi dell'interfaccia utente nel dispositivo.

[Installare il gateway dati locale](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), se necessario.

## <a name="uninstall-ui-flows"></a>Disinstalla flussi dell'interfaccia utente

1. Aprire il menu **start** > **Impostazioni** > **app**.
1. Cercare i **flussi dell'interfaccia utente (anteprima)** e quindi selezionarlo.
1. Selezionare **Disinstalla**.

## <a name="next-steps"></a>Passaggi successivi

- Informazioni su come [creare flussi dell'interfaccia utente desktop](create-desktop.md).
- Informazioni su come [creare flussi dell'interfaccia utente Web](create-web.md).
- Informazioni su come eseguire i [flussi dell'interfaccia utente](run-ui-flow.md).
- Informazioni su come [gestire i flussi dell'interfaccia utente](manage.md).
- Altre informazioni sul [Gateway locale](../gateway-reference.md/#use-a-gateway)

