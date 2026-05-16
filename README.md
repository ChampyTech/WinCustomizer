## WinCustomizer

### 1. Descrizione generale

WinCustomizer è uno script Batch (.bat) per Windows 11 progettato per automatizzare la manutenzione, ottimizzare le prestazioni, tutelare la privacy e personalizzare l'interfaccia utente. Combina comandi CMD nativi, modifiche al registro di sistema e cmdlet PowerShell.

### 2. Prerequisiti

* Richiede i privilegi di amministratore. Integra un controllo nativo (`net session`) che blocca l'esecuzione e mostra le istruzioni di sblocco in caso di privilegi insufficienti.
* Richiede il gestore pacchetti `winget` attivo per il modulo app e PowerShell 5.1 o superiore.

### 3. Struttura dei moduli

#### Modulo 1: Manutenzione sistema

* Verifica e ripara i file e l'immagine di sistema tramite i tool diagnostici `sfc /scannow` e `DISM`.
* Rimuove i file temporanei (`Temp`/`Prefetch`), svuota il Cestino, resetta le cache di Windows Update e del Microsoft Store, e cancella i log del Visualizzatore Eventi.
* Svuota il DNS e resetta il catalogo Winsock per risolvere i problemi di rete.
* Disabilita il file di ibernazione e applica la compressione di sistema LZX (`compactos`) per recuperare spazio.

#### Modulo 2: Privacy e telemetria

* Blocca la raccolta dati e la telemetria di Windows, Microsoft Edge e della suite Office tramite il registro.
* Disattiva Cortana e la ricerca web di Bing integrata nel menu Start.
* Interrompe la geolocalizzazione, l'ID annunci, il tracciamento dell'avvio app e la cronologia attività.
* Rimuove i permessi di accesso automatico in background a fotocamera e microfono per le app UWP.

#### Modulo 3: Personalizzazione UI

* Permette di alternare tra il menu contestuale classico (stile Windows 10) e quello moderno (Windows 11).
* Gestisce la Taskbar consentendo l'allineamento delle icone (sinistra/centro), la modalità piccola e la rimozione di widget, chat e ricerca.
* Configura Esplora File per mostrare le estensioni dei file, gli elementi nascosti e impostare l'apertura su "Questo PC".
* Gestisce Dark/Light Mode, disattiva animazioni, trasparenze e suoni, rimuove il testo "- Collegamento" e la filigrana hardware.
* Crea la cartella "God Mode" sul desktop e disabilita la schermata di blocco. Ogni comando esegue il riavvio istantaneo di `explorer.exe`.

#### Modulo 4: Ottimizzazione performance

* Attiva il piano energetico "Prestazioni Eccellenti" e disabilita il *Power Throttling* della CPU.
* Ottimizza i parametri per il gaming abilitando la *Game Mode*, disattivando il Game DVR e abilitando l'HAGS (GPU Scheduling).
* Disabilita i servizi di indicizzazione (`WSearch`) e `SysMain` (Superfetch) per alleggerire disco e RAM.
* Riduce il timeout di chiusura delle app bloccate in fase di spegnimento e aumenta la priorità di CPU e GPU nel registro.

#### Modulo 5: Gestione app

* Disinstalla via PowerShell i bloatware e i software sponsorizzati preinstallati, inclusa la rimozione forzata di OneDrive.
* Utilizza `winget` per installare in modalità silenziosa i software essenziali (browser, player, utility e sviluppo) e aggiornare centralitamente tutti i programmi.
* Ripristina il Microsoft Store in caso di errori, sblocca l'installazione di app da qualsiasi fonte e pulisce gli installer orfani nella cartella MSI.

#### Modulo 6: Sicurezza

* Forza l'aggiornamento delle firme di Windows Defender e avvia una scansione rapida del sistema.
* Attiva l'accesso controllato alle cartelle contro i Ransomware e abilita l'isolamento del core per l'integrità della memoria.
* Blocca l'esecuzione di script dannosi esterni disabilitando Windows Script Host e attiva la protezione anti-PUA.
* Impedisce a Windows Update di sovrascrivere i driver hardware stabili e verifica lo stato della licenza OS.

### 4. Linee guida per la sicurezza

* Si raccomanda la creazione di un punto di ripristino prima dell'uso, date le modifiche al registro.
