# File Informativi e Dispositivi in Linux: Un Approfondimento

In Linux, le informazioni sull'hardware e sui dispositivi sono accessibili tramite file speciali nelle directory `/proc`, `/sys` e `/dev`.

## File Informativi in /proc e /sys

Le directory `/proc` e `/sys` sono punti di mount per pseudo-filesystem che forniscono informazioni sul kernel e sull'hardware. Questi filesystem risiedono in RAM e non sono destinati all'archiviazione di file convenzionali.

* **`/proc`**: Contiene informazioni sui processi in esecuzione e sulle risorse hardware.
    * `/proc/cpuinfo`: Informazioni dettagliate sulla CPU.
    * `/proc/interrupts`: Elenco degli interrupt per ciascun dispositivo I/O.
    * `/proc/ioports`: Regioni di memoria delle porte I/O in uso.
    * `/proc/dma`: Canali DMA in uso.
* **`/sys`**: Contiene informazioni sui dispositivi e dati del kernel relativi all'hardware.

I comandi `lspci`, `lsusb` e `lsmod` fungono da front-end per leggere queste informazioni.

## File dei Dispositivi in /dev

La directory `/dev` contiene file speciali che rappresentano i dispositivi hardware collegati al sistema.

* Ogni file in `/dev` è associato a un dispositivo di sistema, in particolare ai dispositivi di archiviazione.
* Esempio: `/dev/hda` rappresenta un disco rigido IDE legacy.
* Le partizioni del disco sono rappresentate da `/dev/hda1`, `/dev/hda2`, ecc.

## Udev e Hotplug

Il sottosistema `udev` gestisce i dispositivi rimovibili e crea dinamicamente i file corrispondenti in `/dev`.

* `udev` rileva i dispositivi hardware e crea i file di dispositivo in base a regole predefinite.
* Gestisce sia i dispositivi presenti all'avvio (coldplug) che quelli collegati durante l'esecuzione (hotplug).
* `udev` si basa su SysFS, il pseudo-filesystem montato in `/sys`.
* Hotplug: Rilevamento e configurazione di un dispositivo durante l'esecuzione del sistema.
* Il kernel Linux supporta hotplug dalla versione 2.6.
* `udev` cerca regole corrispondenti in `/etc/udev/rules.d/` quando rileva nuovi dispositivi.

## Collegamento con i Concetti Precedenti

* **Kernel Ring Buffer**: I messaggi di rilevamento hardware del kernel sono accessibili tramite `dmesg` e possono essere utili per il debug di `udev`.
* **systemd**: `udev` è integrato con systemd e gestito come servizio di sistema.
* **Partizioni e File System**: I dispositivi di archiviazione in `/dev` sono utilizzati per creare partizioni e montare file system.
* **FHS**: Le directory `/proc`, `/sys` e `/dev` sono definite dall'FHS.

## Comandi Utili

* **lspci**: Elenca i dispositivi PCI collegati al sistema.
* **lsusb**: Elenca i dispositivi USB collegati al sistema.
* **lsmod**: Elenca i moduli del kernel caricati.
* **dmesg**: Visualizza i messaggi del Kernel Ring Buffer.
* **udevadm**: Gestisce il sottosistema udev.
* **lsblk**: elenca i dispositivi a blocchi.
* **fdisk/gdisk**: gestisce le partizioni dei dischi.