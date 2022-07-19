1. Problem with updating the base image?
   1. Make sure the image is the correct (hashicorp/bionic64 did the trick in this setting)
   2. use `--no-provision` flag
   3. Remove provision line from *Vagrantfile*
2. Configured shell `config.ssh.shell` is invalid
   ```ruby
   VAGRANTFILE_API_VERSION = "2"

   Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
      config.ssh.username = "root"
      config.ssh.password = "tessel2" 
      config.ssh.shell = "ash"

      config.vm.synced_folder ".", "/vagrant", disabled: true

      config.vm.box = "technicalmachine/tessel2"

      # Add usb filter for Arduino
      config.vm.provider :virtualbox do |vb|
         vb.customize ['modifyvm', :id, '--usb', 'on']
         vb.customize ['usbfilter', 'add', '0', '--target', :id, '--name', 'Arduino', '--vendorid', '0x2341', '--productid', '0x0043']
      end
   end
```

From https://gist.github.com/rwaldron/28c2b47ea18cbb0643c0