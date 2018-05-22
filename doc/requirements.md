# VMLINK Requirements

This document lists the requirements of the VMLINK project
and the script(s) which result from it.

## VMLINK Automounter

The goal is to have an automounter script which will automatically
link and mount a disk owned by another virtual machine.

The presumption is that you are running on a hypervisor which
supports guest-driven disk sharing. (As of this writing, only z/VM
is known to accommodate the concept of guest-driven sharing.)

    cd /auto/vmlink/othervmid.otherdisk

`othervmid` is the virtual machine owning the disk in question.

`otherdisk` is the address of the disk on the owning virtual machine.

If the disk is partitioned and a specific partition is desired,
the syntax might be:

    cd /auto/vmlink/othervmid.otherdisk.partition

## Automounter Sequence

The steps the script must handle include:

* find an available I/O slot on the local virtual machine
* `link` the other disk (to the local slot just found)
* bring the linked disk online to the local virtual machine
* mount the linked disk (or the partition of that disk thus indicated)


