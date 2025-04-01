# Il Percorso di Avvio di Linux

1.  **Il BIOS/UEFI e il POST:**

    * Quando premi il pulsante di accensione, il primo software ad entrare in azione è il **BIOS** (Basic Input/Output System) o, nelle macchine più recenti, l'**UEFI** (Unified Extensible Firmware Interface).
    * Questo software risiede in un chip sulla scheda madre del computer.
    * Il BIOS/UEFI esegue un test chiamato **POST** (Power-On Self-Test) per verificare che l'hardware del computer funzioni correttamente (RAM, CPU, dischi, ecc.).
    * Se il POST rileva un problema, potresti sentire dei "beep" o vedere un messaggio di errore sullo schermo.

2.  **Il Boot Loader:**

    * Se il POST ha successo, il BIOS/UEFI cerca un "**boot loader**" su un dispositivo di archiviazione (solitamente il disco rigido).
    * Il boot loader è un piccolo programma responsabile dell'avvio del sistema operativo vero e proprio.
    * In Linux, un boot loader comune è **GRUB** (GRand Unified Bootloader).
    * GRUB ti permette anche di scegliere quale sistema operativo avviare, se ne hai installati più di uno.

3.  **Il Kernel:**

    * Il boot loader carica il **kernel** Linux nella memoria RAM.
    * Il kernel è il cuore del sistema operativo, il software che gestisce l'hardware e fornisce i servizi di base.
    * Il kernel inizia a inizializzare l'hardware, come i driver per i dispositivi, e monta il file system radice (la struttura di cartelle principale del sistema).

4.  **Il Sistema di Init:**

    * Una volta che il kernel è pronto, avvia il primo processo utente, chiamato "**init**".
    * Nelle distribuzioni Linux moderne, "init" è solitamente **systemd**.
    * systemd è responsabile dell'avvio di tutti gli altri servizi e processi necessari per il funzionamento del sistema.
    * systemd avvia i servizi di sistema in parallelo, rendendo l'avvio più veloce.

5.  **I Servizi di Sistema:**

    * systemd avvia una serie di servizi di sistema, come:
        * Il servizio di rete, per connetterti a Internet.
        * Il gestore dei log (**journal**), per registrare gli eventi del sistema.
        * Il gestore del display (**display manager**), come **GDM** o **LightDM**.
    * Per un approfondimento sui servizi di sistema, consulta il file [servizi\_di\_sistema.md](servizi_di_sistema.md).

6.  **Il Gestore del Display (Display Manager) e il Server Grafico:**

    * Il gestore del display è il programma che ti presenta la schermata di accesso grafica.
    * Il gestore del display avvia il server grafico (**display server**).
        * **Xorg**: è il sistema di visualizzazione più maturo e ampiamente supportato.
        * **Wayland**: è un nuovo protocollo di visualizzazione che sta guadagnando popolarità come alternativa a Xorg, offrendo maggiore efficienza e sicurezza.
    * Ti permette di inserire il tuo nome utente e la password per accedere al sistema.
    * Una volta inserite le credenziali corrette, il gestore del display avvia il tuo ambiente desktop (**desktop environments**) come **GNOME**, **KDE**, **XFCE**, ecc...

7.  **Il Session Manager:**

    * Il **session manager** è il software che gestisce la sessione utente corrente.
    * Si occupa di avviare i programmi che hai configurato per l'avvio automatico, ripristinare le finestre aperte, e gestire le impostazioni del tuo ambiente desktop.
    * Una volta che il session manager è pronto, puoi finalmente iniziare a utilizzare il tuo sistema Linux.