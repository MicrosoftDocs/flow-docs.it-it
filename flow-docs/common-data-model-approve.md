---
title: Creare un ciclo di approvazione con Common Data Service | Microsoft Docs
description: Creare un'entità, un flusso e un'app che interagiscano in modo che i revisori possano approvare o rifiutare i file aggiunti a Dropbox.
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
ms.openlocfilehash: 6c48d79138dfdafa94e56380343840d6aa0fcbb5
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690876"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Creazione di un ciclo di approvazione tramite Microsoft Flow e Microsoft Common Data Service
Common Data Service può rappresentare un modo per creare flussi di informazioni archiviate in un database indipendente di un flusso. L'esempio migliore è con le approvazioni. Se si archivia lo stato di approvazione in un'entità, è possibile sovrapporre il flusso.

In questo esempio, si creerà un processo di approvazione che viene avviato quando un utente aggiunge un file a Dropbox. Quando il file viene aggiunto, le relative informazioni vengono visualizzate in un'app, in cui un revisore può approvare o rifiutare la modifica. Quando il revisore approva o rifiuta la modifica, viene inviato un messaggio di notifica e i file rifiutati vengono eliminati da Dropbox.

Seguendo i passaggi descritti in questa sezione, si procederà a creare:

* un'**entità personalizzata** che conterrà le informazioni relative ai singoli file aggiunti a Dropbox e indicherà se lo stato del file è approvato, rifiutato o in sospeso.
* un **flusso** che aggiunge informazioni all'entità personalizzata quando viene aggiunto un file in Dropbox, invia messaggi quando il file viene approvato o rifiutato ed elimina i file rifiutati. Questa procedura illustra come compilare tale flusso da zero, ma è possibile creare un flusso simile da un modello.
* un'**app** in cui un revisore può approvare o rifiutare i file aggiunti a Dropbox. Si userà PowerApps per generare questa app automaticamente in base ai campi nell'entità personalizzata.

**Prerequisiti**

* Iscriversi a [Microsoft Flow](sign-up-sign-in.md) e [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Creare connessioni a Dropbox e Office 365 Outlook, come descritto in [Gestire le connessioni](https://powerapps.microsoft.com/tutorials/add-manage-connections/).

## <a name="build-the-entity"></a>Creare l'entità
1. Accedere a [powerapps.com](https://web.powerapps.com).
2. Se non viene visualizzata la barra di spostamento a sinistra per impostazione predefinita, scegliere o toccare l'icona con tre linee orizzontali in alto a sinistra.
   
    ![Aprire la barra di spostamento a sinistra](./media/common-data-model-approve/hamburger-icon.png)
3. Nella barra di spostamento a sinistra, scegliere o toccare **Gestisci**, quindi scegliere o toccare **Entità**.
   
    ![Gestire le entità](./media/common-data-model-approve/manage-entities.png)
4. Se richiesto, scegliere o toccare **Crea il database personale**.
   
    ![Creare il database](./media/common-data-model-approve/create-database.png)
5. In alto a destra, scegliere o toccare **Nuova entità**.
   
    ![Creare un'entità](./media/common-data-model-approve/new-entity.png)
   
    Se la finestra del browser non è ingrandita, questo pulsante potrebbe essere visualizzato in una posizione diversa.
6. In **Nome entità**, specificare un nome che non contenga spazi e che non sia stato assegnato ad altre entità nel database.
   
    Per seguire esattamente questo esempio, specificare **ReviewDropboxFiles**.
   
    ![Specificare il nome dell'entità](./media/common-data-model-approve/entity-name.png)
7. In **Nome visualizzato** specificare un nome descrittivo.
   
    ![Specificare il nome visualizzato](./media/common-data-model-approve/display-name.png)
8. Scegliere o toccare **Avanti**.
   
    ![Pulsante Avanti](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Aggiungere campi all'entità
1. In alto a destra, scegliere o toccare **Aggiungi campo**.
   
    ![Aggiungere un campo](./media/common-data-model-approve/add-field.png)
2. Nella riga vuota che viene visualizzata nella parte inferiore dell'elenco di campi, impostare le proprietà di un campo **Approver**. Per spostarsi alla colonna successiva durante l'impostazione delle proprietà, premere TAB.
   
   * Nella colonna **Nome visualizzato** digitare **Approver**.
   * Nella colonna **Nome** digitare **ApproverEmail**.
   * Nella colonna **Tipo** scegliere o toccare l'opzione **Email**.
   * Nella colonna **Obbligatorio** selezionare la casella di controllo.
     
     ![Campo Approver](./media/common-data-model-approve/approver-field.png)
3. Nella riga successiva, impostare le proprietà di un campo **Stato**:
   
   * Nella colonna **Nome visualizzato** digitare **Stato**.
   * Nella colonna **Nome** digitare **Stato**.
   * Nella colonna **Tipo** scegliere o toccare l'opzione **Text**.
   * Nella colonna **Proprietà** lasciare il valore predefinito.
   * Nella colonna **Obbligatorio** selezionare la casella di controllo.
     
     ![Campo Stato](./media/common-data-model-approve/status-field.png)
4. Nella riga successiva, impostare le proprietà di un campo **FileID**:
   
   * Nella colonna **Nome visualizzato** digitare **Identificatore file**.
   * Nella colonna **Nome** digitare **FileID**.
   * Nella colonna **Tipo** scegliere o toccare l'opzione **Text**.
   * Nella colonna **Proprietà** lasciare il valore predefinito.
   * Nella colonna **Unico** selezionare la casella di controllo.
   * Nella colonna **Obbligatorio** selezionare la casella di controllo.
     
     ![Campo FileID](./media/common-data-model-approve/fileid-field.png)
5. Vicino al bordo destro, scegliere o toccare i puntini di sospensione (...) per il campo **FileID** e quindi scegliere o toccare **Imposta come campo Titolo**.
   
    ![Imposta come campo Titolo](./media/common-data-model-approve/set-title-field.png)
6. In basso a sinistra, scegliere o toccare **Crea**.
   
    ![Creare un'entità](./media/common-data-model-approve/create-button.png)
7. (facoltativo) Quando l'elenco di entità verrà visualizzato, ingrandire la finestra del browser se non lo è già e quindi scegliere o toccare l'intestazione di colonna **Tipo**. L'elenco viene ordinato con le entità personalizzate, ad esempio quella appena creata, visualizzate nella parte superiore.

## <a name="sign-in-and-create-a-flow"></a>Accedere e creare un flusso
1. Aprire il [portale di Microsoft Flow](https://flow.microsoft.com).
2. Ingrandire la finestra del browser se non lo è già e quindi scegliere o toccare **Accedi** in alto a destra.
   
    ![Pulsante Accedi per Microsoft Flow](./media/common-data-model-approve/signin-flow.png)
3. Su powerapps.com, nel menu in alto a destra selezionare l'ambiente in cui è stato creato il database.
   
    **Nota**: se non si seleziona lo stesso ambiente, non verrà visualizzata l'entità.
4. In alto a sinistra, scegliere o toccare **Flussi personali**.
   
    ![Pulsante Flussi personali](./media/common-data-model-approve/myflows-button.png)
5. In alto a destra, scegliere o toccare **Crea nuovo flusso**.
   
    ![Pulsante Crea nuovo flusso](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Iniziare quando viene aggiunto un file
1. Nella casella contenente **Cerca altri trigger** digitare o incollare **Dropbox** e quindi scegliere o toccare **Dropbox - Quando viene creato un file**.
   
    ![Creare un trigger](./media/common-data-model-approve/create-trigger.png)
2. In **Cartella**, scegliere o toccare l'icona della cartella e quindi passare alla cartella in cui i file verranno aggiunti.
   
    ![Scegliere la cartella](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Aggiungere dati all'entità
1. Scegliere o toccare **Nuovo passaggio**, quindi scegliere o toccare **Aggiungi un'azione**.
   
    ![Aggiungere un'azione](./media/common-data-model-approve/add-action.png)
2. Nella casella con la scritta **Cercare altre azioni** digitare o incollare **Common Data Service** e quindi scegliere o toccare **Common Data Service - Crea oggetto**.
   
    ![Creazione di un oggetto in Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. In **The entity (Entità)**, digitare o incollare **Review (Revisione)**, e quindi scegliere o toccare **Review Dropbox files (Revisione file Dropbox)**.
   
    ![Scegliere l'entità](./media/common-data-model-approve/choose-entity-flow.png)
4. In **Titolo**, fare clic o toccare nella casella e quindi scegliere o toccare il parametro token **Nome file** nell'elenco per aggiungerlo al campo.
   
    ![Aggiungere token Nome file](./media/common-data-model-approve/add-filename-token.png)
5. In **Approver (Revisore)**, digitare o incollare l'indirizzo di posta elettronica della persona che esaminerà i file.
   
    **Nota**: per rendere più semplice il test del flusso, specificare il proprio indirizzo. È possibile modificarlo in un secondo momento, quando il flusso sarà pronto per l'uso effettivo.
   
    ![Aggiungere l'approvatore](./media/common-data-model-approve/add-approver.png)
6. In **Stato** digitare o incollare **In sospeso**.
   
    ![Aggiungere lo stato predefinito](./media/common-data-model-approve/add-default-status.png)
7. In **Identificatore file**, fare clic o toccare nella casella e quindi scegliere o toccare il parametro token **Identificatore file** nell'elenco per aggiungerlo al campo.
   
    ![Aggiungere token Identificatore file](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Controllare se il file è stato rivisto
1. Nell'azione **Crea oggetto** scegliere o toccare **Nuovo passaggio**, scegliere o toccare **Altro** e quindi scegliere o toccare **Aggiungi un'azione fino a**.
   
    ![Aggiungere un'azione fino a](./media/common-data-model-approve/add-do-until.png)
2. In alto a sinistra dell'azione **Esegui fino a** fare clic su o toccare la casella che contiene **Scegliere un valore**.
   
    ![Scegliere un valore](./media/common-data-model-approve/choose-value.png)
   
    **Nota**: se la finestra del browser non è ingrandita, fare clic o toccare nella casella superiore che contiene **Scegliere un valore**.
3. In **Output da Crea oggetto** scegliere o toccare il parametro token **Stato** per aggiungerlo al campo.
   
    ![Aggiungere token Stato](./media/common-data-model-approve/add-status.png)
4. Aprire l'elenco al centro dell'azione **Esegui fino a**, quindi scegliere o toccare **non è uguale a**.
   
    ![Specificare non è uguale a](./media/common-data-model-approve/is-not-equal.png)
5. In alto a destra dell'azione **Esegui fino a** digitare o incollare **In sospeso** nella casella che contiene **Scegliere un valore**.
   
    ![Specifica lo stato per il controllo](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Nota**: se la finestra del browser non è ingrandita, fare clic o toccare nella casella inferiore che contiene **Scegliere un valore**.
6. Nella parte inferiore dell'azione **Esegui fino a** scegliere o toccare **Aggiungi un'azione**.
   
    ![Aggiungere un'azione all'interno di Esegui fino a](./media/common-data-model-approve/add-action-in-dountil.png)
7. Nella casella contenente **Cercare altre azioni** digitare **Common** e quindi scegliere o toccare **Common Data Service - Ottieni oggetto**.
   
    ![Ottenere un oggetto](./media/common-data-model-approve/get-object.png)
8. In **The namespace** scegliere o toccare il database.
9. In **The entity (Entità)**, digitare o incollare **Review (Revisione)**, e quindi scegliere o toccare **Review Dropbox files (Revisione file Dropbox)**.
   
    ![Scegliere un'entità](./media/common-data-model-approve/choose-entity-flow.png)
10. In **ID oggetto**, fare clic o toccare nella casella e quindi scegliere o toccare il parametro token **Identificatore file** per aggiungerlo al campo.
    
     ![Aggiungere l'identificatore di oggetto](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Controllare se l'elemento è stato approvato
1. Nell'azione **Esegui fino a** scegliere o toccare **Nuovo passaggio**, quindi scegliere o toccare **Aggiungi una condizione**.
   
    ![Aggiungere una condizione](./media/common-data-model-approve/add-condition.png)
2. In alto a sinistra della condizione fare clic o toccare nella casella che contiene **Scegliere un valore**.
   
    ![Angolo superiore sinistro della condizione](./media/common-data-model-approve/condition-upper-left.png)
   
    **Nota**: se la finestra del browser non è ingrandita, fare clic o toccare nella casella superiore che contiene **Scegliere un valore**.
3. In **Output da Ottieni oggetto** scegliere o toccare il parametro token **Stato** per aggiungerlo al campo.
   
    ![Aggiungere lo stato alla condizione](./media/common-data-model-approve/add-status-to-condition.png)
4. In alto a destra della condizione digitare o incollare **Approvato** nella casella che contiene **Scegliere un valore**.
   
    ![Verificare se lo stato è impostato su Approvato](./media/common-data-model-approve/status-equals-approved.png)
   
    **Nota**: se la finestra del browser non è ingrandita, digitare o incollare **Approvato** nella casella inferiore che contiene **Scegliere un valore**.

## <a name="send-notification-mail"></a>Inviare messaggio di notifica
1. In **Se sì, non fare nulla** scegliere o toccare **Aggiungi un'azione**.
   
    ![Se sì, aggiungere un'azione](./media/common-data-model-approve/if-yes-action.png)
2. Nella casella contenente **Cercare altre azioni** digitare o incollare **invia messaggio** e quindi scegliere o toccare **Office 365 Outlook - Invia un messaggio di posta elettronica**.
   
    ![Se sì, invia e-mail](./media/common-data-model-approve/if-yes-send-mail.png)
3. In **A**, digitare o incollare l'indirizzo della persona a cui si vuole inviare una notifica quando viene accettato un elemento.
   
    **Nota**: per rendere più semplice il test del flusso, specificare il proprio indirizzo. È possibile modificarlo quando il flusso sarà pronto per l'uso effettivo.
   
    ![Destinatario di approvazione](./media/common-data-model-approve/approval-recipient.png)
4. In **Oggetto**, fare clic o toccare nella casella e quindi scegliere o toccare il parametro token **Nome file** per aggiungerlo al campo.
   
    ![Specificare il nome del file come oggetto del messaggio di posta elettronica](./media/common-data-model-approve/subject-is-file-name.png)
5. In **Corpo** digitare o incollare **The item has been approved (L'elemento è stato approvato)**.
   
    ![Corpo del messaggio di posta elettronica di approvazione](./media/common-data-model-approve/approval-body.png)
6. In **Se no, non fare nulla** ripetere i passaggi da 1 a 5 in questa procedura, ma specificare il corpo del messaggio di posta elettronica come **The item has been rejected (L'elemento è stato rifiutato)**.
   
    ![Corpo del messaggio di posta elettronica di rifiuto](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Eliminare i file rifiutati
1. Nei campi del messaggio di rifiuto, scegliere o toccare **Aggiungi un'azione**.
   
    ![Aggiungere azione di eliminazione](./media/common-data-model-approve/add-delete-action.png)
2. Nella casella contenente **Cercare altre azioni** digitare o incollare **Dropbox** e quindi scegliere o toccare **Dropbox - Elimina file**.
   
    ![Eliminare file da Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. In **File**, fare clic o toccare nella casella e quindi scegliere o toccare il parametro token **Identificatore file** per aggiungerlo al campo.
   
    ![Identificare il file da eliminare](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Salvare il flusso
1. Nella parte superiore della schermata, digitare o incollare un nome per il flusso che si sta creando, quindi scegliere o toccare **Crea flusso**.
   
    ![Salvare il flusso](./media/common-data-model-approve/save-flow.png)
2. Scegliere o toccare **Chiudi**, quindi scegliere o toccare **Fine**.
3. In Dropbox, aggiungere almeno due file nella cartella specificata: uno per eseguire il test di approvazione e uno per testare il rifiuto.

## <a name="build-the-app"></a>Compilare l'app
1. Accedere a [powerapps.com](https://web.powerapps.com), quindi scegliere o toccare **Nuova app** nella parte inferiore della barra di spostamento a sinistra.
   
    ![Creare un'app in un browser](./media/common-data-model-approve/new-app-button.png)
2. Nella finestra di dialogo visualizzata, scegliere o toccare l'opzione per aprire PowerApps Studio per Windows o PowerApps Studio per il Web.
3. Se è stato aperto PowerApps Studio per Windows, scegliere o toccare **Nuovo** nella barra di spostamento a sinistra.
4. In **Create an app from your data** (Crea un'app dai dati) scegliere o toccare **Layout Telefono** nel riquadro **Common Data Service**.
   
    ![Creare un'app](./media/common-data-model-approve/afd-cdm.png)
5. Nella casella **Ricerca** digitare o incollare **Review (Revisione)**.
   
    ![Cercare un'entità](./media/common-data-model-approve/search-entities.png)
6. in **Scegliere un'entità** scegliere o toccare **Review Dropbox Files (Revisione file Dropbox)**.
   
    ![Scegliere un'entità](./media/common-data-model-approve/choose-entity.png)
7. In basso a destra, scegliere o toccare **Connetti**.
   
    ![Pulsante Connetti](./media/common-data-model-approve/connect-button.png)
8. Se viene visualizzata la schermata iniziale della presentazione introduttiva, eseguirla per acquisire familiarità con PowerApps (oppure scegliere o toccare **Ignora**).
   
    ![Presentazione introduttiva](./media/common-data-model-approve/quick-tour.png)
   
    È sempre possibile eseguire la presentazione in un secondo momento scegliendo o toccando l'icona di punto interrogativo in alto a sinistra e quindi scegliendo o toccando **Presentazione introduttiva**.
9. (facoltativo) Nella parte inferiore della schermata, trascinare il dispositivo di scorrimento per ingrandire e visualizzare più facilmente l'app.
   
    ![Controllo zoom](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Personalizzare l'app
1. Nella barra di navigazione a destra, scegliere o toccare il layout che include un'intestazione e una descrizione.
   
    ![Pulsante Connetti](./media/common-data-model-approve/choose-layout.png)
2. Nella **SchermataEsplora** scegliere o toccare poco sotto la barra di ricerca per selezionare il controllo della casella di testo.
   
    ![Selezionare l'intestazione](./media/common-data-model-approve/select-header.png)
3. Nel riquadro di destra, aprire l'elenco inferiore scegliendo o toccando la freccia GIÙ.
   
    ![Aprire l'elenco a discesa](./media/common-data-model-approve/open-dropdown.png)
4. Nell'elenco in basso, scegliere o toccare **Titolo** per mostrare il nome file dei file aggiunti.
   
    ![Impostare i dati di intestazione](./media/common-data-model-approve/set-heading.png)
5. Nel riquadro di destra, aprire l'elenco superiore, quindi scegliere o toccare **Stato** per visualizzare lo stato di ogni file.
   
    ![Impostare i dati del corpo](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Testare la soluzione complessiva
1. In PowerApps, aprire la modalità di anteprima scegliendo o toccando il pulsante di riproduzione in alto a sinistra.
   
    ![Aprire la modalità di anteprima](./media/common-data-model-approve/open-preview.png)
2. Per il primo file nell'elenco, scegliere o toccare la freccia per visualizzare i dettagli su tale file.
   
    ![Aprire la schermata dei dettagli](./media/common-data-model-approve/open-details.png)
3. In alto a destra, scegliere o toccare l'icona a forma di matita per modificare i dettagli relativi al file.
   
    ![Aprire la schermata di modifica](./media/common-data-model-approve/edit-record.png)
4. Nella casella **Stato** digitare o incollare **Approvato**.
   
    ![Approvare un file](./media/common-data-model-approve/change-status.png)
5. In alto a destra, scegliere o toccare l'icona del segno di spunta per salvare le modifiche e tornare alla schermata dei dettagli.
   
    ![Salvare le modifiche](./media/common-data-model-approve/save-record.png)
   
    In pochi minuti, si riceverà un messaggio di posta elettronica che informa che il file è stato approvato.
6. In alto a destra, scegliere o toccare il pulsante Indietro per tornare alla schermata di navigazione.
   
    ![Tornare alla schermata di navigazione](./media/common-data-model-approve/back-arrow.png)
7. Per l'altro file nell'elenco, scegliere o toccare la freccia per visualizzare i dettagli su tale file.
   
    ![Aprire la schermata dei dettagli](./media/common-data-model-approve/open-details.png)
8. In alto a destra, scegliere o toccare l'icona a forma di matita per modificare i dettagli relativi al file.
   
    ![Aprire la schermata di modifica](./media/common-data-model-approve/edit-record.png)
9. Nella casella **Stato** digitare o incollare **Rifiutato** (o qualsiasi altra cosa tranne **Approvato**, inclusi **Aprovato** o **Approovato**).
   
    ![Rifiutare il file](./media/common-data-model-approve/reject-file.png)
10. In alto a destra, scegliere o toccare l'icona del segno di spunta per salvare le modifiche e tornare alla schermata dei dettagli.
    
     ![Salvare le modifiche](./media/common-data-model-approve/save-record.png)
    
     In pochi minuti, si riceverà un messaggio di posta elettronica che informa che il file è stato rifiutato e che verrà eliminato da Dropbox.

