VAGRANTFILE_API_VERSION = '2'.freeze

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = 'chef/centos-7.0'
  config.ssh.forward_agent = true

  config.vm.provider 'virtualbox' do |vb|
    vb.customize ['modifyvm', :id, '--memory', '2048']
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = 'provisioning/playbook.yml'
    ansible.verbose = 'vv'
  end
end
