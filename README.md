
Status: laying down a couple of ideas on a different approach to get Redis running on Windows.

I got this idea the other day: instead of porting Redis to Windows (which I'd still like to see), why not providing an automated way to install a virtual machine on Windows, which would itself run as a service and would run Redis on a Linux lightweight OS?

For instance we could have some kind of installer which would:
- install VirtualBox unless it's already there
- create a virtual machine and install a lightweight Linux OS
- bootstrap the virtual machine for chef maybe
- install redis
- ensure the virtual machine run with port-forwarding enabled for seamless access

At some point I would split the different parts so that people not using VirtualBox can still use this in some way (ie: VMWare...)

Things to figure out:
- my Linux of choice is Ubuntu, yet I'd like to provide a very small OS by default so the install is faster. Which OS can be a good fit here?
- how to run a VirtualBox instance as a service?
- will it blend?