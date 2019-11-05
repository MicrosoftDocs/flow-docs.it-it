---
title: Iscriversi a Flow Q & a nell'organizzazione | Microsoft Docs
description: Domande e risposte comuni su licenze, amministrazione e utenti che si iscrivono a Flow nel tenant di Office 365
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/05/2016
ms.author: stepsic
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 750386a4a90a0b8dfb0f1e1f4320de3afee8db6f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548913"
---
# <a name="flow-in-your-organization-qa"></a>Il flusso nell'organizzazione Q & A
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Questo argomento descrive il modo in cui gli utenti dell'organizzazione possono usare Flow e come è possibile controllare il servizio Flow.

## <a name="signing-up-for-flow"></a>Iscrizione a Flow
### <a name="what-is-microsoft-flow"></a>Che cos'è Microsoft Flow?
Microsoft Flow è un servizio cloud pubblico che consente a singoli utenti e team di configurare flussi di lavoro automatizzati tra le app e i servizi preferiti per sincronizzare, ricevere notifiche, raccogliere dati e altro ancora. 

### <a name="how-do-people-sign-up-for-flow"></a>In che modo gli utenti si iscrivono a Flow?
Ci sono due modi possibili per consentire ai singoli utenti di iscriversi a Flow tramite il portale Web:

#### <a name="option-1"></a>Opzione 1
Chiunque può iscriversi visitando [Flow.Microsoft.com](https://flow.microsoft.com), selezionando **iscrizione gratuita**e quindi completando il processo di iscrizione per flow attraverso [admin.Microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) o [signup.Live.com](https://signup.live.com).

#### <a name="option-2"></a>Opzione 2
Chiunque può iscriversi visitando [Flow.Microsoft.com](https://flow.microsoft.com), selezionando **Accedi**, accedendo con l'ufficio, l'Istituto di istruzione o l'indirizzo di posta elettronica personale e accettando le condizioni per l'utilizzo del flusso.    

Quando un utente dell'organizzazione si iscrive a Flow con l'opzione 2, a tale utente verrà assegnata automaticamente una licenza gratuita Microsoft Flow.

[Per iscriversi a Flow](sign-up-sign-in.md) sono disponibili altri dettagli.

### <a name="what-is-the-microsoft-flow-free-plan"></a>Qual è il piano gratuito Microsoft Flow?

Il piano gratuito Microsoft Flow viene utilizzato solo a scopo di verifica. L'abilitazione o la disabilitazione non influisce sulla capacità di un utente di creare flussi. Se si disabilita il piano Microsoft Flow Free, questo viene abilitato di nuovo quando un utente esegue l'accesso. Questo è il comportamento previsto.

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>È possibile impedire a un altro utente di iscriversi a Flow?
Microsoft Flow è un servizio cloud completamente pubblico e tutti gli utenti del mondo possono iscriversi e usarlo per automatizzare le attività quotidiane. Per usare Microsoft Flow non sono previsti requisiti per gli utenti o per l'uso di un account Office 365. Per questo motivo, al momento non esiste alcun meccanismo per impedire a un altro utente di usare Flow, in quanto tutti gli utenti del mondo possono, indipendentemente dall'indirizzo di posta elettronica.

Tuttavia, se una persona si iscrive a Microsoft Flow e si sceglie di non supportarle all'interno dell'organizzazione, non possono sostenere costi per l'azienda. Quando un utente si iscrive a Microsoft Flow, la relazione è tra l'utente e Microsoft, che è come molti altri servizi cloud di Microsoft, ad esempio Bing, Wunderlist, OneDrive o Outlook.com. L'uso di Microsoft Flow da parte di un utente non implica in alcun modo che il servizio venga fornito dall'organizzazione.

Infine, se l'azienda vuole limitare l'uso di dati solo dell'organizzazione all'interno di Microsoft Flow, ciò è possibile tramite i criteri di prevenzione della perdita dei dati (DLP).

### <a name="how-can-people-gain-access-to-the-paid-features-of-microsoft-flow"></a>In che modo le persone possono accedere alle funzionalità a pagamento di Microsoft Flow?
Gli utenti possono ottenere l'accesso alle funzionalità a pagamento di Microsoft Flow in tre modi diversi:

1. Possono iscriversi individualmente a una versione di valutazione gratuita di Microsoft Flow Plan 1 o Flow Plan 2 90 giorni
2. È possibile assegnare una licenza di Microsoft Flow all'interno del portale di amministrazione di Office 365.
3. All'utente sono stati assegnati piani di Office 365 e Dynamics 365 che includono l'accesso al servizio Flow. Vedere la [pagina prezzi di Flow](https://flow.microsoft.com/pricing/) per l'elenco dei piani di Office 365 e Dynamics 365 che includono le funzionalità di flusso.

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>È possibile impedire a un altro utente di usare le funzionalità a pagamento di Flow?
Qualsiasi utente può provare le funzionalità a pagamento di Microsoft Flow per 90 giorni e non comporta costi aggiuntivi. Tuttavia, è possibile gestire completamente l'assegnazione delle licenze a pagamento perpetue all'interno dell'organizzazione tramite il portale di amministrazione di Office 365.

Come per le offerte gratuite, se un utente sceglie di iscriversi alla versione di valutazione che è una relazione diretta tra l'utente e Microsoft, non necessariamente approvata dall'azienda.

## <a name="administration-of-flow"></a>Amministrazione di Flow
### <a name="why-has-the-flow-icon-appeared-in-the-office-365-app-launcher"></a>Perché è presente l'icona di Flow nell'utilità di avvio delle app di Office 365?
Come annunciato nell'agosto, Microsoft Flow ora è una parte fondamentale della suite Office 365. Tre mesi dopo questo annuncio Microsoft Flow stato abilitato come servizio come parte di tutti gli SKU di Office 365 esistenti. Poiché gli utenti in tutto il mondo possono ora usare Microsoft Flow, è apparso nell'utilità di avvio delle app.

Per impostazione predefinita, vedere la sezione seguente se si vuole rimuovere il riquadro flow dall'utilità di avvio delle app.

### <a name="how-do-i-remove-microsoft-flow-from-the-app-launcher-for-my-organization"></a>Ricerca per categorie rimuovere Microsoft Flow dall'utilità di avvio delle app per la mia organizzazione?
Se a un utente è stata assegnata una licenza di Flow Plan 1 o Flow Plan 2, è possibile eseguire la procedura seguente per rimuovere la licenza di Flow per tale utente, in modo da rimuovere l'icona di flow dall'utilità di avvio dell'app:

1. Passare al [portale di amministrazione di Office 365](https://portal.microsoftonline.com/).
2. Nella barra di spostamento a sinistra selezionare **utenti**, quindi selezionare **utenti attivi**.
3. Trovare l'utente per cui si vuole rimuovere la licenza e quindi selezionarne il nome.
4. Nel riquadro dei dettagli utente, nella sezione **licenze prodotto** , selezionare **modifica**.
5. Trovare la licenza denominata **Microsoft Flow piano 1** o **Microsoft Flow piano 2**, impostare l'interruttore su **disattivato** e quindi selezionare **Salva**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Se un utente ha accesso a Flow attraverso la licenza di Office 365 e Dynamics 365 Plan, è possibile disabilitare l'accesso alle funzionalità aggiuntive incluse in questo piano attenendosi alla procedura seguente:

1. Passare al [portale di amministrazione di Office 365](https://portal.microsoftonline.com/).
2. Nella barra di spostamento a sinistra selezionare **utenti**, quindi selezionare **utenti attivi**.
3. Trovare l'utente per cui si vuole rimuovere l'accesso e quindi selezionarne il nome.
4. Nel riquadro dei dettagli utente, nella sezione **licenze prodotto** , selezionare **modifica**.
5. Espandere la licenza di Office 365 o Dynamics 365 dell'utente, disabilitare l'accesso al servizio denominato **Flow per Office 365** o **flow per Dynamics 365** , quindi selezionare **Salva**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

È possibile eseguire la rimozione in blocco delle licenze anche tramite PowerShell. Per un esempio dettagliato, vedere [rimuovere le licenze dagli account utente con Office 365 PowerShell](https://technet.microsoft.com/library/dn771774.aspx) .   Infine, è possibile trovare ulteriori indicazioni sulla rimozione in blocco dei servizi all'interno di una licenza in [disabilitare l'accesso ai servizi con Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

La rimozione della licenza o del servizio Flow per un utente dell'organizzazione comporterà la rimozione dell'icona di Flow dalle posizioni seguenti per l'utente:

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Utilità di avvio app di Office 365
   
   ![](./media/organization-q-and-a/office-waffle.png)

Si noti che il riquadro Flow verrà rimosso per impostazione predefinita. Un utente può comunque scegliere di usare Microsoft Flow come utente singolo.

### <a name="why-did-10000-licenses-for-microsoft-flow-show-up-in-my-office-365-tenant"></a>Perché le licenze 10.000 per Microsoft Flow vengono visualizzate nel tenant di Office 365?
Ogni persona può provare Microsoft Flow piano 1 o 2 per 90 giorni e queste licenze di valutazione rappresentano la capacità disponibile per i nuovi utenti di Flow nel tenant. Non sono previsti addebiti per queste licenze. In particolare, esistono due possibili motivi per cui è possibile che vengano visualizzate le licenze di capacità 10.000 (versione di valutazione) per il flusso visualizzato nel portale di amministrazione di Office 365:

1. Se almeno un utente nel tenant ha partecipato all'anteprima pubblica di Flow che si estende da aprile 2016 al 2016 ottobre, si vedranno 10.000 licenze con etichetta "Microsoft PowerApps e flussi logici".
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Se almeno un utente nel tenant ha effettuato l'iscrizione per una versione di valutazione del piano 2 di Flow con l' **opzione 1** per l'iscrizione alla versione di valutazione descritta nella sezione [come gli utenti si iscrivono a PowerApps,](#how-do-people-sign-up-for-flow) verranno visualizzate le licenze 10.000 "Microsoft Power Apps & Flow".
   
    ![](./media/organization-q-and-a/licenses1.png)

È possibile scegliere di assegnare licenze aggiuntive agli utenti tramite il portale di amministrazione di Office 365, ma si noti che si tratta di licenze di valutazione per Microsoft Flow piano 2 che scadranno dopo 90 giorni dall'assegnazione a un utente.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Questo è gratuito? Verranno addebitate le licenze?
Nessun utente può comportare alcun costo per l'organizzazione senza il consenso esplicito, quindi nessuna licenza gratuita o di valutazione può causare spese per l'organizzazione. Inoltre, non utilizzano quote, ad esempio le quote di esecuzione.

### <a name="i-removed-the-microsoft-flow-free-license-and-users-can-still-access-flow"></a>Sono state rimosse le Microsoft Flow licenze gratuite e gli utenti possono ancora accedere a Flow?
La licenza gratuita Microsoft Flow è inclusa solo a scopo di verifica. Come spiegato nella prima sezione, non è possibile impedire a un altro utente di usare Microsoft Flow per scopi individuali. In questo modo, la presenza di una licenza gratuita Microsoft Flow non concede né rimuove alcuna funzionalità.

### <a name="why-cant-i-see-all-flow-licenses-in-the-office-365-admin-portal"></a>Perché non è possibile visualizzare tutte le licenze Flow nel portale di amministrazione di Office 365?
Gli utenti possono usare Microsoft Flow come singoli utenti o come parte della propria organizzazione. Le licenze a livello di organizzazione saranno sempre visibili nel portale di Office 365. Tuttavia, se un utente si iscrive a una versione di valutazione come utente singolo, non viene gestito dall'amministratore di Office 365 e non verrà visualizzato nel portale.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>In che modo un utente individua il piano in cui si trovano?
Chiunque può visualizzare il piano di cui dispone visitando la pagina dei prezzi di Flow all' [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). Il piano o la versione di valutazione in cui si trovano attualmente verranno visualizzati.

### <a name="will-microsoft-flow-sign-up-impact-the-identities-in-my-organization"></a>Microsoft Flow iscrizione avrà un effetto sulle identità dell'organizzazione?
Se l'organizzazione dispone già di un ambiente Office 365 e tutti gli utenti dell'organizzazione hanno account di Office 365, la gestione delle identità non ha alcun impatto.

Se l'organizzazione ha già un ambiente di Office 365, ma non tutti gli utenti dell'organizzazione hanno account di Office 365, si crea un utente nel tenant e si assegnano le licenze in base all'indirizzo di posta elettronica aziendale o dell'Istituto di istruzione dell'utente. Ciò significa che il numero di utenti gestiti in un determinato momento aumenterà man mano che gli utenti dell'organizzazione si iscrivono al servizio.

Se l'organizzazione non dispone di un ambiente Office 365 connesso al dominio di posta elettronica, non viene modificata la modalità di gestione dell'identità. Gli utenti verranno aggiunti a una nuova directory di utenti solo cloud e sarà possibile assumere il nome di amministratore del tenant e gestirli.

### <a name="a-new-tenant-was-created-by-microsoft-flow-how-do-i-manage-this"></a>Un nuovo tenant è stato creato da Microsoft Flow, come posso gestirlo?
Se un nuovo tenant è stato creato da Microsoft Flow, è possibile richiedere e gestire tale tenant attenendosi alla procedura seguente:

1. Per aggiungere il tenant, iscriversi a Flow usando un dominio di indirizzo di posta elettronica corrispondente al dominio del tenant che si vuole gestire. Se ad esempio Microsoft ha creato il tenant contoso.com, aggiungere il tenant con un indirizzo di posta elettronica che termina con @contoso.com.
2. Richiedere il controllo di amministratore verificando la proprietà del dominio: una volta al tenant, è possibile alzarsi di livello al ruolo di amministratore verificando la proprietà del dominio. A tale scopo, attenersi alla seguente procedura:    
   
   1. Passare a [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free).
   2. Selezionare l'icona di avvio delle app in alto a sinistra e scegliere amministratore.
   3. Leggere le istruzioni nella pagina **diventare l'amministratore** e quindi scegliere **Sì, voglio essere l'amministratore**.  
      
       **Nota**: se questa opzione non viene visualizzata, è già presente un amministratore di Office 365.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Se si dispone di più domini, è possibile controllare il tenant di Office 365 a cui vengono aggiunti gli utenti?
Se non si esegue alcuna operazione, viene creato un tenant per ogni dominio di posta elettronica dell'utente e sottodominio.

Se si desidera che tutti gli utenti si trovino nello stesso tenant indipendentemente dalle estensioni degli indirizzi di posta elettronica:  

* Creare in anticipo un tenant di destinazione oppure usare un tenant esistente. Aggiungere tutti i domini e i sottodomini esistenti che si desidera consolidare in tale tenant. Tutti gli utenti con indirizzi di posta elettronica che terminano con questi domini e sottodomini vengono automaticamente aggiunti al tenant di destinazione quando si iscrivono.

**Importante**: non esiste alcun meccanismo automatizzato supportato per spostare gli utenti tra i tenant dopo che sono stati creati. Per informazioni sull'aggiunta di domini a un singolo tenant di Office 365, vedere [aggiungere utenti e domini a office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>Come è possibile limitare la capacità degli utenti di accedere ai dati aziendali dell'organizzazione?
Microsoft Flow consente di creare zone dati per i dati aziendali e non aziendali, come illustrato di seguito. Una volta implementati i criteri di prevenzione della perdita dei dati, agli utenti viene impedito di progettare o eseguire flussi che combinano dati aziendali e non aziendali. Per altri dettagli, vedere [criteri di prevenzione della perdita dei dati (DLP)](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

