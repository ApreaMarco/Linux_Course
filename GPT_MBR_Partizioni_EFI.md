# Partizioni, GPT, MBR e Partizione EFI

Le **partizioni** sono divisioni logiche di un'unità di archiviazione (come un disco rigido o un SSD) che consentono di organizzare e gestire i dati in modo più efficiente. Ogni partizione può essere formattata con un file system diverso e utilizzata per scopi specifici.

## GPT (GUID Partition Table)

**GPT** (GUID Partition Table) è uno standard moderno per la tabella delle partizioni. Offre numerosi vantaggi rispetto al vecchio standard MBR, tra cui:

* Supporto per dischi di dimensioni superiori a 2 TB.
* Supporto per un numero illimitato di partizioni (in teoria).
* Maggiore robustezza grazie alla ridondanza dei dati.
* Utilizzo di identificatori univoci globali (GUID) per le partizioni.

GPT è lo standard raccomandato per i sistemi moderni, specialmente quelli basati su UEFI.

## MBR (Master Boot Record)

**MBR** (Master Boot Record) è un vecchio standard per la tabella delle partizioni. Presenta diverse limitazioni, tra cui:

* Supporto per dischi di dimensioni massime di 2 TB.
* Supporto per un massimo di 4 partizioni primarie.
* Minore robustezza rispetto a GPT.

MBR è ancora utilizzato in alcuni sistemi legacy, ma è in fase di graduale abbandono.

## Partizione EFI (Extensible Firmware Interface)

La **partizione EFI** è una partizione speciale utilizzata dai sistemi basati su UEFI per l'avvio del sistema operativo. Contiene i file necessari per l'avvio, come i boot loader e i driver UEFI.

### Caratteristiche della partizione EFI:

* Formattata con il file system FAT32.
* Contiene i file di avvio per il sistema operativo.
* Utilizzata dai sistemi basati su UEFI.

### EFI variables:

Le **EFI variables** sono variabili di sistema memorizzate nella memoria non volatile del firmware UEFI. Queste variabili possono essere utilizzate per configurare vari aspetti del sistema, come l'ordine di avvio, le impostazioni di sicurezza e le informazioni sul sistema.

### Importanza delle EFI variables:

* Consentono al sistema operativo di comunicare con il firmware UEFI.
* Permettono di personalizzare le impostazioni di avvio del sistema.
* Possono essere utilizzate per memorizzare informazioni importanti sul sistema.

### Comandi utili:

* `efibootmgr`: strumento per gestire le voci di avvio UEFI.
* `mount`: comando per montare la partizione EFI.
* `lsblk`: comando per visualizzare le partizioni del disco.

### Informazioni aggiuntive:

* La partizione EFI è essenziale per l'avvio dei sistemi basati su UEFI.
* Le EFI variables sono utilizzate per configurare vari aspetti del sistema.
* È importante non eliminare o modificare la partizione EFI a meno che non si sappia cosa si sta facendo.