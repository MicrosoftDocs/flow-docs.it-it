---
title: Creare un flusso con Dynamics 365 (online) | Microsoft Docs
description: Creare flussi di lavoro utili usando una connessione a Dynamics 365 e Microsoft Flow
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
ms.openlocfilehash: c3a138cef3761b188998766a60ceb84619ae5f0a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546902"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Creare un flusso con Dynamics 365 (online)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Usando un connettore Dynamics 365, è possibile creare flussi che iniziano quando si verifica un evento in Dynamics 365 o un altro servizio, che esegue quindi un'azione in Dynamics 365 o un altro servizio. 

In Microsoft Flow, è possibile configurare flussi di lavoro automatizzati tra le app e i servizi preferiti per sincronizzare file, ricevere notifiche, raccogliere dati e altro ancora. Per ulteriori informazioni, vedere [Introduzione a Microsoft Flow](getting-started.md).

> [!IMPORTANT] 
> Per richiamare un trigger di flusso, l'entità Common Data Service usata con il flusso deve avere **rilevamento modifiche** abilitata. Altre informazioni: [Abilitazione del rilevamento delle modifiche per controllare la sincronizzazione dei dati](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Creare un flusso da un modello
È possibile creare un flusso usando uno dei numerosi modelli disponibili, ad esempio gli esempi seguenti:

* Quando viene creato un oggetto in Dynamics 365, crea una voce di elenco in SharePoint.
* Creare record lead di Dynamics 365 da una tabella di Excel.
* Copia gli account Dynamics 365 ai clienti in Dynamics 365 per le operazioni.

Per creare un flusso da un modello, seguire questa procedura.

1. Accedere al [sito web Microsoft Flow](https://flow.microsoft.com/).
2. Toccare o fare clic su **Servizi**e quindi toccare o fare clic su **Dynamics 365**.
3. Sono disponibili diversi modelli. Per iniziare, selezionare il modello desiderato.

## <a name="create-a-task-from-a-lead"></a>Creare un'attività da un lead
Se un modello non è disponibile per gli elementi necessari, creare un flusso da zero. Questa procedura dettagliata illustra come creare un'attività in Dynamics 365 ogni volta che viene creato un lead in Dynamics 365.

1. Accedere al [sito web Microsoft Flow](https://flow.microsoft.com/).
2. Toccare o fare clic su **flussi personali**e quindi toccare o fare clic su **Crea da zero**.
3. Nell'elenco dei trigger di flusso toccare o fare clic su **Dynamics 365-quando viene creato un record**.
4. Se richiesto, accedere a Dynamics 365.
5. In **nome organizzazione**selezionare l'istanza di Dynamics 365 in cui si vuole che il flusso sia in ascolto.
6. In **nome entità**, selezionare l'entità che si vuole ascoltare, che fungerà da trigger che avvia il flusso.
   
     Per questa procedura dettagliata, selezionare **Lead**.
   
    ![Dettagli flusso](./media/connection-dynamics365/flow-details.png)
    > IMPORTANTE Affinché il flusso venga attivato nell'entità Dynamics 365, è necessario che la definizione dell'entità abbia **rilevamento modifiche** abilitata. Vedere [abilitare il rilevamento delle modifiche per controllare la sincronizzazione dei dati](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Toccare o fare clic su **nuovo passaggio**e quindi toccare o fare clic su **Aggiungi un'azione**.
8. Toccare o fare clic su **Dynamics 365-crea un nuovo record**.
9. In **nome organizzazione**, selezionare l'istanza di Dynamics 365 in cui si vuole che il flusso crei il record. Si noti che non deve necessariamente essere la stessa istanza da cui viene attivato l'evento.
10. In **nome entità**selezionare l'entità che creerà un record quando si verifica l'evento.
    
     Per questa procedura dettagliata, selezionare **attività**.
11. Viene visualizzata una casella **oggetto** . Quando si fa clic o si tocca il riquadro, viene visualizzato un riquadro di contenuto dinamico in cui è possibile selezionare uno di questi campi.
    
    * **Cognome**. Se si seleziona questo campo, il cognome del lead verrà inserito nel campo **oggetto** dell'attività al momento della creazione.
    * **Argomento**. Se si seleziona questo campo, il campo **argomento** per il lead verrà inserito nel campo **oggetto** dell'attività al momento della creazione.
    
    Per questa procedura dettagliata, selezionare **argomento**.
    
    ![Argomento di aggiunta del flusso](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Suggerimento:** Nel riquadro del contenuto dinamico toccare o fare clic su **Visualizza altro** per visualizzare più campi associati all'entità. È possibile, ad esempio, popolare il campo **oggetto** dell'attività con il **nome della società**, il **cliente**, la **Descrizione**o il campo di **posta elettronica** del responsabile.
    > 
    > 
12. Toccare o fare clic su **Crea flusso**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Creare un'attività Wunderlist da un'attività Dynamics 365
Questa procedura dettagliata illustra come creare un'attività in [Wunderlist](https://www.wunderlist.com) ogni volta che viene creata un'attività in Dynamics 365. Wunderlist è un servizio basato su Internet che è possibile usare per creare elenchi di attività, aggiungere promemoria o tenere traccia delle commissioni.

1. Accedere al [sito web Microsoft Flow](https://flow.microsoft.com/).
2. Toccare o fare clic su **flussi personali**e quindi toccare o fare clic su **Crea da zero**.
3. Nell'elenco dei trigger di flusso toccare o fare clic su **Dynamics 365-quando viene creato un record**.
4. In **nome organizzazione**selezionare l'istanza di Dynamics 365 in cui si vuole che il flusso sia in ascolto.
5. In **nome entità**, selezionare l'entità che si vuole ascoltare, che fungerà da trigger per avviare il flusso.
   
    Per questa procedura dettagliata, selezionare **attività**.
6. Toccare o fare clic su **nuovo passaggio**e quindi toccare o fare clic su **Aggiungi un'azione**.
7. Digitare *Crea un'attività*e quindi fare clic o toccare **Wunderlist – crea un'attività**.
8. In **ID elenco**selezionare **posta in arrivo**.
9. In **titolo**selezionare **oggetto** nel riquadro del contenuto dinamico.
10. Toccare o fare clic su **Crea flusso**.  

## <a name="trigger-based-logic"></a>Logica basata su trigger
Trigger come **quando viene creato un**record, **quando**un record viene aggiornato e **quando un record viene eliminato** , avvia il flusso entro pochi minuti dall'evento che si verifica.  In rari casi, l'attivazione del flusso può richiedere fino a 2 ore.

Quando si verifica il trigger, il flusso riceve una notifica, ma il flusso viene eseguito sui dati esistenti al momento dell'esecuzione dell'azione.  Ad esempio, se il flusso viene attivato quando viene creato un nuovo record e il record viene aggiornato due volte prima dell'esecuzione del flusso, il flusso viene eseguito una sola volta con i dati più recenti.

## <a name="specify-advanced-options"></a>Specificare le opzioni avanzate
Quando si aggiunge un passaggio a un flusso, è possibile toccare o fare clic su **Mostra opzioni avanzate** per aggiungere un filtro o una query Order by che controlla la modalità di filtraggio dei dati nel flusso.

Ad esempio, è possibile usare una query di filtro per recuperare solo i contatti attivi ed è possibile ordinarli in base al cognome. A tale scopo, immettere la query di filtro OData **statusCode EQ 1** e selezionare **Cognome** dal riquadro del contenuto dinamico. Per ulteriori informazioni sulle query di filtro e ordinamento, vedere [MSDN: $Filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) e [MSDN: $OrderBy](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Query OrderBy di Flow](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Procedure consigliate per l'utilizzo di opzioni avanzate
Quando si aggiunge un valore a un campo, è necessario corrispondere al tipo di campo se si digita un valore o se ne seleziona uno dal riquadro del contenuto dinamico.

| Tipo di campo | Come usare | Dove trovare | Nome | Tipo di dati |
| --- | --- | --- | --- | --- |
| Campi di testo |I campi di testo richiedono una singola riga di testo o contenuto dinamico che è un campo di tipo testo. Gli esempi includono i campi **categoria** e **sottocategoria** . |**Impostazioni** > **personalizzazioni** > **personalizzare le** **entità** > di sistema > **campi** dell' **attività** >  |**Categoria** |**Riga di testo singola** |
| Campi Integer |Alcuni campi richiedono un intero o contenuto dinamico che sia un campo di tipo Integer. Gli esempi includono la **percentuale di completamento** e la **durata**. |**Impostazioni** > **personalizzazioni** > **personalizzare le** **entità** > di sistema > **campi** dell' **attività** >  |**PercentComplete** |**Numero intero** |
| Campi data |Alcuni campi richiedono una data immessa nel formato mm/gg/aaaa o contenuto dinamico che è un campo di tipo Data. Gli esempi **includono created on**, **Data di inizio**, **inizio effettivo**, **ultimo periodo di attesa**, **fine effettiva**e **scadenza**. |**Impostazioni** > **personalizzazioni** > **personalizzare le** **entità** > di sistema > **campi** dell' **attività** >  |**createdon** |**Data e ora** |
| Campi che richiedono sia un ID record sia un tipo di ricerca |Alcuni campi che fanno riferimento a un altro record di entità richiedono sia l'ID record che il tipo di ricerca. |**Impostazioni** > **personalizzazioni** > **personalizzare le** **entità** > di sistema > **campi** di > **account** |**AccountID** |**Chiave primaria** |
|Set di opzioni|I campi di set di opzioni richiedono un valore integer noto da passare in questo tipo di campo.  Nell'area di personalizzazione di Dynamics 365, è possibile visualizzare l'opzione imposta il campo intero sottostante insieme alla rispettiva etichetta.|Impostazioni > Personalizzazione > personalizzare le entità > di sistema > campi di > account | Metodo di contatto preferito| Numero intero|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Altri esempi di campi che richiedono sia un ID record sia un tipo di ricerca
Espandendo la tabella precedente, di seguito sono riportati altri esempi di campi che non funzionano con i valori selezionati dall'elenco di contenuto dinamico. Al contrario, questi campi richiedono sia un ID record sia un tipo di ricerca immesso nei campi in PowerApps.

* **Proprietario** e **tipo di proprietario**.
  
  * Il campo **proprietario** deve essere un ID record utente o Team valido.
  * Il **tipo di proprietario** deve essere **systemusers** o **Teams**.
* **Customer** e **Customer Type**.
  
  * Il campo **Customer** deve essere un ID record di account o contatto valido.
  * Il **tipo di cliente** deve essere **accounts** o **Contacts**.
* **Per quanto** riguarda il **tipo**.
  
  * Il campo **relativo** deve essere un ID record valido, ad esempio un ID record di account o contatto.
  * Il **tipo relativo** deve essere il tipo di ricerca per il record, ad esempio **accounts** o **Contacts**.

Questo esempio aggiunge un record di account che corrisponde all'ID record, aggiungendolo al campo **relativo** dell'attività.

  ![Flusso recordId e tipo account](./media/connection-dynamics365/flow-recordid-account.png)

Questo esempio assegna anche l'attività a un utente specifico in base all'ID record dell'utente.

  ![Flusso recordId e tipo utente](./media/connection-dynamics365/flow-recordid-user.png)

Per trovare l'ID di un record, vedere [trovare l'ID record](#find-the-records-id) più avanti in questo argomento.

> **Importante:** I campi non devono contenere un valore se hanno una descrizione di "solo per uso interno". Questi campi includono il **percorso attraversato**, i **parametri aggiuntivi**e il **numero di versione della regola del fuso orario.**
> 
> 

## <a name="find-the-records-id"></a>Trovare l'ID del record
1. Nell'applicazione Web Dynamics 365 aprire un record, ad esempio un record di account.
2. Sulla barra degli strumenti azioni fare clic o toccare **apri**
   ![record popout](./media/connection-dynamics365/popout.png) (oppure toccare o fare clic su **Invia tramite posta elettronica un collegamento** per copiare l'URL completo nel programma di posta elettronica predefinito).
   
    Nella barra degli indirizzi del Web browser l'URL contiene l'ID record tra i caratteri di codifica% 7b e% 7D.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Argomenti correlati
[Risoluzione dei problemi relativi a un flusso](fix-flow-failures.md)

[Il flusso nell'organizzazione Q & A](organization-q-and-a.md)

[Domande frequenti](frequently-asked-questions.md)

