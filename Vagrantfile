Vagrant.configure("2") do |hello|
  hello.vm.box = "centos/7"
  hello.vm.network "forwarded_port", guest: 22, host: 2225
  hello.vm.network "forwarded_port", guest: 80, host: 8085

  hello.vm.provision :ansible do |ansible|
    ansible.playbook = "provision.yml"  
  end
end