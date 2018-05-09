# VMLINK

VMLINK Automounter for Linux on z/VM

## VMLINK Automounter

Consider automounter point /vmlink, similar to /misc and /net.
Under /vmlink, one can have target directories ("keys" in automounter speak)
named vmid.addr where "vmid" is the owning virtual machine
and "addr" is the address of a disk on that virtual machine.

## cd /vmlink/yourvm.yourdisk

The VMLINK automounter script uses the key, here `yourvm.yourdisk`,
to "link" (at the z/VM layer) your disk, bring it online,
and then mount it at the named location under the automounter point.

