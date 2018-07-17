## VAGRANT CONFIGURATION


**Define host name of Vagrant instance**
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






















