## WinCustomizer

### 1. Descrizione generale

WinCustomizer è uno script Batch avanzato (.bat) progettato per l'automazione, la manutenzione, l'ottimizzazione delle performance, la tutela della privacy e la personalizzazione dell'interfaccia utente (UI) su sistemi operativi Windows 11. Lo script combina comandi nativi CMD, modifiche dirette al Registro di Sistema (`reg.exe`) e cmdlet PowerShell.

### 2. Requisiti di sistema

* È richiesto il sistema operativo Windows 11 (alcuni tweak sono retrocompatibili con Windows 10).
* Richiede tassativamente l'esecuzione con privilegi di amministratore; lo script integra un controllo nativo (`net session`) che blocca l'esecuzione e mostra le istruzioni di sblocco in caso di privilegi insufficienti.
* Richiede il gestore pacchetti `winget` attivo per il modulo di gestione applicativi e una versione di PowerShell 5.1 o superiore.

### 3. Funzionalità

#### Modulo 1: Manutenzione sistema

* Esegue i tool diagnostici `sfc /scannow` e `DISM` per verificare e riparare l'integrità dei file e dell'immagine di sistema.
* Rimuove i file temporanei dalle cartelle `Temp` e `Prefetch`, svuota forzatamente il Cestino e cancella la cache di Windows Update e del Microsoft Store.
* Svuota il DNS, resetta il catalogo Winsock per risolvere problemi di rete e cancella i log del Visualizzatore Eventi.
* Disabilita il file di ibernazione per recuperare spazio su disco e applica la compressione di sistema tramite algoritmo LZX (`compactos`).

#### Modulo 2: Privacy e Telemetria

* Disabilita la raccolta dati e la telemetria nativa di Windows, del browser Microsoft Edge e della suite Office tramite chiavi di registro dedicate.
* Disattiva l'assistente vocale Cortana e la ricerca web di Bing integrata nel menu Start.
* Interrompe i servizi di geolocalizzazione, disabilita l'ID annunci, il tracciamento dell'avvio app e la cronologia attività (*Activity Feed*).
* Rimuove i permessi di accesso automatico in background a fotocamera e microfono per le applicazioni UWP.

#### Modulo 3: Personalizzazione UI (Interfaccia Utente)

* Ripristina il menu contestuale classico dello stile Windows 10 o reimposta quello moderno predefinito di Windows 11.
* Gestisce la Taskbar consentendo l'allineamento delle icone a sinistra o al centro, il ridimensionamento in modalità piccola e la rimozione di widget, chat e icone di ricerca.
* Modifica il comportamento di Esplora File forzando la visualizzazione delle estensioni dei file noti, mostrando elementi nascosti e impostando l'apertura su "Questo PC" invece di "Home".
* Applica modifiche estetiche come l'attivazione di Dark/Light Mode, la rimozione del suffisso "- Collegamento", la disattivazione di animazioni, trasparenze e suoni di sistema, e la rimozione della filigrana per hardware non supportato.
* Crea la cartella speciale "God Mode" sul desktop e disabilita la schermata di blocco (*Lock screen*). Ogni comando di questo modulo esegue il riavvio istantaneo di `explorer.exe`.

#### Modulo 4: Ottimizzazione Performance

* Sblocca e attiva il piano energetico nascosto "Prestazioni Eccellenti" e disabilita il *Power Throttling* per evitare limitazioni della CPU.
* Ottimizza i parametri di sistema per il gaming abilitando la *Game Mode* di Windows, disattivando il Game DVR e abilitando l'HAGS (Hardware Accelerated GPU Scheduling).
* Interrompe i servizi di indicizzazione (`WSearch`) e `SysMain` (Superfetch) per alleggerire il carico su disco e RAM.
* Velocizza lo spegnimento del sistema riducendo il timeout di chiusura delle app bloccate e aumenta la priorità di elaborazione per CPU e GPU tramite modifiche al registro.

#### Modulo 5: Gestione App

* Disinstalla tramite PowerShell le applicazioni preinstallate non necessarie e i software sponsorizzati di sistema, inclusa la rimozione forzata di OneDrive.
* Utilizza il gestore `winget` per installare in modalità silenziosa e automatizzata i software essenziali (browser, player multimediali, utility di compressione e sviluppo).
* Permette l'aggiornamento centralizzato di tutti i programmi installati nel sistema e il ripristino del Microsoft Store in caso di errori di funzionamento.
* Rimuove i file di installazione orfani nella cartella MSI e sblocca l'installazione di applicativi da qualsiasi fonte attendibile.

#### Modulo 6: Sicurezza

* Forza l'aggiornamento immediato delle firme virali di Windows Defender e avvia una scansione rapida del sistema.
* Attiva l'accesso controllato alle cartelle come protezione nativa contro i Ransomware e abilita l'isolamento del core per l'integrità della memoria.
* Blocca l'esecuzione di script esterni dannosi disabilitando Windows Script Host e attiva la protezione contro le applicazioni potenzialmente indesiderate (PUA).
* Impedisce a Windows Update di sovrascrivere i driver stabili hardware con versioni generiche e interroga i server Microsoft per verificare lo stato della licenza OS.
