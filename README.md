# EarCandle
EarCandle wants to provide users with their virtual machines 

If one uses virtualization servers like Proxmox-VE one could provide the users with a limited proxmox web gui but I feel that users do not need to know about proxmox. They log on at some web portal and get some buttons where they could see their machines which they can start, stop or suspend.
Just minimal functionality for a careless user of a VM, that just should work somehow. Don't bother me with details :-)



Interesting approaches that should be considered for integration are:

https://github.com/novnc/noVNC

https://github.com/joshpatten/PVE-VDIClient

Apache Guacamole!
https://github.com/osc3b/proxmox-guacamole-client
Interessting architecture! The Database part should be integrated with the registration and login-foo below :-)
(This integration uses containers, which could be a security issuse. Better to use a VM to serve guacamole and the supporting infrastructure, as
one wants to minimize the attack surface of a virtualization server. It es easier to jail-break a "container" (escape linux name spaces) than a virtualization (or "containers" in a virtual machine with proper hardware insulation)

Serving the net of the VM:
A VM shall be generic and indifferntly if it is a full clone or a linked clone based on a template.

Therefore a *database driven DHCP server*, that serves static dhcp leases needs to be used ....
https://github.com/flan/staticdhcpd

As the database as **single point of truth knows** 

“One Database to rule them all,
One Database to find them,
One Database to bring them all
and into the light and connect them with joy”

― modified and inspired by J.R.R. Tolkien, The Fellowship of the Ring 


The mighty Database knows the *fate of each VM*:
... how many will pass from the VM-server and how many will be created on the VM-server; who will live and who will die; who will die at his predestined time and who before his time; who by ACPI shutdown and who by reset, who by system crash, who by freezing, who by badly written software, who by wrong data, who by wrong "business logic", who by exploit, who by power outage, and who by loss of network connectivity. Who will rest and who will operate, who will run in harmony and who will be harried, who will enjoy tranquillity and who will suffer, who will be impoverished and who will be enriched, who will be degraded and who will be exalted. 
Yes, I enjoyed the holidays :-)


For registration and login-foo the mighty database might have these servants:

https://github.com/samir321-pixel/Django-Registration

https://github.com/vismodo/django-login-and-register



For Proxmox-VE remote control:
(proxmoxer a python based wrapper to address the proxmox api)
https://github.com/proxmoxer/proxmoxer


Status:
EarCandle is sort of a playground for now.


Hints: Maybe, statically linked oasislinux is a good VM platform for EarCandle
