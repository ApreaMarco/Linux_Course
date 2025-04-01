# Sistema di Logging in Linux: Dal Kernel Ring Buffer ai Runlevel

Il sistema di logging in Linux è fondamentale per monitorare il funzionamento del sistema, risolvere problemi e garantire la sicurezza. Iniziamo con il Kernel Ring Buffer e proseguiamo con i runlevel.

## Kernel Ring Buffer

Il **Kernel Ring Buffer** è una struttura di dati circolare in memoria RAM che memorizza i messaggi generati dal kernel. Questi messaggi includono informazioni sull'hardware, sui driver, sugli errori e su altri eventi di sistema.

* **dmesg:** Il comando `dmesg` viene utilizzato per visualizzare il contenuto del Kernel Ring Buffer.
* **Importanza:** Il Kernel Ring Buffer è essenziale per il debug del kernel e per la diagnosi di problemi hardware.

## Runlevel

I **runlevel** sono modalità operative del sistema che definiscono quali servizi sono in esecuzione. Ogni runlevel è associato a un insieme specifico di servizi.

* **Runlevel comuni:**
    * **0:** Arresto del sistema.
    * **1:** Modalità utente singolo.
    * **3:** Modalità multiutente con interfaccia a riga di comando.
    * **5:** Modalità multiutente con interfaccia grafica.
    * **6:** Riavvio del sistema.
* **systemd:** Nei sistemi moderni, systemd ha sostituito i runlevel con i "target". I target sono simili ai runlevel, ma offrono maggiore flessibilità e controllo.
* **systemctl:** Il comando `systemctl` viene utilizzato per gestire i target e i servizi di systemd.

## Sistema di Logging

Linux dispone di un sistema di logging centralizzato che raccoglie i messaggi di log da varie fonti, inclusi il kernel, i servizi di sistema e le applicazioni.

* **syslog:** Il demone `syslog` è stato tradizionalmente utilizzato per la gestione dei log.
* **journald:** Nei sistemi moderni, `journald` è il sistema di logging predefinito. Raccoglie i log in formato binario strutturato, offrendo vantaggi in termini di prestazioni e funzionalità di ricerca.
* **journalctl:** Il comando `journalctl` viene utilizzato per interrogare e visualizzare i log di journald.
* **/var/log:** La directory `/var/log` contiene i file di log di sistema.

## Importanza del Logging

Il sistema di logging è fondamentale per:

* **Monitoraggio del sistema:** Consente di tenere traccia del funzionamento del sistema e delle applicazioni.
* **Risoluzione dei problemi:** Aiuta a identificare e risolvere problemi di sistema e applicazioni.
* **Sicurezza:** Registra eventi di sicurezza, come tentativi di accesso non autorizzati.

## Comandi Utili

* `dmesg`: Visualizza i messaggi del Kernel Ring Buffer.
* `journalctl`: Interroga e visualizza i log di journald.
* `systemctl`: Gestisce i target e i servizi di systemd.