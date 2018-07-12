## VAGRANT INITIAL CONFIGURATION on Windows

### 1. Setup Project
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


### 2. Setup the Box
Instead of building a virtual machine from scratch, which would be a slow and tedious process, Vagrant uses a base image (**Box**) to quickly clone a virtual machine.

2.1. Choose the [Box](https://app.vagrantup.com/boxes/search) to be used.

2.2. Configure the Project to use necessary Box as a base
     
   2.2.1. To use downloaded Box
     
     
```
 vagrant box add ubuntu/trusty64

                  ==> box: Loading metadata for box 'ubuntu/trusty64'
                      box: URL: https://vagrantcloud.com/ubuntu/trusty64
                  ==> box: Adding box 'ubuntu/trusty64' (v20180709.0.0) for provider: virtualbox
                      box: Downloading: https://vagrantcloud.com/ubuntu/boxes/trusty64/versions/20180709.0.0/providers/virtualbox.box
                      box: Download redirected to host: cloud-images.ubuntu.com--:--:--)
                      box: Progress: 100% (Rate: 1596k/s, Estimated time remaining: --:--:--)
                  ==> box: Successfully added box 'ubuntu/trusty64' (v20180709.0.0) for 'virtualbox'!
```
Open the Vagrantfile and change the contents to the following:
```
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
end
```


   2.2.2. To download Box each time during Vagrant startup

