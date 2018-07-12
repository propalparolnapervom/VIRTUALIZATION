## VAGRANT MAINTENANCE

### Which Vagrant env is going to be maintained

**ALL commands have to be run from Vagrant root dir for necessary Vagrant env**

```
cd C:\Users\sergii.burtovyi\vagrant_root
dir

       Directory of C:\Users\sergii.burtovyi\vagrant_root

      12-Jul-18  16:09    <DIR>          .
      12-Jul-18  16:09    <DIR>          ..
      12-Jul-18  16:09    <DIR>          .vagrant
      12-Jul-18  17:05             3,092 Vagrantfile
```

### Maintenance commands to be run for previously chosen Vagrant env

**Start Vagrant**

Boot configured Vagrant env

```
vagrant up
```

**Stop Vagrant**
Terminate the use of any resources by the virtual machine
```
vagrant destroy
```

**SSH to the Vagrant**

```
vagrant ssh
```
