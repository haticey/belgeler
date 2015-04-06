=================
Nfs Notlar
=================

:date: Çrş 18 Şub 2015 15:07:20 EET
:comments: true
:categories: 
:tags: 
:Author: Orkun Gunay

Teori
-----

By using smb in stead of nfs my disk spins up less often. But it still
spins up with no apparent reason (no computer in the network is on)
that's tipical of linux. Some measures can be taken to alliviate the problem, 
but they are not 100% effective.

nfs has another characteristic that might contribute to the problem: the 
server stores some status on disk, so that after a crash/porweroff/poweron  it 
can resume operations and continue serving the same clients, without they even 
noticed what happened (but the clients blocks if they try to contact the 
server -- when it comes back the client de-blocks and continues).

With this nfs philosofy in mind, Alt-F sets the save-status directory on disk.
This was a design decision, as I could setup those directories in memory, 
trying to avoid the disk spinup.  The problem is that on a server crash you 
would have to poweroff the clients also, as the server could not resume 
operations.
Unless... (this is becaming a class!) that in the client you mounted the nfs 
share in "soft" mode (not "hard" -- but then you could have data loss...

client kurulum
-----------------

.::

    yum install -y nfs-utils nfs-utils-lib

    chkconfig nfs on

#. duzenlemeler /etc altinda exports ve fstab (emrah.com'da)

#. Servisleri baslatma, paylasimi check etme

.:: 

    service  rpcbind start
    service  nfs start
    showmount -e localhost

server'da yapilandirma;
-----------------------

exports dosyasi duzeni;

..code:: sh

    directory machine1(option11,option12) machine2(option21,option22)

#. NOT: NFS server duzenlemeleri /etc/sysconfig/nfs'ten 

Kaynaklar;
----------

#. `<http://www.jamescoyle.net/how-to/1019-view-available-exports-on-an-nfs-server>`_

#. `<http://www.faqs.org/docs/Linux-HOWTO/NFS-HOWTO.html#CLIENT>`_

#. `<http://www.tecmint.com/how-to-setup-nfs-server-in-linux/>`_
