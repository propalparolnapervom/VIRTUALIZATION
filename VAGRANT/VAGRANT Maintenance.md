# VAGRANT MAINTENANCE

**[Documentation](https://www.vagrantup.com/docs/cli/)**

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


## Which Vagrant envs are running

**Globally**

> This info from cache, so it might be not up-to-date.

```
vagrant global-status

       id       name    provider   state   directory
       ------------------------------------------------------------------------
       a6fa07b  default virtualbox running D:/overall/vagrant_project

       The above shows information about all known Vagrant environments
       on this machine. This data is cached and may not be completely
       up-to-date (use "vagrant global-status --prune" to prune invalid
       entries). To interact with any of the machines, you can go to that
       directory and run Vagrant, or you can use the ID directly with
       Vagrant commands from any directory. For example:
       "vagrant destroy 1a2b3c4d"
```

**Status**
```
vagrant status

       Current machine states:

       default                   running (virtualbox)

       The VM is running. To stop this VM, you can run `vagrant halt` to
       shut it down forcefully, or you can run `vagrant suspend` to simply
       suspend the virtual machine. In either case, to restart it again,
       simply run `vagrant up`.
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

### 4. Networking

**IP of host machine as seen from Vagrant instance**
```
ip route sho

       default via 10.0.2.2 dev eth0 proto dhcp metric 100
```





