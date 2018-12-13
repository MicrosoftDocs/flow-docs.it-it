Considerando la continua espansione dell'elenco dei [servizi](https://flow.microsoft.com/services) disponibili per la creazione di flussi di lavoro con [Microsoft Flow](https://flow.microsoft.com), potrebbe risultare necessario proteggere i dati business sensibili o critici archiviati in servizi aziendali come SharePoint o Salesforce. È possibile che l'organizzazione abbia l'esigenza di creare criteri per assicurarsi che i dati business sensibili non vengano pubblicati in servizi per gli utenti come Twitter e Facebook. Con Microsoft Flow, è possibile creare facilmente criteri di **prevenzione della perdita dei dati** (DLP) per esercitare un maggiore controllo sui servizi per gli utenti con cui è possibile condividere i dati business, quando gli utenti creano flussi.  

## <a name="terms-you-should-get-familiar-with"></a>Terminologia da conoscere

| Termine | Descrizione |
| --- | --- |
| **DLP** |Acronimo di Data Loss Prevention, ovvero prevenzione della perdita dei dati. I criteri DLP vengono creati per gestire la condivisione dei dati tra i **servizi**. |
| **Servizi** |I [servizi](https://flow.microsoft.com/services) sono applicazioni come Salesforce, SharePoint e Twitter. Questi servizi, e molti altri, vengono usati per creare flussi. |
| **Gruppo di dati** |Raggruppamento logico di servizi. I servizi che possono condividere dati vengono inseriti nello stesso gruppo di dati. Esistono due gruppi di dati: **Business data only** (Solo dati business) e **No business data allowed** (Nessun dato business consentito). |
| **Ambiente** |I criteri DLP vengono applicati a un [ambiente](../environments-overview-admin.md). Un ambiente contiene utenti. |
| **Utenti** |Gli utenti sono i membri dell'organizzazione a cui vengono applicati i criteri DLP, in base all'appartenenza in un ambiente. |
| **Flusso** |Un flusso è un'app per flussi di lavoro che usa una qualsiasi combinazione dei servizi disponibili. |

## <a name="all-about-how-dlp-policies-work"></a>Tutto sul funzionamento dei criteri DLP
Un criterio DLP è semplicemente una regola denominata che inserisce ogni servizio in uno dei due gruppi di dati che si escludono a vicenda. Questa regola viene applicata a un ambiente. Un ambiente è un raggruppamento logico di utenti. Gli utenti non sono autorizzati a creare flussi che condividono dati tra i servizi inseriti in gruppi di dati diversi. In altre parole, gli utenti possono solo creare flussi che condividono i dati tra i servizi all'interno di un **singolo** gruppo di dati. Non è consentita la condivisione tra gruppi di dati diversi.  

| **Nome del gruppo di dati** | **Descrizione del gruppo dei dati** |
| --- | --- |
| **Business data only** (Solo dati business) |Tutti i servizi in questo gruppo possono condividere dati tra loro, ma non possono condividere dati con il gruppo **No business data allowed**. |
| **No Business data allowed** (Nessun dato business consentito) |Tutti i servizi in questo gruppo possono condividere dati tra loro, ma non possono condividere dati con il gruppo **Business data only**. |

**Nota**: L'aggiunta di un servizio a un gruppo di dati ne comporta la rimozione automatica dall'altro gruppo. Ad esempio, se Twitter è incluso nel gruppo di dati **Business data only** e non si vuole consentire la condivisione dei dati business con Twitter, è sufficiente aggiungere il servizio Twitter al gruppo di dati **No Business data allowed**. Twitter verrà così rimosso dal gruppo **Business data only**.

## <a name="heres-what-you-need-to-create-a-dlp"></a>Ecco cosa occorre per creare un criterio DLP
* Accesso all'[interfaccia di amministrazione](https://admin.flow.microsoft.com) di Microsoft Flow  
* Un account nel ruolo di amministratore dell'ambiente  
* Un ambiente con utenti assegnati  

## <a name="create-a-dlp-policy"></a>Creare criteri DLP
Ecco una rapida panoramica della procedura per creare criteri DLP:  

1. Assegnare un nome al criterio
2. Selezionare l'ambiente a cui verrà applicato il criterio
3. Aggiungere i servizi a uno dei due gruppi di dati Tenere presente che solo i servizi che si trovano in un gruppo specifico possono condividere dati, pertanto qualsiasi flusso creato per condividere dati tra servizi inclusi nei due gruppi di dati verrà bloccato automaticamente quando viene salvato dall'autore.  

Per i criteri DLP è disponibile anche una [procedura dettagliata](../prevent-data-loss.md).  

## <a name="examples"></a>Esempi
* Si supponga di voler creare un criterio per limitare i flussi alla condivisione dei dati business tra SharePoint, Office 365, Office 365 Outlook, OneDrive for Business, Dynamics 365, SQL Server e Salesforce. L'aspetto sarebbe simile al seguente:  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* Ecco l'aspetto che avrebbe se si decidesse di creare un criterio per non consentire ad alcun membro di un ambiente specifico di creare un flusso per condividere i dati di SharePoint. Si noti che SharePoint è l'unico servizio incluso nel gruppo di dati **Business data only**:  
  ![Business data only](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

