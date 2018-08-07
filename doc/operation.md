# VMLINK Automounter Operation

The basic flow is as follows:

* a user references a file or directory triggering the script
* the script loads its optional configuration, if any
* the script parses the key `$1` into *vmid*, *addr*, and optionally *partition*
* next, the script looks for an available (unused) I/O address (local address)
* it attempts to link the target *vmid* and *addr* to that local address
* if the link was successful, then the script varies the new disk (local address) online
* if the online was successful, the script must find the block device assigned
* if the block device was found, the script finally attempts to mount it (or a partition)
* all the logs been stored by the help of logger command and then SYSLOG takes care of them

## Clean-up:

The script should check if a disk being linked has already been linked.
To be effective, that check must happen before the new (redundant) link is varied online.
Skipping this check is not a hindrance to operation. Performing this check makes for good hygiene.

The script should periodically vary-off and detach (unlink) disks which
have become unmounted. This too makes for good hygiene but is not vital to operation.

## Partitioning:

Minidisks might be unpartitioned.
For example, the CMS "EDF" minidisk filesystem occupies the entire disk.
Other filesystems may also start at offset zero and may or may not obscure the partition table.

If no partition is specified, the VMLINK automounter script must attempt both
"whole disk" and "partition one". The order of the attempts is yet to be determined
and might not matter since only one should succeed. If a specific partition was indicated,
then the script must succeed in mounting that partition or must fail the operation.


