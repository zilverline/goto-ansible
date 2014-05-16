Vagrant.require_version ">= 1.6.0"

Vagrant.configure("2") do |config|

  config.vbguest.auto_update = false

  (1..3).each do |i|
    config.vm.define "web#{i}" do |c|
      c.vm.network :forwarded_port, guest: 22, host: 2200 + i, auto_correct: false, id: "ssh"
      c.vm.network :forwarded_port, guest: 80, host: 8800 + i, auto_correct: false

      c.vm.provider :docker do |d|
        d.image = "zilverline/baseimage"
        d.cmd = ["/sbin/my_init", "--enable-insecure-key"]
        d.has_ssh = true
        d.vagrant_vagrantfile = "./docker/Vagrantfile"
      end

      #c.vm.provision :shell do |s|
      #  s.inline = <<-SCRIPT
      #    apt-get update
      #    apt-get install -y python
      #  SCRIPT
      #end

      c.vm.provision :ansible do |a|
        a.playbook = "goto.yml"
        a.inventory_path = "hosts"
        #a.verbose = "vvvv"
      end

      c.ssh.username = "root"
      c.ssh.private_key_path = "zilverline.key"
      c.ssh.port = 22
    end
  end

  config.vm.define "lb" do |l|
    l.vm.network :forwarded_port, guest: 22, host: 2200, auto_correct: false, id: "ssh"
    l.vm.network :forwarded_port, guest: 80, host: 8800, auto_correct: false

    l.vm.provider :docker do |d|
      d.image = "zilverline/baseimage"
      d.cmd = ["/sbin/my_init", "--enable-insecure-key"]
      d.has_ssh = true
      d.vagrant_vagrantfile = "./docker/Vagrantfile"
    end

    l.vm.provision :ansible do |a|
      a.playbook = "goto.yml"
      a.inventory_path = "hosts"
    end

    l.ssh.username = "root"
    l.ssh.private_key_path = "zilverline.key"
    l.ssh.port = 22
  end

end
