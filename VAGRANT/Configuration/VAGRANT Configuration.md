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


### NETWORKING

#### PORT

**Port forwarding**

Forward port 80 from Guest OS to port 4567 on Host OS
```
Vagrant.configure("2") do |config|
  ...
  config.vm.network :forwarded_port, guest: 80, host: 4567
  ...
end
```

#### PRIVATE NETWORKS

[Documentation](https://www.vagrantup.com/docs/networking/private_network.html)

> Vagrant private networks allow you to access your guest machine by some address that is not publicly accessible from the global internet. 
> Multiple machines within the same private network (also usually with the restriction that they're backed by the same provider) can communicate with each other on private networks

**DHCP**

This will automatically assign an IP address from the reserved address space. The IP address can be determined by using vagrant ssh to SSH into the machine and using the appropriate command line tool to find the IP, such as ifconfig.
```
Vagrant.configure("2") do |config|
  ...
  config.vm.network "private_network", type: "dhcp"
  ...
end
```

**Static IP**

Specify a static IP address for the machine. This lets you access the Vagrant managed machine using a static, known IP.

> While you can choose any IP you would like, you should use an IP from the [reserved private address space](https://en.wikipedia.org/wiki/Private_network#Private_IPv4_address_spaces). These IPs are guaranteed to never be publicly routable, and most routers actually block traffic from going to them from the outside world.

```
Vagrant.configure("2") do |config|
  ...
  config.vm.network "private_network", ip: "192.168.50.4"
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



















