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
  <table>
    <tr>
        <td>000 – 1BD</td>
        <td>000 – 445</td>
        <td>Generally unused; normally filled with zeroes; may contain another boot loader i.e. a partition boot record, for example in conjunction with Advanced Active Partitions</td>
        <td>446</td>
    </tr>
    <tr>
        <td>1BE – 1CD</td>
        <td>446 – 461</td>
        <td>Partition table's first entry</td>
        <td>16</td>
    </tr>
    <tr>
        <td>1DE – 1ED</td>
        <td>462 – 477	</td>
        <td>Partition table's second entry</td>
        <td>16</td>
    </tr>
    <tr>
        <td>1DE – 1ED</td>
        <td>478 – 493</td>
        <td>Unused third entry filled with zeroes</td>
        <td>16</td>
    </tr>
    <tr>
        <td>1EE – 1FD</td>
        <td>494 – 509</td>
        <td>Unused fourth entry filled with zeroes</td>
        <td>16</td>
    </tr>
    <tr>
        <td>1FE - 1FF</td>
        <td>510 - 511</td>
        <td>Signature 55AAh in big-endian network order, same as little-endian 0xAA55. On disk: 0x55 at offset 510 and 0xAA at offset 511</td>
        <td>2</td>
    </tr>
    <tr>
        <td>EBR, total size: 446 +(4×16) +2 =	512(byte!)</td>
    </tr>
</table>
