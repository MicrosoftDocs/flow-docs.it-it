---
title: Gruppi di dati di Microsoft Flow | Microsoft Docs
description: Introduzione ai gruppi di dati di Microsoft PowerApps e Microsoft Flow.
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
ms.openlocfilehash: fd76c12d1879c9b613ba833d9ef2211cd4aab702
ms.sourcegitcommit: f0202f74ba9a2282a670a1751462f598a5ea0ce5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="learn-all-about-data-groups"></a>Tutte le informazioni su gruppi di dati
## <a name="what-is-a-data-group"></a>Che cos'è un gruppo di dati?
I gruppi di dati sono un metodo semplice per categorizzare i servizi all'interno di un [criterio di prevenzione della perdita dei dati (DLP)](prevent-data-loss.md). I due gruppi di dati disponibili nei gruppi **Business data only** (Solo dati business) e **No business data allowed** (Nessun dato business consentito). Ogni organizzazione è libera di decidere quali servizi inserire in un determinato gruppo di dati. Un buon metodo per categorizzare i servizi consiste nell'organizzarli in gruppi, in base all'impatto che hanno sull'organizzazione. Per impostazione predefinita, tutti i servizi sono inseriti nel gruppo di dati **No business data allowed** (Nessun dato business consentito). La gestione dei servizi in un gruppo di dati viene eseguita creando o modificando le proprietà di un criterio DLP nell'interfaccia di amministrazione.

## <a name="how-data-is-shared-between-data-groups"></a>Modalità di condivisione fra gruppi di dati
Non è possibile condividere dati tra servizi che si trovano in gruppi diversi. Ad esempio, se si inseriscono SharePoint e Salesforce nel gruppo **Business data only** (Solo dati business), mentre nel gruppo **No business data allowed** (Nessun dato business consentito) si inseriscono Facebook e Twitter, non è possibile creare un flusso che trasferisca i dati tra SharePoint e Facebook. Se non è possibile condividere dati tra i servizi inseriti in gruppi diversi, è invece possibile condividerli tra servizi all'interno di un gruppo specifico. Per tornare all'esempio precedente, poiché SharePoint e Salesforce sono stati inseriti nello stesso gruppo di dati, i flussi creati dagli utenti finali possono condividere i dati tra SharePoint e Salesforce. Allo stesso modo, gli utenti finali possono creare flussi e PowerApps che condividono i dati tra Facebook e Twitter. In sintesi, i servizi inseriti in uno stesso gruppo possono condividere i dati, mentre quelli inseriti in gruppi diversi non possono farlo.  

Inoltre, è necessario che un gruppo di dati sia designato come il gruppo *predefinito*. Inizialmente, il gruppo **No business data allowed** (Nessun dato business consentito) sarà quello *predefinito* e conterrà tutti i servizi. L'amministratore può successivamente decidere di impostare come gruppo di dati predefinito il gruppo **Business data only** (Solo dati business). **Nota**: gli eventuali nuovi servizi aggiunti al flusso verranno inseriti nel gruppo designato come *predefinito*. Per questo motivo, è consigliabile mantenere come gruppo predefinito il gruppo **No business data allowed** (Nessun dato business consentito) e aggiungere manualmente i servizi nel gruppo **Business data only** (Solo dati business) solo dopo che l'organizzazione avrà valutato le possibili conseguenze di condividere i dati di business con il nuovo servizio.

## <a name="add-services-to-a-data-group"></a>Aggiungere servizi a un gruppo di dati
In questa procedura dettagliata aggiungeremo SharePoint e Salesforce al gruppo di dati **Business data only** (Solo dati business) di un criterio di prevenzione della perdita dei dati (DLP). 

1. Selezionare il collegamento **+ Add** (+ Aggiungi) nella casella di gruppo **Business data only** (Solo dati business) di un criterio DLP:    
   ![Add image](./media/introduction-to-data-groups/add-to-data-group-1.png) (Aggiungi immagine)  
2. Selezionare SharePoint e Salesforce, quindi **Add services** (Aggiungi servizi) per aggiungerli entrambi al gruppo riservato ai dati business:    
   ![Add services image](./media/introduction-to-data-groups/add-to-data-group-2.png) (Aggiungi immagine servizi)  
3. Selezionare **Save Policy** (Salva criterio) dal menu in alto:  
   ![Save policy](./media/introduction-to-data-groups/add-to-data-group-4.png) (Salva criterio) 
4. Ora il gruppo riservato ai dati business contiene Salesforce e SharePoint:  
   ![gruppo di dati business aggiornato](./media/introduction-to-data-groups/add-to-data-group-3.png)   

In questa procedura dettagliata SharePoint e Salesforce sono stati aggiunti al gruppo di dati **Business data only** (Solo dati business) di un criterio DLP. Se una persona che fa parte dell'ambiente dei criteri DLP crea un'app che condivide i dati tra SharePoint o Salesforce e un altro servizio nel gruppo **No business data allowed** (Nessun dato business consentito), l'applicazione non potrà essere eseguita.

## <a name="remove-services-from-a-data-group"></a>Rimuovere servizi da un gruppo di dati
Poiché i servizi devono essere tutti in uno dei gruppi di dati disponibili, per rimuovere un servizio da un determinato gruppo è sufficiente aggiungerlo a un altro gruppo e quindi salvare il criterio.  

## <a name="change-the-default-data-group"></a>Modificare il gruppo di dati predefinito
In questa procedura dettagliata modificheremo il gruppo di dati predefinito dal gruppo **No business data allowed** (Nessun dato business consentito) al gruppo **Business data only** (Solo dati business).  

**Importante**: gli eventuali nuovi servizi aggiunti al flusso verranno inseriti nel gruppo designato come *predefinito*. Per questo motivo, è consigliabile mantenere come gruppo predefinito il gruppo **No business data allowed** (Nessun dato business consentito) e aggiungere manualmente i servizi nel gruppo **Business data only** (Solo dati business).

1. Fare clic su **...** in alto a destra nel gruppo di dati che si desidera designare come predefinito:    
   ![modificare il gruppo predefinito](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Fare clic su **Set as default group** (Imposta come gruppo predefinito):  
   ![modificare il gruppo predefinito](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selezionare **Save Policy** (Salva criterio) dal menu in alto:  
   ![modificare il gruppo predefinito](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Ora il gruppo di dati è designato come il gruppo di dati predefinito:  
   ![modificare il gruppo predefinito](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Passaggi successivi
* [Altre informazioni sui criteri di prevenzione della perdita dei dati (DLP)](prevent-data-loss.md)
* [Altre informazioni sugli ambienti](environments-overview-admin.md)   

