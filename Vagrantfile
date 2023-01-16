Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end
  config.vm.define "appserver" do |app|
    app.vm.hostname = "yoloserver"
    app.vm.box = "geerlingguy/ubuntu2004"
    app.vm.provision "ansible" do |ansible|
      ansible.playbook="playbook.yml"
    end
   end
 end