---
title: Creare un ciclo di approvazione con la Common Data Service | Microsoft Docs
description: Creare un'entità, un flusso e un'app che interagiscono in modo che i revisori possano approvare o rifiutare i file aggiunti a Dropbox.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4f58e5b3095769349e71e9ba8b203ea678981391
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546839"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Creare un ciclo di approvazione utilizzando Microsoft Flow e Microsoft Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Il Common Data Service può fornire un modo per creare flussi con informazioni archiviate in un database indipendentemente da un flusso. L'esempio migliore è costituito dalle approvazioni. Se si archivia lo stato di approvazione in un'entità, il flusso può funzionare sopra di esso.

In questo esempio verrà creato un processo di approvazione che viene avviato quando un utente aggiunge un file a Dropbox. Quando viene aggiunto il file, le relative informazioni vengono visualizzate in un'app, in cui un revisore può approvare o rifiutare la modifica. Quando il revisore approva o rifiuta la modifica, viene inviato un messaggio di notifica e i file rifiutati vengono eliminati da Dropbox.

Seguendo i passaggi descritti in questa sezione, verrà compilato:

* **entità personalizzata** che conterrà informazioni su ogni file aggiunto a Dropbox e indica se lo stato del file è approvato, rifiutato o in sospeso.
* un **flusso** che aggiunge informazioni all'entità personalizzata quando un file viene aggiunto a Dropbox, invia un messaggio di posta elettronica quando il file viene approvato o rifiutato ed Elimina i file rifiutati. Questi passaggi illustrano come creare un flusso di questo tipo da zero, ma è possibile creare un flusso simile da un modello.
* **app** in cui un revisore può approvare o rifiutare i file aggiunti a Dropbox. Si userà PowerApps per generare automaticamente l'app in base ai campi nell'entità personalizzata.

**Prerequisiti**

* Iscriversi a [Microsoft Flow](sign-up-sign-in.md) e [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Creare connessioni a Dropbox e Office 365 Outlook, come descritto in [gestire le connessioni](https://powerapps.microsoft.com/tutorials/add-manage-connections/) .

## <a name="build-the-entity"></a>Compilare l'entità
1. Accedere a [powerapps.com](https://web.powerapps.com).
2. Se la barra di spostamento a sinistra non viene visualizzata per impostazione predefinita, toccare o fare clic sull'icona con tre linee orizzontali nell'angolo superiore sinistro.
   
    ![Apri barra di spostamento a sinistra](./media/common-data-model-approve/hamburger-icon.png)
3. Nella barra di spostamento a sinistra toccare o fare clic su **Gestisci**e quindi toccare o fare clic su **entità**.
   
    ![Gestisci entità](./media/common-data-model-approve/manage-entities.png)
4. Se richiesto, toccare o fare clic su **Crea il database**.
   
    ![Crea database](./media/common-data-model-approve/create-database.png)
5. Nell'angolo in alto a destra toccare o fare clic su **nuova entità**.
   
    ![Crea entità](./media/common-data-model-approve/new-entity.png)
   
    Se la finestra del browser non è ingrandita, questo pulsante potrebbe essere visualizzato in una posizione diversa.
6. In **nome entità**specificare un nome che non contenga spazi e che non siano presenti altre entità nel database.
   
    Per seguire esattamente questo esempio, specificare **ReviewDropboxFiles**.
   
    ![Specificare il nome dell'entità](./media/common-data-model-approve/entity-name.png)
7. In **nome visualizzato**specificare un nome descrittivo.
   
    ![Specifica nome visualizzato](./media/common-data-model-approve/display-name.png)
8. Toccare o fare clic su **Avanti**.
   
    ![Pulsante Avanti](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Aggiungere campi all'entità
1. Nell'angolo in alto a destra toccare o fare clic su **Aggiungi campo**.
   
    ![Aggiungi campo](./media/common-data-model-approve/add-field.png)
2. Nella riga vuota visualizzata nella parte inferiore dell'elenco di campi impostare le proprietà di un campo **responsabile approvazione** . (Quando si impostano queste proprietà, è possibile passare alla colonna successiva premendo TAB).
   
   * Nella colonna **nome visualizzato** digitare **responsabile approvazione**.
   * Nella colonna **nome** digitare **ApproverEmail**.
   * Nella colonna **tipo** toccare o fare clic sull'opzione **posta elettronica** .
   * Nella colonna **obbligatoria** selezionare la casella di controllo.
     
     ![Campo responsabile approvazione](./media/common-data-model-approve/approver-field.png)
3. Nella riga successiva, impostare le proprietà di un campo di **stato** :
   
   * Nella colonna **nome visualizzato** digitare **status**.
   * Nella colonna **nome** digitare **status**.
   * Nella colonna **tipo** scegliere o toccare l'opzione **testo** .
   * Nella colonna **Proprietà** lasciare il valore predefinito.
   * Nella colonna **obbligatoria** selezionare la casella di controllo.
     
     ![Campo stato](./media/common-data-model-approve/status-field.png)
4. Nella riga successiva, impostare le proprietà di un campo **fileid** :
   
   * Nella colonna **nome visualizzato** digitare identificatore del **file**.
   * Nella colonna **nome** digitare **fileid**.
   * Nella colonna **tipo** scegliere o toccare l'opzione **testo** .
   * Nella colonna **Proprietà** lasciare il valore predefinito.
   * Nella colonna **univoco** selezionare la casella di controllo.
   * Nella colonna **obbligatoria** selezionare la casella di controllo.
     
     ![Campo FileID](./media/common-data-model-approve/fileid-field.png)
5. Vicino al bordo destro toccare o fare clic sui puntini di sospensione (...) per il campo **fileid** e quindi toccare o fare clic su **Imposta come campo titolo**.
   
    ![Imposta campo titolo](./media/common-data-model-approve/set-title-field.png)
6. Nell'angolo in basso a sinistra toccare o fare clic su **Crea**.
   
    ![Creare un'entità](./media/common-data-model-approve/create-button.png)
7. opzionale Quando viene visualizzato l'elenco delle entità, ingrandire la finestra del browser se non è ancora ingrandita e quindi toccare o fare clic sull'intestazione di colonna **tipo** . L'elenco viene ordinato con le entità personalizzate, ad esempio quella appena creata, visualizzate nella parte superiore.

## <a name="sign-in-and-create-a-flow"></a>Accedere e creare un flusso
1. Aprire il [portale di Microsoft Flow](https://flow.microsoft.com).
2. Ingrandire la finestra del browser se non è ancora ingrandita, quindi toccare o fare clic su Accedi vicino all'angolo **in** alto a destra.
   
    ![Pulsante di accesso per Microsoft Flow](./media/common-data-model-approve/signin-flow.png)
3. Nel menu in alto a destra selezionare l'ambiente in cui è stato creato il database in powerapps.com.
   
    **Nota**: se non si seleziona lo stesso ambiente, l'entità non verrà visualizzata.
4. Nell'angolo in alto a sinistra toccare o fare clic su **flussi personali**.
   
    ![Pulsante flussi personali](./media/common-data-model-approve/myflows-button.png)
5. Nell'angolo in alto a destra toccare o fare clic su **Crea nuovo flusso**.
   
    ![Pulsante Crea nuovo flusso](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Inizia quando viene aggiunto un file
1. Nella casella che contiene **Cerca altri trigger**Digitare o incollare **Dropbox**e quindi fare clic o toccare **Dropbox-quando viene creato un file**.
   
    ![Crea trigger](./media/common-data-model-approve/create-trigger.png)
2. In **cartella**toccare o fare clic sull'icona della cartella e quindi passare alla cartella in cui verranno aggiunti i file.
   
    ![Scegli cartella](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Aggiungere dati all'entità
1. Toccare o fare clic su **nuovo passaggio**e quindi toccare o fare clic su **Aggiungi un'azione**.
   
    ![Aggiungi un'azione](./media/common-data-model-approve/add-action.png)
2. Nella casella contenente **cercare altre azioni**Digitare o incollare **Common Data Service**e quindi fare clic o toccare **Common Data Service-crea oggetto**.
   
    ![Creare un oggetto nel Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. In **entità**Digitare o incollare la **Revisione**e quindi fare clic o toccare **Controlla file Dropbox**.
   
    ![Scegliere l'entità](./media/common-data-model-approve/choose-entity-flow.png)
4. In **titolo**toccare o fare clic sulla casella e quindi toccare o fare clic su **nome file** nell'elenco dei token di parametro per aggiungere tale token al campo.
   
    ![Aggiungi token nome file](./media/common-data-model-approve/add-filename-token.png)
5. In **responsabile approvazione**Digitare o incollare l'indirizzo di posta elettronica della persona che esaminerà i file.
   
    **Nota**: per semplificare il test del flusso, specificare un indirizzo personalizzato. È possibile modificarlo in un secondo momento, quando il flusso è pronto per l'uso effettivo.
   
    ![Aggiungi responsabile approvazione](./media/common-data-model-approve/add-approver.png)
6. In **stato**Digitare o incollare **in sospeso**.
   
    ![Aggiungi stato predefinito](./media/common-data-model-approve/add-default-status.png)
7. In **identificatore file**fare clic o toccare nella casella e quindi toccare o fare clic su **identificatore file** nell'elenco dei token di parametro per aggiungere tale token al campo.
   
    ![Aggiungi token identificatore file](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Controllare se il file è stato rivisto
1. Nell'azione **Crea oggetto** toccare o fare clic su **nuovo passaggio**, toccare o fare clic su **altro**e quindi toccare o fare clic su **Aggiungi un do fino a**.
   
    ![Aggiungi do until](./media/common-data-model-approve/add-do-until.png)
2. Nell'angolo in alto a sinistra dell'azione **Esegui fino a** fare clic o toccare nella casella che contiene **scegliere un valore**.
   
    ![Scegliere un valore](./media/common-data-model-approve/choose-value.png)
   
    **Nota**: se la finestra del browser non è ingrandita, fare clic o toccare nella casella superiore che contiene **scegliere un valore**.
3. In **output da Crea oggetto**toccare o fare clic su **stato** per aggiungere il token del parametro al campo.
   
    ![Aggiungi token di stato](./media/common-data-model-approve/add-status.png)
4. Aprire l'elenco accanto al centro dell'azione **Esegui fino a** , quindi fare clic o toccare **non è uguale a**.
   
    ![Specificare non è uguale a](./media/common-data-model-approve/is-not-equal.png)
5. Nell'angolo in alto a destra dell'azione **Esegui fino a** Digitare o incollare in **sospeso** nella casella che contiene **scegliere un valore**.
   
    ![Specificare lo stato da controllare](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Nota**: se la finestra del browser non è ingrandita, fare clic o toccare nella casella inferiore che contiene **scegliere un valore**.
6. Nella parte inferiore dell'azione **Esegui fino a** fare clic o toccare **Aggiungi un'azione**.
   
    ![Aggiungere un'azione all'interno di un Do Until](./media/common-data-model-approve/add-action-in-dountil.png)
7. Nella casella contenente **cercare altre azioni**digitare **Common**e quindi toccare o fare clic su **Common Data Service-Get Object**.
   
    ![Ottenere un oggetto](./media/common-data-model-approve/get-object.png)
8. **Nello spazio dei nomi**toccare o fare clic sul database.
9. In **entità**Digitare o incollare la **Revisione**e quindi fare clic o toccare **Controlla file Dropbox**.
   
    ![Scegliere un'entità](./media/common-data-model-approve/choose-entity-flow.png)
10. In **ID oggetto**fare clic o toccare nella casella e quindi toccare o fare clic sul token del parametro **identificatore file** per aggiungerlo al campo.
    
     ![Aggiungi identificatore oggetto](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Verificare se l'elemento è stato approvato
1. Sotto l'azione **Do-Until** , fare clic o toccare **nuovo passaggio**, quindi fare clic o toccare **Aggiungi una condizione**.
   
    ![Aggiungi condizione](./media/common-data-model-approve/add-condition.png)
2. Nell'angolo in alto a sinistra della condizione fare clic o toccare nella casella che contiene **scegliere un valore**.
   
    ![Angolo superiore sinistro della condizione](./media/common-data-model-approve/condition-upper-left.png)
   
    **Nota**: se la finestra del browser non è ingrandita, fare clic o toccare nella casella superiore che contiene **scegliere un valore**.
3. In **output da ottenere oggetto**toccare o fare clic sul token del parametro **status** per aggiungerlo al campo.
   
    ![Aggiungere lo stato alla condizione](./media/common-data-model-approve/add-status-to-condition.png)
4. Nell'angolo in alto a destra della condizione digitare o incollare **approvato** nella casella che contiene **scegliere un valore**.
   
    ![Verificare se lo stato è impostato su approvato](./media/common-data-model-approve/status-equals-approved.png)
   
    **Nota**: se la finestra del browser non è ingrandita, digitare o incollare **approvato** nella casella inferiore che contiene **scegliere un valore**.

## <a name="send-notification-mail"></a>Invia posta elettronica di notifica
1. In **se sì, non fare nulla**, toccare o fare clic su **Aggiungi un'azione**.
   
    ![Se sì, Aggiungi un'azione](./media/common-data-model-approve/if-yes-action.png)
2. Nella casella contenente **cercare altre azioni**Digitare o incollare **Invia messaggio**e quindi toccare o fare clic su **Office 365 Outlook-invia un messaggio di posta elettronica**.
   
    ![In caso affermativo, inviare un messaggio di posta elettronica](./media/common-data-model-approve/if-yes-send-mail.png)
3. In **a**Digitare o incollare l'indirizzo della persona a cui si desidera inviare una notifica quando un elemento viene accettato.
   
    **Nota**: per semplificare il test del flusso, specificare un indirizzo personalizzato. È possibile modificarlo quando il flusso è pronto per l'uso effettivo.
   
    ![Destinatario approvazione](./media/common-data-model-approve/approval-recipient.png)
4. In **oggetto**, fare clic o toccare nella casella e quindi toccare o fare clic sul token del parametro **nome file** per aggiungerlo al campo.
   
    ![Specificare il nome del file come oggetto del messaggio di posta elettronica](./media/common-data-model-approve/subject-is-file-name.png)
5. In **corpo**Digitare o incollare **l'elemento approvato.**
   
    ![Corpo del messaggio di approvazione](./media/common-data-model-approve/approval-body.png)
6. In **se no, non eseguire alcuna**operazione, ripetere i passaggi 1-5 in questa procedura, eccetto specificare il corpo del messaggio di posta elettronica perché **l'elemento è stato rifiutato.**
   
    ![Corpo del messaggio di posta elettronica di rifiuto](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Elimina file rifiutati
1. Nei campi del messaggio di rifiuto, fare clic o toccare **Aggiungi un'azione**.
   
    ![Aggiungi azione Delete](./media/common-data-model-approve/add-delete-action.png)
2. Nella casella contenente **cercare altre azioni**Digitare o incollare **Dropbox**e quindi fare clic o toccare **Dropbox-Elimina file**.
   
    ![Elimina file da Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. In **file**fare clic o toccare nella casella e quindi scegliere o toccare il parametro token **identificatore file** per aggiungerlo al campo.
   
    ![Identificare il file da eliminare](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Salvare il flusso
1. Nella parte superiore della schermata digitare o incollare un nome per il flusso che si sta creando e quindi fare clic o toccare **Crea flusso**.
   
    ![Salva flusso](./media/common-data-model-approve/save-flow.png)
2. Toccare o fare clic su **Chiudi** e quindi toccare **o fare clic su fine.**
3. In Dropbox aggiungere almeno due file alla cartella specificata: uno per testare l'approvazione e uno per il test del rifiuto.

## <a name="build-the-app"></a>compilare l'app
1. Accedere a [powerapps.com](https://web.powerapps.com)e quindi toccare o fare clic su **nuova app** nella parte inferiore della barra di spostamento a sinistra.
   
    ![Creare un'app in un browser](./media/common-data-model-approve/new-app-button.png)
2. Nella finestra di dialogo visualizzata toccare o fare clic sull'opzione per aprire PowerApps Studio per Windows o PowerApps Studio per il Web.
3. Se è stato aperto PowerApps Studio per Windows, toccare o fare clic su **nuovo** nella barra di spostamento a sinistra.
4. In **creare un'app dai dati**toccare o fare clic su **layout del telefono** nel riquadro **Common Data Service** .
   
    ![Crea app](./media/common-data-model-approve/afd-cdm.png)
5. Nella casella di **ricerca** Digitare o incollare **Review**.
   
    ![Ricerca di un'entità](./media/common-data-model-approve/search-entities.png)
6. In **scegliere un'entità**toccare o fare clic su **rivedere i file di Dropbox**.
   
    ![Scegliere un'entità](./media/common-data-model-approve/choose-entity.png)
7. Nell'angolo in basso a destra toccare o fare clic su **Connetti**.
   
    ![Pulsante Connetti](./media/common-data-model-approve/connect-button.png)
8. Se viene visualizzata la schermata iniziale della presentazione introduttiva, seguire la presentazione per acquisire familiarità con PowerApps (oppure toccare o fare clic su **Ignora**).
   
    ![Presentazione introduttiva](./media/common-data-model-approve/quick-tour.png)
   
    È sempre possibile seguire la presentazione in un secondo momento toccando o facendo clic sull'icona del punto interrogativo nell'angolo in alto a sinistra e quindi toccando o facendo clic su **Take The Intro Tour (presentazione introduttiva**).
9. opzionale Nella parte inferiore della schermata trascinare il dispositivo di scorrimento per aumentare lo zoom in modo da visualizzare più facilmente l'app.
   
    ![Controllo zoom](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Personalizzare l'app
1. Nella barra di spostamento a destra toccare o fare clic sul layout che include un'intestazione e una descrizione.
   
    ![Pulsante Connetti](./media/common-data-model-approve/choose-layout.png)
2. In **BrowseScreen**toccare o fare clic sulla barra di ricerca per selezionare il controllo della casella di testo più grande.
   
    ![Seleziona intestazione](./media/common-data-model-approve/select-header.png)
3. Nel riquadro di destra aprire l'elenco inferiore facendo clic o toccando la freccia verso il basso.
   
    ![Apri elenco a discesa](./media/common-data-model-approve/open-dropdown.png)
4. Nell'elenco inferiore toccare o fare clic su **title (titolo** ) per visualizzare il nome del file aggiunto.
   
    ![Imposta dati intestazione](./media/common-data-model-approve/set-heading.png)
5. Nel riquadro di destra aprire l'elenco superiore e quindi toccare o fare clic su **stato** per visualizzare lo stato di ogni file.
   
    ![Imposta i dati del corpo](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Testare la soluzione complessiva
1. In PowerApps aprire la modalità di anteprima toccando o facendo clic sul pulsante di riproduzione nell'angolo in alto a sinistra.
   
    ![Apri modalità di anteprima](./media/common-data-model-approve/open-preview.png)
2. Per il primo file nell'elenco, toccare o fare clic sulla freccia per visualizzare i dettagli relativi a tale file.
   
    ![Apri schermata dei dettagli](./media/common-data-model-approve/open-details.png)
3. Nell'angolo in alto a destra toccare o fare clic sull'icona a forma di matita per modificare i dettagli del file.
   
    ![Apri schermata di modifica](./media/common-data-model-approve/edit-record.png)
4. Nella casella **stato** Digitare o incollare **approvato**.
   
    ![Approva un file](./media/common-data-model-approve/change-status.png)
5. Nell'angolo in alto a destra toccare o fare clic sull'icona del segno di spunta per salvare le modifiche e tornare alla schermata dei dettagli.
   
    ![Salva modifiche](./media/common-data-model-approve/save-record.png)
   
    In pochi minuti, si riceverà un messaggio di posta elettronica che informa che il file è stato approvato.
6. Nell'angolo in alto a destra toccare o fare clic sul pulsante indietro per tornare alla schermata di esplorazione.
   
    ![Torna alla schermata di esplorazione](./media/common-data-model-approve/back-arrow.png)
7. Per l'altro file nell'elenco, toccare o fare clic sulla freccia per visualizzare i dettagli relativi a tale file.
   
    ![Apri schermata dei dettagli](./media/common-data-model-approve/open-details.png)
8. Nell'angolo in alto a destra toccare o fare clic sull'icona a forma di matita per modificare i dettagli del file.
   
    ![Apri schermata di modifica](./media/common-data-model-approve/edit-record.png)
9. Nella casella **stato** Digitare o incollare **rifiutato** (o qualsiasi elemento eccetto **approvato**, incluso **aproved** o **approovato**).
   
    ![Rifiuta file](./media/common-data-model-approve/reject-file.png)
10. Nell'angolo in alto a destra toccare o fare clic sull'icona del segno di spunta per salvare le modifiche e tornare alla schermata dei dettagli.
    
     ![Salva modifiche](./media/common-data-model-approve/save-record.png)
    
     In pochi minuti, si riceverà un messaggio di posta elettronica che informa che il file è stato rifiutato e che il file verrà eliminato da Dropbox.

