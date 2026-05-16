# WinCustomizer

WinCustomizer è uno script Batch avanzato progettato per automatizzare la manutenzione, ottimizzare le prestazioni, tutelare la privacy e personalizzare l'interfaccia utente su sistemi operativi Windows 11.

## Requisiti di sistema

* Windows 11 o Windows 10
* Privilegi di Amministratore (obbligatori per modificare il registro e i servizi)
* Connessione internet attiva (necessaria per il corretto funzionamento di `winget`)

## Funzionalità principali

### Manutenzione sistema

Esegue la pulizia dei file temporanei, della cache e dei log di sistema. Ripara l'immagine del sistema operativo e i file corrotti utilizzando i tool nativi `sfc` e `DISM`.

### Privacy e telemetria

Disabilita i servizi di tracciamento in background, la geolocalizzazione, la raccolta dati di Windows, Microsoft Edge e della suite Office, bloccando inoltre l'accesso non necessario a microfono e fotocamera.

### Personalizzazione ui

Permette di ripristinare il menu contestuale classico di Windows 10, gestire l'allineamento e la dimensione delle icone sulla taskbar, configurare Esplora File (mostrando estensioni e file nascosti) e attivare la modalità Dark Mode o il God Mode.

### Ottimizzazione performance

Attiva il piano energetico nascosto Prestazioni Eccellenti, configura i parametri per il gaming (Game Mode, HAGS) e disabilita i servizi superflui come `SysMain` e l'indicizzazione dei file per ridurre il carico su RAM e disco.

### Gestione app

Rimuove i bloatware e le applicazioni sponsorizzate preinstallate da Microsoft tramite PowerShell, e installa in blocco i programmi essenziali (come Google Chrome, VLC, 7-Zip) sfruttando il gestore pacchetti `winget`.

### Sicurezza

Gestisce le definizioni e le scansioni di Windows Defender, attiva le protezioni native contro i Ransomware e i PUA, e impedisce a Windows Update di sovrascrivere i driver hardware stabili.

## Sicurezza e backup del registro

Prima di accedere al menu principale, lo script mostra un avviso e avvia una procedura di sicurezza automatica:

* Lo script verifica se è già presente un salvataggio precedente nella cartella `C:\Backup_Registro`.
* Se i file di backup esistono già, lo step viene saltato automaticamente per risparmiare tempo ed evitare sovrascritture non necessarie.
* e non viene trovato alcun backup, lo script crea la cartella ed esporta le intere chiavi di registro `HKLM` e `HKCU` in formato `.reg` prima di effettuare qualsiasi modifica al sistema.

## Come utilizzare lo script

1. Scarica il file `WinCustomizer.bat`.
2. Fai click con il tasto destro sul file.
3. Seleziona **Esegui come amministratore**.
4. Segui le istruzioni a schermo e scegli le opzioni dal menu inserendo il numero corrispondente.
