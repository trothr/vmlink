# VMLINK History

As a verb, "vmlink" refers to the VM/CMS command.

The idea is that you can access a disk owned by a different
virtual machine from your own virtual machine, and that you can
do this quickly and easily and without special privileges.

## CMS `vmlink`



If you are on a z/VM system and running CMS, enter the command ...

    help cms vmlink

 ... for the best description of using `vmlink` on VM/CMS.

## DASD Automounter

At one time, Nationwide Insurance had a substantial Linux-on-z/VM
installation and had the need to share disks across virtual machines.
The team consisted of engineers familiar with z/VM and engineers
familiar with Unix and Linux. Linking and mounting shared disks
required that one speak both languages.

Eventually there was an automounter script which combined the steps
of finding an available I/O slot, linking the disk, varying it online,
and mounting it. The whole operation did not require privileges,
being handled by the automounter.

That work was lost and would be out of date.




