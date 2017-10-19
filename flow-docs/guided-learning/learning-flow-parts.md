---
title: Blocchi predefiniti di Microsoft Flow | Microsoft Docs
description: Conoscere le diverse parti di Microsoft Flow e le relative correlazioni. Creare nuovi flussi dai modelli e da zero.
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: 9U8jMRO-Jv0
courseduration: 9m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 6a7fe2d56c7bc3b2253b675ce26f3f29042a7a71
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2017
---
# <a name="building-blocks-of-microsoft-flow"></a>Blocchi predefiniti di Microsoft Flow
Una volta apprese le nozioni di base, è possibile passare alla **demo di Microsoft Flow**, che illustra brevemente come creare flussi a partire dai modelli oppure da zero.

## <a name="check-out-the-templates"></a>Dare un'occhiata ai modelli
Alla pagina flow.microsoft.com fare clic sul collegamento **Modelli** in alto per visualizzare vari modelli pronti da usare con i servizi Web. Esplorare le varie app per **farsi un'idea delle operazioni eseguibili** e di come usare proficuamente Microsoft Flow in azienda.

![Modelli di flusso](./media/learning-flow-parts/template-list.png)

Ogni flusso di modello è progettato per uno scopo specifico, ad esempio per ricevere una notifica al verificarsi di un evento, copiare un nuovo file da un servizio a un altro o tener traccia delle approvazioni di SharePoint. Questi modelli sono **pronti all'uso**  pertanto è sufficiente **configurarli** per aggiungere flussi al proprio account. Per farlo, fare clic su **Usa questo modello**, iscriversi ai servizi necessari e quindi compilare i moduli che seguono.  Ad esempio, questo è un flusso creato a partire da un modello per inviare notifiche tramite e-mail quando viene modificato un elenco di SharePoint. 

![Modello di esempio di flusso](./media/learning-flow-parts/example-template.png)

Sono disponibili centinaia di modelli, tutti accessibili in **Microsoft Flow per il Web** o **Microsoft Flow per dispositivi mobili**.

![Flow per il Web e per dispositivi mobili](./media/learning-flow-parts/flow-web-mobile.png)

## <a name="create-a-flow-from-scratch"></a>Creare un flusso da zero
È stata illustrata la procedura per creare un flusso usando un modello, ma talvolta potrebbe essere necessario automatizzare un'attività senza che sia disponibile un modello appropriato. In tal caso, è possibile **compilare un flusso da zero**.  Quando si crea un flusso da zero, si parte da un canvas vuoto e vi si aggiungono **servizi, trigger e azioni** per realizzare il flusso.  

![Flusso vuoto](./media/learning-flow-parts/flow-from-blank.png)

## <a name="building-blocks-of-a-flow"></a>Blocchi predefiniti di un flusso
Se si sta creando un flusso da un modello o da zero, i flussi conterranno **blocchi predefiniti** che interagiscono in determinati modi, un po' come i diagrammi di flusso.

* I **servizi** sono le origini e le destinazioni dei dati di un flusso.
* I **trigger** sono eventi che avviano un flusso.
* Le **azioni** sono le attività eseguite dal flusso.
* Le **condizioni** consentono l'implicazione logica se/allora in un flusso.
* I **cicli** servono a ripetere le azioni più volte.

### <a name="services"></a>Servizi
Microsoft Flow può connettersi a molti **servizi e applicazioni**,  come **Twitter**, **Github**, **Wunderlist**, **Office 365** e **Documenti Google**.  Questi ultimi sono le **origini** da cui Microsoft Flow acquisisce i dati e le **destinazioni** delle operazioni che esegue.  L'elenco completo dei servizi è disponibile facendo clic sul collegamento **Servizi** nella parte superiore della pagina **flow.microsoft.com**.

![Connettori di Flow](./media/learning-flow-parts/flow-connectors.png)

### <a name="triggers"></a>Trigger
Ogni flusso inizia con un **trigger**,  che può essere di molti tipi.  Alcuni sono eventi dei servizi Web connessi, come l'**invio di tweet da parte di un utente** o il **salvataggio di file in un account Dropbox**.  Altri trigger sono predefiniti, come l'**esecuzione di un flusso in base a una pianificazione ricorrente** o l'**esecuzione di un flusso in risposta a una richiesta Web**.  Infine, esistono trigger manuali, come l'avvio di un flusso facendo clic su un **pulsante di Microsoft Flow o Microsoft PowerApps**.  Spesso i trigger **trasmettono informazioni sull'evento che si è verificato** alle azioni nel flusso.

![Trigger di Flow](./media/learning-flow-parts/flow-triggers.png)  

### <a name="actions"></a>Azioni
Un'**azione** è il **risultato** che si desidera realizzare con l'attivazione di un flusso,  ad esempio una **notifica**, la **copia di dati o file** da un'origine a una destinazione, ma anche la **pubblicazione di contenuti sui social media** o il **posticipo di un'azione per un certo periodo di tempo**.  Con le azioni è inoltre possibile **recuperare da un servizio i dati** da utilizzare con altre azioni.

![Azioni di Flow](./media/learning-flow-parts/flow-actions.png) 

### <a name="conditions"></a>Condizioni
Le **condizioni** consentono di aggiungere al flusso le decisioni elaborate.  Quando viene valutata una condizione, il flusso si dirama in un percorso **yes** e un percorso **no**.   Ad esempio, se si desidera copiare le foto delle vacanze pubblicate in **Dropbox** su **OneDrive**, è possibile creare una condizione successiva al trigger **Nuovo file di Dropbox** per verificare se il nome del file contenga la parola *vacanze*, nel qual caso il file verrà copiato su **OneDrive**, altrimenti non succederà nulla.

![Condizione di Flow](./media/learning-flow-parts/flow-condition.png) 

### <a name="loops"></a>Cicli
I **cicli** consentono di eseguire un'operazione più volte, ad esempio quando occorre ripetere un'azione diverse volte oppure una volta sola per ciascuno degli elementi di una raccolta.

## <a name="next-lesson"></a>Lezione successiva
Questo argomento descrive Microsoft Flow.  Abbiamo esplorato i **modelli** e illustrato come **creare un flusso da zero**.  Creeremo flussi connettendo app e servizi, **trigger** per avviare un flusso, **azioni** per farvi accadere qualcosa, **condizioni** per applicare decisioni e **cicli** per ripetere un'operazione nel flusso.  **Il modo più semplice per conoscere Microsoft Flow è partire da un modello** e connetterlo alle app e ai servizi già in uso. 

Dopodiché, faremo un ripasso di quanto imparato finora in questo corso per l'apprendimento guidato.

