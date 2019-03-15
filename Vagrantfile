# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
    config.vm.provision "shell", inline: <<-SHELL
    echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC47pg+DXJcQHZn4xpArzfB1UdhuU1MK7I4aT6g+3vfhFVakTagZFhxnmb/DpEmPfyzzYkvhOyoMPjh2giHhZEf8Mu8WaTmj7DUrw2vExJJooqUCkeYuz81C3kVNDX3MOsdP8L5LytHe0WJYji3BSM6WhTUTkPIa2zLqKjkvtfbIprmrtrBbIgdsYe+2gnxIcPmxMjziL+drudTWGP0Mac1q4jbkUajYTFQkmEP4HnHhlCQpbDkBlejr3kWBTIqV7xHRIaTwuCpLyvi1g2Ph8hnyggC7OCh52w5YP+h7lu6YvNlVMxkA7N6wXxln3cD4U36pbyBdzzFWeez8PV5KWv1 matt@localhost.localdomain" >> /home/vagrant/.ssh/authorized_keys
    sudo systemctl restart sshd.service
    SHELL
  
    config.vm.define "openNebula" do |m|
      m.vm.box = "bento/centos-7.5"
      m.vm.hostname = 'one'
      
    
      m.vm.network :"public_network", bridge: "wlp1s0", ip: "192.168.1.210"
    
      m.vm.provider :virtualbox do |v|
        v.name    = "one"
        v.memory  = "4096"
        v.cpus    = "2" 
      end
    end
  end
  
