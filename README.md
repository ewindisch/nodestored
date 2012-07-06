nodestored - server block storage daemon
==========
Author: Eric Windisch
License: APL 2.0

Nodestored intends to provide an API to mounting and accessing backend
block storage devices, as visible from the destination machine.

Running
-------

Commands pass into nodestored in the JSON format, over an STDIN pipe.
This makes it easy to use with SSH. It would be trivial to support
JSONRPC or another RPC library instead.

With nodestored, a system can be configured with storage on a local
disk, nfs share, or iscsi. API calls to create new block devices
(generally for virtualization) can create new files, iscsi LUNs, etc. It
will handle mounting those files appropriately and can also wrap many OS
methods.

Peekfs
------

The "peekfs" methods which allow inner-filesystem manipulation use
Twisted's FilePath module to provide a fake chroot.
