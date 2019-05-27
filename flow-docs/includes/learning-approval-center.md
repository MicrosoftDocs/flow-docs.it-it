---
ms.openlocfilehash: 431bb579e19f89132f5ea0ca772a89ea17988de2
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463420"
---
In un argomento precedente, è stato illustrato come potenziare i feed di Twitter in un modo semplice con un elenco di SharePoint. In questo argomento si apprenderà come creare uno scenario più efficiente usando le approvazioni. In questo modo, chiunque abbia accesso all'elenco di SharePoint può contribuire con i tweet e il team di social networking potrà approvare o rifiutare tali tweet. Il team mantiene il controllo dell'account e del contenuto che viene pubblicato per i clienti. 

## <a name="create-an-approval-request-flow"></a>Creare un flusso di richiesta di approvazione
1. Nella home page di **Microsoft Flow**, selezionare **Approvazioni**, selezionare **Crea flusso di lavoro** e quindi scorrere verso il basso e selezionare il modello **Pubblica gli elementi elenco in Twitter dopo l'approvazione**. 
   
    ![Selezionare il modello](./media/learning-approval-center/create-approval.png)
2. Verificare le credenziali dell'account per **SharePoint**, **Approvazioni** e **Twitter**, quindi selezionare **Continua**. 
   
    ![Verificare le credenziali](./media/learning-approval-center/verify-credentials.png)

Per impostazione predefinita, questo modello avvia un processo di approvazione quando viene creato un nuovo elemento in un elenco specifico e, se questo viene approvato, pubblica un tweet su Twitter. In questo argomento si modificherà questo processo aggiungendo i passaggi per aggiornare l'elenco di SharePoint con la risposta di approvazione, indicare se è stata approvata o no e aggiungere eventuali commenti del responsabile approvazione al tweet proposto. 

1. Nell'elenco **Tweet di Contoso** creato in precedenza, aggiungere due nuove colonne:
   
   1. Selezionare il segno più "**+**", quindi selezionare **Sì/No**
   2. Immettere **StatoApprovazione** e selezionare **Crea**
   3. Selezionare il segno più "**+**", quindi selezionare **Singola riga di testo**
   4. Immettere **CommentiResponsabile** e selezionare **Salva**
      
      ![Aggiungere colonne](./media/learning-approval-center/new-columns.png)
2. Tornando a **Microsoft Flow**, nell'azione **Quando viene creato un nuovo elemento**, immettere i valori seguenti:
   
   * **Indirizzo sito**: l'URL del team di SharePoint
   * **Nome elenco**: ContosoTweets
     
     ![Sito ed elenco](./media/learning-approval-center/site-address.png)
3. Nell'azione **Avviare un'approvazione**, selezionare **Modifica** per visualizzare tutti i campi. 
   
    ![Modificare i campi](./media/learning-approval-center/edit-all-fields.png)
4. In **Titolo**, immettere **Nuovo tweet per** e selezionare **Titolo** dall'elenco del contenuto dinamico. 
   
    ![Titolo](./media/learning-approval-center/tweet-title.png)
5. In **Assegnato a**, immettere e selezionare il proprio nome o un nome utente di test. 
   
    ![Assegnato a](./media/learning-approval-center/tweet-assigned-to.png)
6. In **Dettagli**, rimuovere gli elementi predefiniti e aggiungere **ContenutoTweet**, **DataTweet** e **Creato da NomeVisualizzato** dall'elenco del contenuto dinamico, connesso delle parole **il** e **da**. 
   
    ![Dettagli](./media/learning-approval-center/tweet-details.png)
7. In **Collegamento all'elemento** copiare e incollare l'URL dell'elenco di SharePoint e immettere **Elenco tweet di Contoso** in **Descrizione collegamento all'elemento**. 
   
    ![Collegamento all'elemento](./media/learning-approval-center/tweet-item-link.png)
8. Nell'azione **Condizione** passare con il mouse sopra la casella **SE SÌ**, selezionare il segno più "**+**" e infine selezionare **Aggiungi un'azione**. 
   
    ![Aggiungere un'azione](./media/learning-approval-center/add-an-action.png)
9. Cercare **Aggiorna elemento**, selezionare il connettore **SharePoint**, quindi selezionare l'azione **SharePoint - Aggiorna elemento**.
   
    ![Aggiorna elemento di SharePoint](./media/learning-approval-center/update-item.png)
10. In **Indirizzo sito** e **Nome elenco** immettere di nuovo l'URL del sito e l'elenco **TweetDiContoso**, quindi immettere **ID** in **ID** dall'elenco del contenuto dinamico. 
    
     ![Sito, elenco e ID](./media/learning-approval-center/address-list-id.png)
11. Selezionare il campo **Titolo** e, nell'elenco del contenuto dinamico, cercare **Titolo**. Aggiungere l'elemento **Titolo** dall'azione **Quando viene creato un nuovo elemento**. 
    
     ![Nuovo titolo](./media/learning-approval-center/add-title.png)
12. Selezionare **StatoApprovazione** e impostare il valore su **Sì**, quindi selezionare **CommentiResponsabile** e impostare il valore su **Commenti** dall'elenco del contenuto dinamico. 
    
     ![Stato e commenti](./media/learning-approval-center/approver-status.png)
13. Nella parte inferiore della casella **SE NO, NON FARE NULLA**, selezionare **Aggiungi un'azione**.
    
     ![Aggiungere un'azione in caso di no](./media/learning-approval-center/add-a-no-action.png)
14. Usando la stessa procedura impiegata per la configurazione di **SE SÌ**, creare un'azione **SharePoint - Aggiorna elemento** e configurare i campi con gli stessi valori, ad eccezione dell'impostazione **StatoApprovazione** su **No**. 
    
     ![Stato = no](./media/learning-approval-center/status-no.png)
15. Selezionare l'azione **Pubblica un tweet**, selezionare **Modifica** e impostare **Testo tweet** su **ContenutoTweet** dall'elenco del contenuto dinamico.  Nella parte superiore della pagina, selezionare **Crea flusso** per salvare il lavoro. 
    
     ![Pubblicare e salvare](./media/learning-approval-center/post-tweet.png)

Questo è solo uno dei modi in cui Microsoft Flow può incrementare la produttività del team. Il team può contribuire con idee, notizie pertinenti o materiale sussidiario sul prodotto ed è comunque possibile mantenere il controllo sul contenuto che viene pubblicato su Twitter per i clienti.

Nell'argomento successivo, si vedrà cosa succede quando un responsabile approvazione riceve una nuova richiesta per un tweet proposto. 

