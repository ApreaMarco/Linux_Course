# Gestione dei Job, Scheduling e Niceness in Linux

In Linux, la gestione dei job, la loro schedulazione e la "niceness" sono fondamentali per ottimizzare l'utilizzo delle risorse del sistema.

## Gestione dei Job

* **Job**: Un'unità di lavoro eseguita dal sistema.
* **Processi in background**:
    * Utilizzare `&` alla fine di un comando per eseguirlo in background.
    * Esempio: `comando &`.
* **Controllo dei job**:
    * `jobs`: Visualizza i job in esecuzione.
    * `fg`: Porta un job in foreground.
    * `bg`: Porta un job in background.
    * `kill`: Termina un job.
* **Comandi utili**:
    * `ps`: Visualizza i processi in esecuzione.
    * `top`: Monitora i processi e l'utilizzo delle risorse.

## Scheduling dei Job

* **Schedulazione una tantum (at)**:
    * `at`: Pianifica l'esecuzione di un comando in un momento specifico.
    * Esempio: `at 15:30 tomorrow -f script.sh`.
    * `atq`: Visualizza i job pianificati con `at`.
    * `atrm`: Rimuove un job pianificato con `at`.
* **Schedulazione regolare (cron)**:
    * `cron`: Pianifica l'esecuzione regolare di comandi.
    * `crontab -e`: Modifica la tabella cron dell'utente.
    * Sintassi di crontab: `minuto ora giorno_del_mese mese giorno_della_settimana comando`.
    * Esempio: `0 1 * * * /path/to/script.sh` (esegue lo script ogni giorno all'1:00).
    * `/etc/cron.daily`, `/etc/cron.weekly`, `/etc/cron.monthly`: Directory per script eseguiti giornalmente, settimanalmente e mensilmente.
* **Schedulazione con timer di systemd**:
    * I timer di systemd offrono una gestione più flessibile e potente per la schedulazione dei job.
    * Un timer di systemd è un'unità che controlla l'esecuzione di un'altra unità (solitamente un servizio).
    * I timer possono essere configurati per eseguire job in base a intervalli di tempo, calendari o eventi specifici.
    * Comandi utili:
        * `systemctl list-timers`: elenca i timer attivi.
        * `systemctl enable nome_timer.timer`: abilita un timer all'avvio del sistema.
        * `systemctl start nome_timer.timer`: avvia un timer immediatamente.

## Niceness

* **Niceness**: Un valore che influenza la priorità di un job.
* Valori: Da -20 (massima priorità) a 19 (minima priorità).
* `nice`: Avvia un job con un valore di "niceness" specifico.
    * Esempio: `nice -n 10 comando`.
* `renice`: Modifica il valore di "niceness" di un job in esecuzione.
    * Esempio: `renice -n -5 -p PID`.
* Comando ps: La colonna "NI" mostra il valore di "niceness".
* La niceness è utile per dare priorità a processi importanti o per limitare l'impatto di processi ad alta intensità di risorse.

## Gestione dei Messaggi di Log

* **systemd-cat**: Esegue un comando e invia il suo output al journal di systemd.
    * Esempio: `systemd-cat comando`.
* **logger**: Invia messaggi di log al syslog (o journald).
    * Esempio: `logger "Messaggio di log"`.
* Questi comandi sono utili per la creazione di log personalizzati, e per il debug.

## Approfondimenti

* La gestione dei job consente di eseguire compiti in background e di controllare i processi.
* Lo scheduling permette di automatizzare l'esecuzione di comandi in momenti specifici o regolari.
* La "niceness" consente di regolare la priorità dei processi per ottimizzare l'utilizzo delle risorse.
* I timer di systemd offrono una soluzione moderna e flessibile per la schedulazione dei job, integrandosi strettamente con il sistema di gestione dei servizi di systemd.
* `systemd-cat` e `logger` permettono di personalizzare i messaggi di log.