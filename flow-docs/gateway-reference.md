---
title: Informazioni sui gateway dati locali | Microsoft Docs
description: Informazioni di riferimento, installazione e risoluzione dei problemi per i gateway dati locali
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: af2e113278f480eb3c748cb1a2f9a81e34d32258
ms.sourcegitcommit: a35abc6a2148cbfb48ca36d4af09bfd90eaffa42
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2019
ms.locfileid: "55647853"
---
# <a name="understand-on-premises-data-gateways-for-microsoft-flow"></a>Comprendere i gateway dati locali per Microsoft Flow
Usare il gateway dati locale con Microsoft Flow per stabilire connessioni protette alle origini dati locali, ad esempio Microsoft SQL Server.

## <a name="installation-and-configuration"></a>Installazione e configurazione
### <a name="prerequisites"></a>Prerequisiti
Minimo:

* [.NET Framework 4.6](https://www.microsoft.com/download/details.aspx?id=48130)
* Versione a 64 bit di Windows 7 o Windows Server 2008 R2 (o versioni successive)

Consigliato:

* CPU 8 core
* 8 GB di memoria
* Versione a 64 bit di Windows Server 2012 R2 (o versioni successive)

Considerazioni correlate:

* Il gateway non può essere installato in un controller di dominio.
* È consigliabile non installare un gateway in un computer, ad esempio un portatile, che può essere disattivato, sospeso o non connesso a Internet.
* Le prestazioni del gateway potrebbero peggiorare su una rete wireless.

## <a name="install-a-gateway"></a>Installare un gateway
> [!IMPORTANT]
> I gateway di dati di Microsoft SharePoint ora supportano il traffico sia HTTP che HTTPS.
> 
> 

1. [Scaricare il programma di installazione](https://go.microsoft.com/fwlink/?LinkID=820931), quindi eseguirlo.
   
    ![Eseguire il programma di installazione](./media/gateway-reference/run-installer.png)
2. Nella prima schermata dell'installazione guidata, selezionare **Avanti** per confermare il promemoria sull'installazione di un gateway in un computer portatile.
   
    ![Schermata di promemoria](./media/gateway-reference/laptop-reminder.png)
3. Selezionare il percorso di installazione.
4. Accettare le condizioni per l'utilizzo e l'informativa sulla privacy.
5. Selezionare **Installa**.
   
    ![schermata di percorso](./media/gateway-reference/location.png)
6. Nelle finestre di dialogo **Controllo dell'account utente** selezionare **Sì** per continuare.
7. Nella schermata **Gateway dati locale** immettere l'indirizzo e-mail per l'account che si userà per accedere al gateway, selezionare **Accedi**, quindi completare la procedura di accesso.
   
    ![Accedi](./media/gateway-reference/sign-in.png)

## <a name="register-new-gateway-or-take-over-existing-gateway"></a>Registrare il nuovo gateway o assumere il controllo del gateway esistente
1. Selezionare **Consente di registrare un nuovo gateway in questo computer** oppure **Eseguire la migrazione, ripristinare o acquisire la proprietà di un gateway esistente**, quindi selezionare **Avanti**.
   
    ![Scegliere nuovo o esistente](./media/gateway-reference/new-existing.png)
2. Per configurare un nuovo gateway, immettere un nome nella casella **Nuovo nome del gateway dati locale**, immettere una chiave di ripristino nella casella **Chiave di ripristino**, immettere la stessa chiave di ripristino nella casella **Conferma chiave di ripristino**. Selezionare **Configura**, quindi selezionare **Chiudi**.
   
    ![Configurare un nuovo gateway](./media/gateway-reference/configure-new.png)
3. Specificare una chiave di ripristino di almeno otto caratteri e conservarla in un luogo sicuro. Questa chiave è necessaria se si vuole per eseguire la migrazione, ripristinare o acquisire la proprietà di un gateway.
4. Per eseguire la migrazione, ripristinare o acquisire la proprietà di un gateway esistente, specificare il nome del gateway e la relativa chiave di ripristino, selezionare **Configura**, quindi seguire le istruzioni aggiuntive.
   
    ![Ripristinare un gateway esistente](./media/gateway-reference/recover-existing.png)

## <a name="restart-the-gateway"></a>Riavviare il gateway
Il gateway viene eseguito come servizio Windows e, come con qualsiasi altro servizio di Windows, è possibile avviarlo e arrestarlo in diversi modi. Ad esempio, è possibile aprire un prompt dei comandi con autorizzazioni elevate nel computer in cui il gateway è in esecuzione e quindi eseguire questi comandi:

* Per arrestare il servizio, eseguire questo comando:

```batchfile
    net stop PBIEgwService
```

* Per avviare il servizio, eseguire questo comando:

```batchfile
    net start PBIEgwService
```

## <a name="configure-a-firewall-or-proxy"></a>Configurare un firewall o proxy
Per informazioni su come fornire informazioni sul proxy per il gateway, vedere [Configurare le impostazioni proxy](https://powerbi.microsoft.com/documentation/powerbi-gateway-proxy/).

È possibile verificare se il firewall, o proxy, potrebbe star bloccando le connessioni eseguendo il comando seguente da un prompt dei comandi di PowerShell. Questo comando esegue il test della connettività al bus di servizio di Azure. Questo comando verifica solo la connettività di rete e non influisce sul servizio server cloud o sul gateway. Consente di determinare se il computer ha la connettività a Internet.

```powershell
Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350
```

I risultati dovrebbero essere simili all'output seguente. Se **TcpTestSucceeded** non è *true*, il computer potrebbe essere bloccato da un firewall.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Per completezza, sostituire i valori **NomeComputer** e **Porta** con quelli elencati in **Configurare porte** più avanti in questo argomento.

Anche il firewall potrebbe bloccare le connessioni tra il bus di servizio di Azure e il data center di Azure. In tal caso, è opportuno inserire nell'elenco elementi consentiti (sbloccare) tutti gli [indirizzi IP](https://www.microsoft.com/download/details.aspx?id=41653) per la propria area per tali data center.

## <a name="configure-ports"></a>Configurare le porte
Il gateway crea una connessione in uscita al bus di servizio di Azure. Comunica sulle porte in uscita TCP 443 (predefinita), 5671, 5672 e da 9350 a 9354. Il gateway non richiede porte in ingresso.

Altre informazioni sulle [soluzioni ibride](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/).

| Nomi di dominio | Porte in uscita | Descrizione |
| --- | --- | --- |
| *.analysis.windows.net |443 |HTTPS |
| *.login.microsoftonline.com |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Listener in Inoltro del bus di servizio su TCP (è richiesta la porta 443 per l'acquisizione del token di Controllo di accesso) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *.msftncsi.com |443 |Usato per testare la connettività a internet se il gateway non è raggiungibile. |

Se è necessario creare un elenco di indirizzi consentiti anziché di domini, è possibile scaricare e usare l'[elenco di intervalli IP dei data center di Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653). In alcuni casi, le connessioni del bus di servizio di Azure verranno stabilite con l'indirizzo IP anziché con i nomi di dominio completo.

## <a name="sign-in-account"></a>Account di accesso
Gli utenti eseguiranno l'accesso con un account aziendale o dell'istituto di istruzione. Questo è l'account aziendale. Se è stata effettuata l'iscrizione per un'offerta di Office 365 senza specificare l'indirizzo di posta elettronica dell'ufficio, questo può apparire come nancy@contoso.onmicrosoft.com. All'interno di un servizio cloud, l'account viene archiviato in un tenant di Azure Active Directory (AAD). Nella maggior parte dei casi, l'UPN dell'account AAD corrisponderà all'indirizzo di posta elettronica.

## <a name="windows-service-account"></a>Account del servizio Windows
Il gateway dati locale è configurato in modo da usare *NT SERVICE\PBIEgwService* per le credenziali di accesso al servizio Windows. Per impostazione predefinita, ha il diritto Accedi come servizio a seconda del contesto del computer su cui si sta installando il gateway.

Questo non è l'account usato per connettersi alle origini dati locali. Non si tratta neanche dell'account aziendale o dell'istituto di istruzione con cui si accede ai servizi cloud.

## <a name="tenant-level-administration"></a>Amministrazione a livello di tenant

Non è attualmente disponibile alcuna posizione centralizzata da cui gli amministratori tenant possano gestire tutti i gateway installati e configurati da altri utenti.  Per gli amministratori tenant è consigliabile chiedere agli utenti dell'organizzazione di essere aggiunti come amministratore in ogni gateway installato. In questo modo è possibile gestire tutti i gateway all'interno dell'organizzazione tramite la pagina Impostazioni gateway oppure tramite i [comandi di PowerShell](https://docs.microsoft.com/power-bi/service-gateway-high-availability-clusters#powershell-support-for-gateway-clusters).

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="general-questions"></a>Domande generali
**Domanda:** quali origini dati supporta il gateway?
**Risposta:**

* SQL Server
* SharePoint
* Oracle
* Informix
* Filesystem
* DB2

**Domanda:** è necessario un gateway per origini dati nel cloud come SQL Azure?
**Risposta:** No. Un gateway si connette solo a origini dati locali.

**Domanda:** è necessario installare il gateway nell'ambiente predefinito?
**Risposta:** sì, Microsoft Flow supporta solo i gateway installati nell'ambiente predefinito.

**Domanda:** qual è il nome effettivo del servizio di Windows?
**Risposta:** in Servizi, il gateway si chiama **Power BI Enterprise Gateway Service**.

**Domanda:** sono presenti connessioni in ingresso verso il gateway dal cloud?
**Risposta:** No. Il gateway usa connessioni in uscita al bus di servizio di Azure.

**Domanda:** cosa succede se si bloccano le connessioni in uscita? Cosa occorre aprire?
**Risposta:** vedere l'elenco di [porte](gateway-reference.md#configure-ports) e host usati dal gateway.

**Domanda:** il gateway deve essere installato nello stesso computer dell'origine dati?
**Risposta:** No. Il gateway si connetterà all'origine dati usando le informazioni di connessione fornite. In questo senso il gateway è simile a un'applicazione client. È solo necessario che riesca a connettersi allo stesso nome server specificato.

**Domanda:** qual è la latenza per l'esecuzione di query in un'origine dati dal gateway? Qual è l'architettura migliore?
**Risposta:**  è consigliabile che il gateway si trovi il più vicino possibile all'origine dati, in modo da evitare la latenza di rete. Se è possibile installare il gateway nell'origine dati effettiva, si ridurrà al minimo la latenza introdotta. Prendere in considerazione anche i data center. Se, ad esempio, il servizio usa il data center Stati Uniti occidentali e SQL Server è ospitato in una macchina virtuale di Azure, è consigliabile posizionare anche la macchina virtuale di Azure negli Stati Uniti occidentali. In questo modo si minimizza la latenza e si evitano addebiti in uscita sulla macchina virtuale di Azure.

**Domanda:** sono previsti requisiti per la larghezza di banda di rete?
**Risposta:** è consigliabile mantenere una velocità effettiva ottimale per la connessione di rete. Ogni ambiente è diverso e questo valore dipende anche dalla quantità di dati inviati. L'uso di ExpressRoute può essere utile per assicurare un livello specifico di velocità effettiva tra l'ambiente locale e i data center di Azure.

È possibile usare l'[app Azure Speed Test](http://azurespeedtest.azurewebsites.net/) di terze parti per determinare la velocità effettiva.

**Domanda:** il servizio di Windows Gateway può essere eseguito con un account Azure Active Directory?
**Risposta:** No. Il servizio di Windows deve avere un account di Windows valido. Per impostazione predefinita, verrà eseguito con SID del servizio *NT SERVICE\PBIEgwService*.

**Domanda:** in che modo i risultati vengono inviati al cloud?
**Risposta:** i risultati vengono inviati con il bus di servizio di Azure. Per altre informazioni, vedere la [sezione relativa al funzionamento](gateway-reference.md#how-the-gateway-works).

**Domanda:** dove vengono archiviate le credenziali?
**Risposta:** le credenziali immesse per un'origine dati vengono crittografate e archiviate nel servizio cloud gateway. Le credenziali vengono decrittografate nel gateway locale.

### <a name="high-availabilitydisaster-recovery"></a>Disponibilità elevata/Ripristino di emergenza
**Domanda:** sono disponibili piani per l'abilitazione di scenari a disponibilità elevata con il gateway?
**Risposta:** sì, la disponibilità elevata è [ora disponibile](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each).

**Domanda:** quali opzioni sono disponibili per il ripristino di emergenza?
**Risposta:** è possibile usare la chiave di ripristino per ripristinare o spostare un gateway.

**Domanda:** qual è il vantaggio della chiave di ripristino?
**Risposta:** consente di eseguire la migrazione o di ripristinare le impostazioni del gateway.

### <a name="troubleshooting-questions"></a>Domande sulla risoluzione dei problemi
**Domanda:** dove si trovano i log del gateway?
**Risposta:** vedere la sezione [Strumenti](gateway-reference.md#tools) più avanti in questo argomento.

**Domanda:** in che modo è possibile visualizzare le query inviate all'origine dati locale?
**Risposta:** è possibile abilitare la traccia della query, che includerà le query inviate. Occorre ricordare di ripristinare il valore originale al termine della risoluzione dei problemi. L'abilitazione della traccia della query comporterà la creazione di log di dimensioni maggiori.

È anche possibile verificare gli strumenti disponibili nell'origine dati per tenere traccia delle query. Per SQL Server e Analysis Services è ad esempio possibile usare Extended Events o SQL Profiler.

## <a name="how-the-gateway-works"></a>Come funziona il gateway
![Come funziona](./media/gateway-reference/gateway-arch.png)

Questa sezione descrive cosa accade quando un utente interagisce con un elemento connesso a un'origine dati locale.

1. Il servizio cloud crea una query insieme alle credenziali crittografate per l'origine dati locale, che verrà quindi inviata alla coda di elaborazione nel gateway.
2. Il servizio cloud gateway analizzerà la query e invierà la richiesta al [bus di servizio di Azure](https://azure.microsoft.com/documentation/services/service-bus/).
3. Il gateway dati locale esegue il polling delle richieste in sospeso sul bus di servizio di Azure.
4. Il gateway riceve la query, decrittografa le credenziali e si connette all'origine o alle origini dati con tali credenziali.
5. Il gateway invia la query all'origine dati per l'esecuzione.
6. I risultati vengono inviati dall'origine dati al gateway, quindi al servizio cloud. Il servizio usa quindi i risultati.

## <a name="troubleshooting"></a>Risoluzione dei problemi
### <a name="update-to-the-latest-version"></a>Aggiornare alla versione più recente
Quando la versione del gateway non è aggiornata, possono verificarsi molti problemi. Verificare di avere la versione più recente.  Se il gateway non è stato aggiornato di recente, potrebbe essere utile provare a installare la versione più recente e provare a riprodurre il problema.

#### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Errore: Non è stato possibile aggiungere l'utente al gruppo.  (-2147463168   PBIEgwService   Performance Log Users   )
Questo errore può verificarsi se si sta provando a installare il gateway in un controller di dominio. La distribuzione in un controller di dominio non è supportata. Il gateway deve essere installato in un computer che non sia un controller di dominio.

## <a name="tools"></a>Strumenti
### <a name="collecting-logs-from-the-gateway-configurator"></a>Raccolta di registri dallo strumento di configurazione del gateway
Esistono vari registri che è possibile raccogliere per il gateway. Iniziare sempre con i registri.

1. Registri di installazione
   
    %localappdata%\Temp\On-premises_data_gateway_*.log
2. Registri di configurazione
   
    %localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log
3. Registri eventi del gateway dati locale
   
    C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log
4. Registri eventi

I registri eventi del **servizio gateway dati locale** sono presenti in **Registri applicazioni e servizi**.

![Registri eventi](./media/gateway-reference/event-logs.png)

### <a name="fiddler-trace"></a>Traccia di Fiddler
[Fiddler](http://www.telerik.com/fiddler) è uno strumento gratuito di Telerik che monitora il traffico HTTP.  È possibile visualizzare il traffico dal servizio Power BI al computer client e viceversa. Potrebbero essere illustrati errori e altre informazioni correlate.

