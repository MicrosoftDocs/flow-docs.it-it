---
title: Creare un flusso con Dynamics 365 (online) | Microsoft Docs
description: Creare flussi di lavoro utili con una connessione di Dynamics 365 e Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 64dc59bc53dfdc1d09dbb80be4f32a33c7259415
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64457384"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Creare un flusso con Dynamics 365 (online)
Usando un connettore Dynamics 365, è possibile creare flussi che si avviano quando si verifica un evento in Dynamics 365 o in un altro servizio, che quindi esegue un'azione in Dynamics 365 o un altro servizio. 

In Microsoft Flow è possibile configurare i flussi di lavoro automatizzati tra le app e i servizi preferiti per sincronizzare file, ricevere notifiche, raccogliere dati e altro ancora. Per altre informazioni, vedere [Attività iniziali con Microsoft Flow](getting-started.md).

> [!IMPORTANT] 
> Per chiamare un trigger di flusso, nell'entità di engagement personalizzata di Dynamics 365 deve essere abilitato il **Rilevamento modifiche**. Altre informazioni: [Abilitare la registrazione delle modifiche per controllare la sincronizzazione dei dati](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Creare un flusso da un modello
È possibile creare un flusso usando uno dei numerosi modelli disponibili, come in questi esempi:

* Quando viene creato un oggetto in Dynamics 365, creare una voce di elenco in SharePoint.
* Creare record di lead in Dynamics 365 da una tabella di Excel.
* Copiare gli account di Dynamics 365 nei record clienti di Dynamics 365 per le operazioni.

Per creare un flusso da un modello, seguire questi passaggi.

1. Accedere al [sito Web di Microsoft Flow](https://flow.microsoft.com/).
2. Scegliere o toccare **servizi**, quindi scegliere o toccare **Dynamics 365**.
3. Sono disponibili diversi modelli. Per iniziare, selezionare il modello desiderato.

## <a name="create-a-task-from-a-lead"></a>Creare un'attività da un lead
Se non è disponibile un modello adatto alle proprie necessità, creare un flusso da zero. Questa procedura dettagliata illustra come creare un'attività in Dynamics 365 ogni volta che viene creato un lead in Dynamics 365.

1. Accedere al [sito Web di Microsoft Flow](https://flow.microsoft.com/).
2. Scegliere o toccare **Flussi personali**, quindi scegliere o toccare **Crea da zero**.
3. Nell'elenco dei trigger di flusso, scegliere o toccare **Dynamics 365 - Quando un record viene creato**.
4. Se richiesto, accedere a Dynamics 365.
5. In **Nome organizzazione**, selezionare l'istanza di Dynamics 365 in cui avviare l'ascolto del flusso.
6. In **Nome entità**, selezionare l'entità da ascoltare, che fungerà da trigger di avvio del flusso.
   
     Per questa procedura dettagliata, selezionare **Lead**.
   
    ![Flow details (Dettagli del flusso)](./media/connection-dynamics365/flow-details.png)
    > [IMPORTANTE] Per consentire l'attivazione del flusso sull'entità di Dynamics 365, è necessario che l'opzione **Rilevamento modifiche** sia abilitata per la definizione dell'entità. Vedere [Abilitare la registrazione delle modifiche per controllare la sincronizzazione dei dati](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Scegliere o toccare **Nuovo passaggio**, quindi scegliere o toccare **Aggiungi un'azione**.
8. Scegliere o toccare **Dynamics 365 - Crea un nuovo record**.
9. In **Nome organizzazione**, selezionare l'istanza di Dynamics 365 in cui il flusso dovrà creare il record. Si noti che non deve necessariamente essere la stessa istanza da cui viene attivato l'evento.
10. In **Nome entità**, selezionare l'entità che creerà un record quando si verifica l'evento.
    
     Per questa procedura dettagliata, selezionare **Attività**.
11. Viene visualizzata la casella **Oggetto**. Quando si sceglie o si tocca la casella, viene visualizzato un riquadro di contenuto dinamico in cui è possibile selezionare uno di questi campi.
    
    * **Cognome**. Se si seleziona questo campo, il cognome del lead verrà inserito nel campo **Oggetto** dell'attività quando viene creato.
    * **Argomento**. Se si seleziona questo campo, il campo **Argomento** per il lead verrà inserito nel campo **Oggetto** dell'attività quando viene creato.
    
    Per questa procedura dettagliata, selezionare **Argomento**.
    
    ![Flow - Aggiungi argomento](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Suggerimento:** nel riquadro del contenuto dinamico, fare clic o toccare **Vedi altro** per visualizzare più campi associati all'entità. Ad esempio, è anche possibile popolare il campo **Oggetto** dell'attività con il campo **Nome società**, **Cliente**, **Descrizione** o **Posta elettronica** del lead.
    > 
    > 
12. Scegliere o toccare **Crea flusso**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Creare un'attività Wunderlist da un'attività di Dynamics 365
Questa procedura dettagliata illustra come creare un'attività in [Wunderlist](https://www.wunderlist.com) ogni volta che viene creata un'attività in Dynamics 365. Wunderlist è un servizio basato su Internet che è possibile usare per creare elenchi di attività, aggiungere i promemoria o tenere traccia di commissioni.

1. Accedere al [sito Web di Microsoft Flow](https://flow.microsoft.com/).
2. Scegliere o toccare **Flussi personali**, quindi scegliere o toccare **Crea da zero**.
3. Nell'elenco dei trigger di flusso, scegliere o toccare **Dynamics 365 - Quando un record viene creato**.
4. In **Nome organizzazione**, selezionare l'istanza di Dynamics 365 in cui avviare l'ascolto del flusso.
5. In **Nome entità**, selezionare l'entità da ascoltare, che fungerà da trigger di avvio del flusso.
   
    Per questa procedura dettagliata, selezionare **Attività**.
6. Scegliere o toccare **Nuovo passaggio**, quindi scegliere o toccare **Aggiungi un'azione**.
7. Digitare *Crea un'attività*, quindi scegliere o toccare **Wunderlist - Crea un'attività**.
8. In **ID lista**, selezionare **Posta in arrivo**.
9. In **Titolo**selezionare **oggetto** nel riquadro del contenuto dinamico.
10. Scegliere o toccare **Crea flusso**.  

## <a name="trigger-based-logic"></a>Logica basata sui trigger
I trigger come **Quando un record viene creato**, **Quando un record viene aggiornato** e **Quando un record viene eliminato** avviano il flusso dopo pochi minuti che si è verificato l'evento.  In rari casi, l'attivazione del flusso può richiedere fino a 2 ore.

Quando si verifica il trigger, il flusso riceve una notifica ma viene eseguito sui dati esistenti al momento dell'esecuzione dell'azione.  Ad esempio, se il flusso viene avviato quando viene creato un nuovo record e il record viene aggiornato due volte prima dell'esecuzione del flusso, il flusso viene eseguito una sola volta con i dati più recenti.

## <a name="specify-advanced-options"></a>Specificare le opzioni avanzate
Quando si aggiunge un passaggio a un flusso, è possibile scegliere o toccare **Mostra opzioni avanzate** per aggiungere un filtro o per ordinare in base alla query che controlla come vengono filtrati i dati nel flusso.

Ad esempio, è possibile usare una query di filtro per recuperare solo i contatti attivi e ordinarli in base al cognome. A tale scopo, immettere la query del filtro OData **statuscode eq 1** e selezionare **Cognome** dal riquadro del contenuto dinamico. Per altre informazioni sul filtro e ordinamento in base alle query, vedere [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) e [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Flow - Ordinamento in base alla query](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Procedure consigliate quando si usano le opzioni avanzate
Quando si aggiunge un valore a un campo, deve corrispondere al tipo di campo che si digiti un valore o se ne selezioni uno dal riquadro del contenuto dinamico.

| Tipo di campo | Come usarlo | Dove trovarlo | Nome | Tipo di dati |
| --- | --- | --- | --- | --- |
| Campi di testo |I campi di testo richiedono una singola riga di testo o contenuto dinamico che sia un campo di tipo testo. Alcuni esempi sono i campi **Categoria** e **Sottocategoria**. |**Impostazioni** > **Personalizzazioni** > **Personalizzare il sistema** > **Entità** > **Attività** > **Campi** |**categoria** |**Singola riga di testo** |
| Campi integer |Alcuni campi richiedono un valore integer o contenuto dinamico che sia un campo di tipo integer. Alcuni esempi sono **Percentuale completata** e **Durata**. |**Impostazioni** > **Personalizzazioni** > **Personalizzare il sistema** > **Entità** > **Attività** > **Campi** |**percentcomplete** |**Numero intero** |
| Campi di data |Alcuni campi richiedono una data immessa nel formato mm/gg/aaaa o contenuto dinamico che sia un campo di tipo data. Gli esempi includono **Data creazione**, **Data di inizio**, **Inizio effettivo**, **Ultimo periodo sospensione**, **Fine effettiva** e **Scadenza**. |**Impostazioni** > **Personalizzazioni** > **Personalizzare il sistema** > **Entità** > **Attività** > **Campi** |**createdon** |**Data e ora** |
| I campi che richiedono sia un ID record sia un tipo di ricerca |Alcuni campi che fanno riferimento a un altro record di entità richiedono sia l'ID record sia il tipo di ricerca. |**Impostazioni** > **Personalizzazioni** > **Personalizzare il sistema** > **Entità** > **Account** > **Campi** |**accountid** |**Chiave primaria** |
|Set di opzioni|Per i campi Set di opzioni è richiesto il passaggio di un valore integer noto.  Nell'area di personalizzazione di Dynamics 365 è possibile visualizzare i set di opzioni a supporto del campo integer insieme alla rispettiva etichetta.|Impostazioni > Personalizzazione > Personalizzare il sistema > Entità > Account > Campi | Metodo di contatto preferito| Numero intero|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Altri esempi di campi che richiedono sia un ID record sia un tipo di ricerca
Espandendo la tabella precedente, ecco altri esempi di campi che non funzionano con i valori selezionati dall'elenco di contenuto dinamico, ma richiedono invece l'immissione sia di un ID record sia di un tipo di ricerca nei campi in PowerApps.

* **Proprietario** e **Tipo proprietario**.
  
  * Il campo **proprietario** deve essere un ID valido di record utente o del team.
  * Il **Tipo proprietario** deve essere **systemusers** o **teams**.
* **Cliente** e **Tipo cliente**.
  
  * Il campo **Cliente** deve essere un ID record di account o contatto valido.
  * Il **Tipo cliente** deve essere **accounts** o **contacts**.
* **Tema** e **Tipo relativo**.
  
  * Il campo **Tema** deve essere un ID record valido, ossia un ID record di account o contatto.
  * Il campo **Tipo relativo** deve essere il tipo di ricerca per il record, ad esempio **accounts** o **contacts**.

In questo esempio aggiunge un record dell'account che corrisponde all'ID del record, aggiungendolo al campo **Tema** dell'attività.

  ![Flow - ID record e account tipo](./media/connection-dynamics365/flow-recordid-account.png)

In questo esempio viene anche assegnata l'attività a un utente specifico in base all'ID record dell'utente.

  ![Flow - ID record e utente tipo](./media/connection-dynamics365/flow-recordid-user.png)

Per trovare l'ID di un record, vedere [Trovare l'ID del record](#find-the-records-id) più avanti in questo argomento.

> **Importante:** i campi non devono contenere un valore se hanno una descrizione del tipo "Solo per uso interno." Questi campi sono **Percorso incrociato**, **Parametri aggiuntivi** e **Numero di versione regola fuso orario.**
> 
> 

## <a name="find-the-records-id"></a>Trovare l'ID del record
1. Nell'applicazione Web Dynamics 365, aprire un record, ad esempio un record di account.
2. Nella barra degli strumenti Azioni, scegliere o toccare **Apri nuova finestra**
   ![popout record](./media/connection-dynamics365/popout.png) (oppure scegliere o toccare **Invia link tramite messaggio e-mail** per copiare l'URL completo nel programma di posta elettronica predefinito).
   
    Nella barra degli indirizzi del Web browser, l'URL conterrà l'ID record tra i caratteri %7b e %7d.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Argomenti correlati
[Risoluzione dei problemi relativi a un flusso](fix-flow-failures.md)

[Domande e risposte riguardo alla registrazione a Microsoft Flow nell'organizzazione](organization-q-and-a.md)

[Domande frequenti](frequently-asked-questions.md)

