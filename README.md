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


For registration and login-foo:

https://github.com/samir321-pixel/Django-Registration

https://github.com/vismodo/django-login-and-register



For Proxmox-VE remote control:
(proxmoxer a python based wrapper to address the proxmox api)
https://github.com/proxmoxer/proxmoxer


Status:
EarCandle is sort of a playground for now.


Hints: Maybe, statically linked oasislinux is a good VM platform for EarCandle
