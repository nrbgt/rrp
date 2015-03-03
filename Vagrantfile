VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |vbox|
    vbox.name = "my-app"
    vbox.memory = 1024
    vbox.cpus = 2
  end

  config.vm.network "forwarded_port", guest: 8080, host: 8080,
    auto_correct: true

  config.vm.provision :shell,
    inline: <<-eos
      add-apt-repository ppa:docker-maint/testing
      apt-get update
      apt-get install -y docker.io

      usermod -a -G docker vagrant

      wget https://raw.github.com/pypa/pip/master/contrib/get-pip.py
      python get-pip.py

      /usr/local/bin/pip install -q -U docker-compose
      yes | /usr/local/bin/pip uninstall -q requests
      /usr/local/bin/pip install -q requests==2.4.3
    eos
end
