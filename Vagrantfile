##################################
##  Ansible Inventory Definitions #
###################################
      
groups = {
  "border" => ["border1", "border2"],
  "spine" => ["spine1", "spine2"],
  "leaf" => ["leaf1", "leaf2"], 
  "switch" => ["sw10"],
  "servers" => ["host11", "host12", "host2", "host10", "host3"],
  "networking:children" => ["spine", "leaf", "switch"]
}


##################################
#   Vagrant Machine Definitions  #
##################################
      
Vagrant.configure(2) do |config|

	config.vm.define "border1" do |border1|
		border1.vm.box = "cumulus-vx-3.0.0"
		if Vagrant.has_plugin?("vagrant-cachier")
    		config.cache.scope = :box
 		end

		border1.vm.hostname = "border1"
		border1.vm.network "private_network", virtualbox__intnet: "b1s1"
		border1.vm.network "private_network", virtualbox__intnet: "b1s2"
		border1.vm.network "private_network", virtualbox__intnet: "b1rou"
		border1.vm.network "private_network", virtualbox__intnet: "peerlink_b12"
		border1.vm.network "private_network", virtualbox__intnet: "peerlink_b21"
		border1.vm.network "private_network", virtualbox__intnet: "b1nci"
		border1.vm.network "private_network", virtualbox__intnet: "b1int"
		border1.vm.network "private_network", virtualbox__intnet: "b1aws"

		border1.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		border1.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111111"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
		end
	end

	config.vm.define "border2" do |border2|
		border2.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		border2.vm.hostname = "border2"
		border2.vm.network "private_network", virtualbox__intnet: "b2s1"
		border2.vm.network "private_network", virtualbox__intnet: "b2s2"
		border2.vm.network "private_network", virtualbox__intnet: "b2rou"
		border2.vm.network "private_network", virtualbox__intnet: "peerlink_b12"
		border2.vm.network "private_network", virtualbox__intnet: "peerlink_b21"
		border2.vm.network "private_network", virtualbox__intnet: "b2nci"
		border2.vm.network "private_network", virtualbox__intnet: "b2int"
		border2.vm.network "private_network", virtualbox__intnet: "b2aws"

		border2.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		border2.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111112"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
		end
	end
	  
	config.vm.define "spine1" do |spine1|
		spine1.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		spine1.vm.hostname = "spine1"
		spine1.vm.network "private_network", virtualbox__intnet: "s1l1"
		spine1.vm.network "private_network", virtualbox__intnet: "s1l2"
		spine1.vm.network "private_network", virtualbox__intnet: "s1l3"
		spine1.vm.network "private_network", virtualbox__intnet: "peerlink_s12"
		spine1.vm.network "private_network", virtualbox__intnet: "peerlink_s21"
		spine1.vm.network "private_network", virtualbox__intnet: "b1s1"
		spine1.vm.network "private_network", virtualbox__intnet: "b2s1"

		spine1.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end
		
		spine1.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111121"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
		end
	end

	config.vm.define "spine2" do |spine2|
		spine2.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		spine2.vm.hostname = "spine2"
		spine2.vm.network "private_network", virtualbox__intnet: "s2l1"
		spine2.vm.network "private_network", virtualbox__intnet: "s2l2"
		spine2.vm.network "private_network", virtualbox__intnet: "s2l3"
		spine2.vm.network "private_network", virtualbox__intnet: "peerlink_s12"
		spine2.vm.network "private_network", virtualbox__intnet: "peerlink_s21"
		spine2.vm.network "private_network", virtualbox__intnet: "b1s2"
		spine2.vm.network "private_network", virtualbox__intnet: "b2s2"

		spine2.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		spine2.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111122"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
		end
	end


	config.vm.define "leaf1" do |leaf1|
		leaf1.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		leaf1.vm.hostname = "leaf1"
		leaf1.vm.network "private_network", virtualbox__intnet: "s1l1"
		leaf1.vm.network "private_network", virtualbox__intnet: "s2l1"
		leaf1.vm.network "private_network", virtualbox__intnet: "l1h11"
		leaf1.vm.network "private_network", virtualbox__intnet: "l1h12"
		
		leaf1.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		leaf1.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111131"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		end
	end

	config.vm.define "leaf2" do |leaf2|
		leaf2.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		leaf2.vm.hostname = "leaf2"
		leaf2.vm.network "private_network", virtualbox__intnet: "s1l2"
		leaf2.vm.network "private_network", virtualbox__intnet: "s2l2"
		leaf2.vm.network "private_network", virtualbox__intnet: "l2h2"
		leaf2.vm.network "private_network", virtualbox__intnet: "l2sw10"
		
		leaf2.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		leaf2.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111132"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		end
	end

	config.vm.define "sw10" do |sw10|
		sw10.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		sw10.vm.hostname = "sw10"
		sw10.vm.network "private_network", virtualbox__intnet: "l2sw10"
		sw10.vm.network "private_network", virtualbox__intnet: "sw10l3"
		sw10.vm.network "private_network", virtualbox__intnet: "sw10h10"

		sw10.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		sw10.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111133"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		end
	end


	config.vm.define "leaf3" do |leaf3|
		leaf3.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		leaf3.vm.hostname = "leaf3"
		leaf3.vm.network "private_network", virtualbox__intnet: "s1l3"
		leaf3.vm.network "private_network", virtualbox__intnet: "s2l3"
		leaf3.vm.network "private_network", virtualbox__intnet: "l3h3"
		leaf3.vm.network "private_network", virtualbox__intnet: "sw10l3"

		leaf3.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		leaf3.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111134"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
		end
	end


	config.vm.define "host11" do |host11|
		host11.vm.box = "ubuntu/trusty64"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		host11.vm.hostname = "host11"
		host11.vm.network "private_network", virtualbox__intnet: "l1h11", auto_config: false
	  
		host11.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		end

		host11.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/host-provision.yml"
		  ansible.groups = groups
		end
	end

	config.vm.define "host12" do |host12|
		host12.vm.box = "ubuntu/trusty64"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		host12.vm.hostname = "host34"
		host12.vm.network "private_network", virtualbox__intnet: "l1h12", auto_config: false
	  
		host12.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		end

		host12.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/host-provision.yml"
		  ansible.groups = groups
		end
	end

	config.vm.define "host2" do |host2|
		host2.vm.box = "ubuntu/trusty64"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		host2.vm.hostname = "host2"
		host2.vm.network "private_network", virtualbox__intnet: "l2h2", auto_config: false
	  
		host2.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		end

		host2.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/host-provision.yml"
		  ansible.groups = groups
		end
	end

	config.vm.define "host10" do |host10|
		host10.vm.box = "ubuntu/trusty64"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		host10.vm.hostname = "host10"
		host10.vm.network "private_network", virtualbox__intnet: "sw10h10", auto_config: false

		host10.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		end

		host10.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/host-provision.yml"
		  ansible.groups = groups
		end
	end

	config.vm.define "host3" do |host3|
		host3.vm.box = "ubuntu/trusty64"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		host3.vm.hostname = "host3"
		host3.vm.network "private_network", virtualbox__intnet: "l3h3", auto_config: false

		host3.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
		end

		host3.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/host-provision.yml"
		  ansible.groups = groups
		end
	end


	config.vm.define "ncilink" do |ncilink|
		ncilink.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		ncilink.vm.hostname = "ncilink"
		ncilink.vm.network "private_network", virtualbox__intnet: "b1nci"
		ncilink.vm.network "private_network", virtualbox__intnet: "b2nci"

		ncilink.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		ncilink.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111141"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		end
	end

	config.vm.define "internet" do |internet|
		internet.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		internet.vm.hostname = "internet"
		internet.vm.network "private_network", virtualbox__intnet: "b1int"
		internet.vm.network "private_network", virtualbox__intnet: "b2int"

		internet.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		internet.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111142"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		end
	end

	config.vm.define "aws" do |aws|
		aws.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		aws.vm.hostname = "aws"
		aws.vm.network "private_network", virtualbox__intnet: "b1aws"
		aws.vm.network "private_network", virtualbox__intnet: "b2aws"

		aws.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		aws.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111143"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		end
	end

	config.vm.define "rounsw" do |rounsw|
		rounsw.vm.box = "cumulus-vx-3.0.0"
        if Vagrant.has_plugin?("vagrant-cachier")
            config.cache.scope = :box
        end

		rounsw.vm.hostname = "rounsw"
		rounsw.vm.network "private_network", virtualbox__intnet: "b1rou"
		rounsw.vm.network "private_network", virtualbox__intnet: "b2rou"

		rounsw.vm.provision "ansible" do |ansible|
		  ansible.playbook = "provisioning/playbook.yml"
		  ansible.groups = groups
		end

		rounsw.vm.provider "virtualbox" do |v|
		  v.customize ["modifyvm", :id, "--macaddress1", "000000111144"]
		  v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
		  v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
		end
	end
end
