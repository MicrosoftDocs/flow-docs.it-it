---
title: Gruppi di dati per Microsoft Flow | Microsoft Docs
description: Introduzione ai gruppi di dati per Microsoft PowerApps e Microsoft Flow.
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
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 030e0563ce9adaa7c1c5c44f1446859e3152a398
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547432"
---
# <a name="learn-all-about-data-groups"></a>Informazioni sui gruppi di dati
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-is-a-data-group"></a>Che cos'è un gruppo di dati?
I gruppi di dati rappresentano un modo semplice per categorizzare i servizi in un [criterio di prevenzione della perdita dei dati (DLP)](prevent-data-loss.md). I due gruppi di dati disponibili sono il gruppo **solo dati aziendali** e il gruppo **Nessun dato aziendale consentito** . Le organizzazioni sono gratuite per determinare i servizi inseriti in un particolare gruppo di dati. Un modo efficace per categorizzare i servizi consiste nell'inserirli in gruppi, in base all'effetto sull'organizzazione. Per impostazione predefinita, tutti i servizi vengono inseriti nel gruppo di dati **Nessun dato aziendale consentito** . È possibile gestire i servizi in un gruppo di dati quando si creano o si modificano le proprietà di un criterio DLP dall'interfaccia di amministrazione.

## <a name="how-data-is-shared-between-data-groups"></a>Modalità di condivisione dei dati tra i gruppi di dati
I dati non possono essere condivisi tra i servizi presenti in gruppi diversi. Se ad esempio si inseriscono SharePoint e Salesforce nel gruppo **solo dati aziendali** e si posizionano Facebook e Twitter nel gruppo **Nessun dato business consentito** , non è possibile creare un flusso che sposta i dati tra SharePoint e Facebook. Mentre i dati non possono essere condivisi tra i servizi in gruppi diversi, è possibile condividere i dati tra i servizi all'interno di un gruppo specifico. Quindi, tornando all'esempio precedente, poiché SharePoint e Salesforce sono stati inseriti nello stesso gruppo di dati, i flussi creati dagli utenti finali possono condividere dati tra SharePoint e Salesforce. Analogamente, gli utenti finali possono creare flussi e PowerApps che condividono i dati tra Facebook e Twitter. Il punto chiave è che i servizi in un gruppo specifico possono condividere dati, mentre i servizi in gruppi diversi non possono condividere dati.  

Inoltre, un gruppo di dati deve essere designato come gruppo *predefinito* . Inizialmente, il gruppo **No Business Data allowed** è il gruppo *predefinito* e tutti i servizi si trovano nel gruppo di dati. Un amministratore può modificare il gruppo di dati predefinito nel gruppo di dati **Business Data Only** . Si **noti** che tutti i nuovi servizi aggiunti al flusso verranno inseriti nel gruppo *predefinito* designato. Per questo motivo, è consigliabile evitare che i **dati aziendali siano consentiti** come gruppo predefinito e aggiungere manualmente i servizi al gruppo **solo dati di business** dopo che l'organizzazione ha valutato l'effetto della condivisione dei dati aziendali con il nuovo servizio.

## <a name="add-services-to-a-data-group"></a>Aggiungere servizi a un gruppo di dati
In questa procedura dettagliata verranno aggiunti SharePoint e Salesforce al gruppo di dati **Business Data Only** di un criterio di prevenzione della perdita dei dati (DLP). 

1. Selezionare il collegamento **+ Aggiungi** nella casella di gruppo **Business Data Only (solo dati business** ) di un criterio DLP:    
   ![Aggiungi immagine](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Selezionare SharePoint e Salesforce, quindi selezionare **Aggiungi servizi** per aggiungere entrambi al gruppo solo dati aziendali:    
   ![aggiungere un'immagine dei servizi](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Selezionare **Salva criterio** dal menu in alto:  
   ![salvare i criteri](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Si noti che SharePoint e Salesforce sono ora presenti nel gruppo solo dati aziendali:  
   ![gruppo di dati business aggiornato](./media/introduction-to-data-groups/add-to-data-group-3.png)   

In questa procedura dettagliata sono stati aggiunti SharePoint e Salesforce al gruppo di dati **Business Data Only (solo dati business** ) di un criterio DLP. Se una persona che fa parte dell'ambiente dei criteri DLP crea un'app che condivide i dati tra SharePoint o Salesforce e qualsiasi servizio nel gruppo di dati **Nessun dato aziendale consentito** , l'app non sarà consentita per l'esecuzione.

## <a name="remove-services-from-a-data-group"></a>Rimuovere servizi da un gruppo di dati
Poiché tutti i servizi devono trovarsi in uno dei gruppi di dati disponibili, per rimuovere un servizio da un gruppo specifico, è sufficiente aggiungere il servizio a un altro gruppo, quindi salvare il criterio.  

## <a name="change-the-default-data-group"></a>Modificare il gruppo di dati predefinito
In questa procedura dettagliata verrà modificato il gruppo di dati predefinito dal gruppo di dati **Nessun dato aziendale consentito** al gruppo di dati **Business Data Only (solo dati** business).  

**Importante** tutti i nuovi servizi aggiunti al flusso verranno inseriti nel gruppo *predefinito* designato. Per questo motivo, è consigliabile evitare che i **dati aziendali siano consentiti** come gruppo predefinito e aggiungere manualmente i servizi nel gruppo **solo dati aziendali** .

1. Selezionare il **...** nell'angolo superiore destro del gruppo di dati che si desidera designare come gruppo di dati predefinito:    
   ![modificare il gruppo predefinito](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Selezionare **Imposta come gruppo predefinito**:  
   ![modificare il gruppo predefinito](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selezionare **Salva criterio** dal menu in alto:  
   ![modificare il gruppo predefinito](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Si noti che il gruppo di dati è ora designato come gruppo di dati predefinito:  
   ![modificare il gruppo predefinito](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Passaggi successivi
* [Altre informazioni sui criteri di prevenzione della perdita dei dati (DLP)](prevent-data-loss.md)
* [Altre informazioni sugli ambienti](environments-overview-admin.md)   

