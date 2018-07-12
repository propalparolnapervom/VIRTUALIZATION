## VAGRANT INITIAL CONFIGURATION on Windows

### Setup Project
The first step in configuring any Vagrant project is to create a [Vagrantfile](https://www.vagrantup.com/docs/vagrantfile/).
The purpose of the Vagrantfile is twofold:
1. Mark the root directory of your project;
2. Describe the kind of machine and resources you need to run your project, as well as what software to install and how you want to access it.

Go to any empty dir (or to the just created one):
```
mkdir "C:\Users\sergii.burtovyi\vagrant_root"
cd "C:\Users\sergii.burtovyi\vagrant_root"
dir

      Directory of C:\Users\sergii.burtovyi\vagrant_root

      12-Jul-18  11:58    <DIR>          .
      12-Jul-18  11:58    <DIR>          ..
                     0 File(s)              0 bytes
                     2 Dir(s)  113,579,331,584 bytes free

```

Initialize the dir for usage with Vagrant
```
vagrant init

      A `Vagrantfile` has been placed in this directory. You are now
      ready to `vagrant up` your first virtual environment! Please read
      the comments in the Vagrantfile as well as documentation on
      `vagrantup.com` for more information on using Vagrant.
```

Vagrant file should be created
```
dir

      Directory of C:\Users\sergii.burtovyi\vagrant_root

      12-Jul-18  13:02    <DIR>          .
      12-Jul-18  13:02    <DIR>          ..
      12-Jul-18  13:02             3,081 Vagrantfile
                     1 File(s)          3,081 bytes
                     2 Dir(s)  113,578,332,160 bytes free
```
