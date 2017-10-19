In questo argomento, si apprenderà come eseguire flussi precedentemente pianificati usando un trigger chiamato **Ricorrenza**.  Si creerà un flusso per il team di marketing di Contoso che richiama automaticamente gli indirizzi di posta elettronica del cliente da una tabella di Excel in OneDrive. Si configurerà il flusso in modo che, i nuovi indirizzi di posta elettronica che sono stati aggiunti al foglio di calcolo vengano quindi aggiunti una volta al giorno a un elenco clienti di MailChimp. 

## <a name="create-a-scheduled-flow"></a>Creare un flusso pianificato
1. Aprire **Microsoft Flow**, selezionare **Flussi personali**, quindi selezionare **Crea da zero**. 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. Selezionare **Cerca tra centinaia di connettori e trigger**.
3. Cercare il servizio **Pianifica**, quindi selezionarlo e infine selezionare il trigger **Pianifica - Ricorrenza**.
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. Impostare **Frequenza** su **Giorno** e **Intervallo** su **1**. Selezionare **Nuovo passaggio** e scegliere **Aggiungi un'azione**. 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. Cercare **Excel**, selezionare il servizio **Excel** e quindi selezionare l'azione **Excel - Ottieni righe**. 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **Nota**: assicurarsi di selezionare **Ottieni righe**, non **Ottieni riga**. 
6. Selezionare **Nome file** e passare al percorso del file. Selezionare **Nome tabella** e selezionare la tabella desiderata nel foglio di calcolo. 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. Aggiungere una nuova azione. 
   
    ![](./media/learning-recurrence/new-step.png)
8. Cercare il servizio **MailChimp**, quindi selezionare l'azione **MailChimp - Aggiungi membro all'elenco**.
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **Nota:** MailChimp è un connettore *premium*. In base alla licenza di Microsoft Flow, per poter usare questo connettore potrebbe essere necessario effettuare l'iscrizione a una versione di valutazione.
9. Aggiungere i campi **Id lista** e **Stato** dai menu a discesa:
   
   * **Id lista**: selezionare la lista di distribuzione MailChimp desiderata
   * **Stato**: selezionare **Sottoscritto** 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. In **Indirizzo e-mail**, usare la funzionalità di contenuto dinamico per aggiungere il campo **Indirizzo posta elettronica contatto**. 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     Si noti che il flusso crea automaticamente un ulteriore passaggio. Flow rileva che si vuole impostare un'azione che richiede un'azione aggiuntiva. Ogni volta che il flusso legge un nuovo indirizzo di posta elettronica, creerà anche una nuova azione per ogni riga. 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. Usare il contenuto dinamico per compilare i campi **Nome** e **Cognome**:
    
    * **Nome**: Nome
    * **Cognome**: Cognome
      
      ![](./media/learning-recurrence/mailchimp-names.png)

Ora questo flusso verrà eseguito una volta al giorno e otterrà nuove righe da questa tabella di Excel, acquisirà l'indirizzo di posta elettronica e il nome e li userà per popolare la listra di distribuzione MailChimp per Contoso, risparmiando tempo e denaro. 

