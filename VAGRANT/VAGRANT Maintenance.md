# VAGRANT MAINTENANCE


## Which Vagrant instance is going to be maintained

The one in which Vagrant root dir you are.
So go to the necessary Vagrant root dir.

```
cd C:\Users\sergii.burtovyi\vagrant_root
dir

       Directory of C:\Users\sergii.burtovyi\vagrant_root

      12-Jul-18  16:09    <DIR>          .
      12-Jul-18  16:09    <DIR>          ..
      12-Jul-18  16:09    <DIR>          .vagrant
      12-Jul-18  17:05             3,092 Vagrantfile
```

## Maintenance commands to be run for previously chosen Vagrant env

### Bouncing Vagrant instance

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

### Login to Vagrant instance

**Log in to the Vagrant instance**

Make connection to Vagrant instance as ``vagrant`` user via ``ssh``
```
vagrant ssh
```

**Log out from the Vagrant instance**
```
logout
```




