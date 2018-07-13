# VAGRANT MAINTENANCE


## Which Vagrant env is going to be maintained

The one in which Vagrant root dir you are.

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

### 1. Bouncing Vagrant env

**Start**

Boot configured Vagrant env.

Based Box will be started (no changes from previous run will be available).

```
vagrant up
```

**Stop**

Terminates the use of any resources by the VM.

All changes made during Vagrant env running will be lost.

Doesn't delete the Box.
```
vagrant destroy
```

### 2. Session to Vagrant env handling

**Log in**

Make connection to Vagrant instance as ``vagrant`` user via ``ssh``
```
vagrant ssh
```

**Log out**
```
logout
```

### 3. Box handling

**Download the Box**
```
vagrant box add ubuntu/trusty64
```

**Remove the Box**
```
vagrant box remove ubuntu/trusty64
```



