# VAGRANT CONFIGURATION

[Useful link 1](https://www.sitepoint.com/vagrantfile-explained-setting-provisioning-shell/)

## GUEST OS ITSELF (Linux, for example)

**Define host name**
```
Vagrant.configure("2") do |config|
  ...
  config.vm.hostname = "db.host.ua"
  ...
end
```

**Add shared folder btw host OS and guest OS**
```
#1st arg: host machine folder to be shared with the VM
#2nd arg: target folder inside the VM
#create: "true" - create if target dir doesn't exist
#group: “www-data” and owner: “www-data” specifies the owner and the group of the shared folder inside the VM. 

Vagrant.configure("2") do |config|
  ...
  config.vm.synced_folder "./", "/var/www", create: true, group: "vagrant", owner: "vagrant"
  ...
end
```



## VAGRANT ITSELF (Specific Vagrant instance)

**Set the name of Vagrant instance**
```
Vagrant.configure("2") do |config|
  ...
  config.vm.define "not_default"
  ...
end
```




## VM ITSELF (VirtualBox, for example)

[Documentation](https://www.virtualbox.org/manual/ch08.html#vboxmanage-modifyvm)

**Set the name for VM itself**
```
Vagrant.configure("2") do |config|
  ...
  config.vm.provider "virtualbox" do |v|
    v.name = "My First Test Vagrant VM"
  end
  ...
end
```

**Set the memory of VM**
```
#The :id is the virtual machine’s ID, which needs to be passed to VBoxManage everytime we want to modify something VM specific. #Fortunately, Vagrant handles this for us, so we just need to pass this variable.

Vagrant.configure("2") do |config|
  ...
  v.customize ["modifyvm", :id, "--memory", "1024"]
  ...
end
```



















