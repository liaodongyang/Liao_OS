# Liao_OS
OS Learning

Computer Boot:
  "pull oneself up by one's bootstraps" mean prepare of start(go) in computer

BIOS: 
  Power-On Self-Test --> Boot Sequence -->Master boot record(MBR)(1-446 machine code, 447-510 Partition table,511-512 End with 0xaa55)

Partition table: 
  http://wiki.osdev.org/Partition_Table

GDT:
  also, we create the gdt in boot and lgdt here to push into the protected mode(pm).

EBR:
  000 – 1BD	000 – 445	Generally unused; normally filled with zeroes; may contain another boot loader i.e. a partition boot record, for                           example in conjunction with Advanced Active Partitions	446
  1BE – 1CD	446 – 461	Partition table's first entry	16
  1CE – 1DD	462 – 477	Partition table's second entry	16
  1DE – 1ED	478 – 493	Unused[4] third entry filled with zeroes	16
  1EE – 1FD	494 – 509	Unused[4] fourth entry filled with zeroes	16
  1FE - 1FF	510 - 511	Signature 55AAh in big-endian network order, same as little-endian 0xAA55. On disk: 0x55 at offset 510 and 0xAA at                         offset 511. 2
  EBR, total size: 446 +(4×16) +2 =	512(byte!)

