---
title: Progettare flussi con Microsoft Visio | Microsoft Docs
description: Sfrutta le competenze di Visio della tua organizzazione per creare modelli comuni come punto di partenza per la creazione di flussi.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0ffe9fbf8c29682bbcb941dbb48f9986f3c7144d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548772"
---
# <a name="design-flows-in-microsoft-visio"></a>Flussi di progettazione in Microsoft Visio
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Il Microsoft Flow designer è uno strumento completo in cui è possibile configurare tutti i dettagli della logica. Tuttavia, a volte potrebbe essere necessario disegnare la logica del flusso prima di iniziare a creare il flusso. A tale scopo, utilizzare Microsoft Visio direttamente dall'interno Microsoft Flow.

>[!TIP]
> Molti processi condividono un modello comune ma presentano variazioni minime in un'organizzazione. Per risparmiare tempo all'interno dell'organizzazione, è possibile utilizzare Visio per creare un modello di flusso di lavoro master che verrà modificato da altri utenti con parametri specializzati.

## <a name="prerequisites"></a>Prerequisiti

- Un account Microsoft Flow.
- L'app desktop Microsoft Visio (versione in lingua inglese).
- Esperienza nell'utilizzo di Microsoft Visio.

## <a name="design-a-workflow-in-visio"></a>Progettare un flusso di lavoro in Visio

1. Accedere [Microsoft Flow](https://flow.microsoft.com).
1. Selezionare **modelli** dal pannello sul lato sinistro.

     ![Selezionare i modelli dal pannello sinistro](./media/visio-flows/templates-from-left-panel.png)

1. Selezionare **Visio** dall'elenco.

     ![Filtra per modelli di Visio](./media/visio-flows/select-visio.png) 

1. Selezionare il modello di **Diagramma BPMN del flusso di base** nell'elenco dei modelli di **Visio** visualizzato.

     ![Selezionare un modello di Visio](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >Visio informa che i file da Internet potrebbero danneggiare il dispositivo. Se si ha familiarità, selezionare **Sì** nel messaggio di avviso.

     ![Nota avviso sui file da Internet](./media/visio-flows/visio-warning.png)

1. Viene avviata la finestra di progettazione di Visio.

     ![Visualizzazione di progettazione Visio](./media/visio-flows/visio-designer.png)


1. Usare le forme di base di BPMN per [progettare il flusso di lavoro](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a).

   ![BPMN forme di base](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-microsoft-flow"></a>Preparare l'esportazione del flusso di lavoro in Microsoft Flow

Seguire questa procedura per preparare il flusso di lavoro in modo che sia possibile esportarlo in Microsoft Flow.

1. Selezionare la scheda **processo** .
1. Selezionare **prepararsi per l'esportazione** dal **Microsoft Flow** gruppo di icone.

   ![Selezionare l'icona prepara per l'esportazione](./media/visio-flows/prepare-export-icon.png)
   
   Verrà aperto il gruppo **preparare l'esportazione** .

   ![Prepara gruppo di esportazione](./media/visio-flows/prepare-export-group.png)

1. Nella scheda **mapping di flusso** del gruppo **prepararsi all'esportazione** eseguire il mapping del diagramma BPMN ai controlli Microsoft Flow. 

1. Nella scheda **trigger e azioni** del gruppo **prepararsi all'esportazione** eseguire il mapping del diagramma BPMN per Microsoft Flow trigger e azioni selezionando ogni forma e quindi selezionando un trigger o un'azione per rappresentare la forma in Microsoft Flow.

Il flusso di lavoro è pronto per essere esportato quando non ci sono problemi rimanenti nel controllo **prepara per l'esportazione** .

![Nessun problema](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>Esportare il flusso di lavoro
1. Selezionare il pulsante **Esporta in flusso** per esportare il diagramma del flusso di lavoro in Microsoft Flow.
1. Assegnare un nome al flusso e quindi selezionare il pulsante **Crea flusso** .
   
   ![Creare il flusso](./media/visio-flows/export-create-flow.png)

1. Verrà visualizzato un report di esito positivo simile a quello seguente.

    ![Successo](./media/visio-flows/export-create-flow-success.png)

È ora possibile eseguire o apportare modifiche al flusso dalla finestra di progettazione Microsoft Flow, proprio come qualsiasi altro flusso.

>[!TIP]
> Usare le funzionalità di condivisione e commenti di Visio per collaborare con più stakeholder e creare rapidamente un flusso di lavoro completo.

## <a name="learn-more"></a>Ulteriori informazioni

- [Inizia a usare Microsoft Flow](getting-started.md) 
- [Creazione di flussi in più passaggi](multi-step-logic-flow.md)
- [Progettare un flusso con Microsoft Visio](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
