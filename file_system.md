# Partizioni e File System in Linux: Guida Dettagliata

Le **partizioni** sono divisioni logiche di un'unità di archiviazione, che consentono di organizzare i dati in modo efficiente. Ogni partizione può essere formattata con un file system specifico.

## Tipi di Partizioni

* **Partizioni primarie**: Partizioni principali del disco, utilizzabili per sistemi operativi o dati.
* **Partizioni estese**: Partizioni speciali che contengono partizioni logiche.
* **Partizioni logiche**: Partizioni all'interno di una partizione estesa.

## File System Comuni in Linux

* **ext4**: File system predefinito per molte distribuzioni, offre prestazioni elevate e affidabilità.
* **XFS**: File system ad alte prestazioni, ideale per server con grandi volumi di dati.
* **Btrfs**: File system moderno con funzionalità avanzate come snapshot e compressione.
* **FAT32**: File system legacy, usato per partizioni EFI e unità flash USB.
* **NTFS**: File system di Windows, supportato in lettura/scrittura da Linux.
* **swap**: Partizione per memoria virtuale.

## Concetti Chiave

* **Copy-on-Write (CoW)**:
    * Una tecnica di gestione dei dati in cui le modifiche ai file non sovrascrivono i dati originali, ma creano copie delle parti modificate.
    * Btrfs utilizza CoW per snapshot e ripristino.
* **Journaling**:
    * Un metodo per registrare le modifiche al file system prima che vengano scritte sul disco.
    * ext4 e XFS utilizzano il journaling per migliorare l'affidabilità e la velocità di ripristino in caso di crash.

## Comandi Utili

* `lsblk`: Visualizza partizioni e file system del disco.
* `fdisk` o `gdisk`: Crea e gestisce partizioni.
* `mkfs`: Formatta una partizione con un file system.
* `mount`: Monta un file system.
* `umount`: Smonta un file system.
* `du`: Stima l'utilizzo dello spazio su disco.
* `df`: Riporta l'utilizzo dello spazio su disco del file system.
* `fsck`: Controlla e ripara un file system.

## Approfondimenti

* La scelta del file system dipende dalle esigenze: ext4 per uso generale, XFS per grandi volumi, Btrfs per funzionalità avanzate.
* CoW e journaling sono tecniche che migliorano l'affidabilità e la gestione dei dati nei file system moderni.