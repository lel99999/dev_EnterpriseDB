Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end

  config.vm.define :edbas13server do |edbas13server|
#   edbas13server.vm.box = "bento/centos-6.10"
#   edbas13server.vm.box = "clouddood/RH7.5_baserepo"
    edbas13server.vm.box = "clouddood/RH7.9_infra"
    edbas13server.vm.host_name = "edbas13server.test.dev"

#   edbas13server.ssh.forward_agent = true

    edbas13server.vm.provision "ansible" do |ansible|
#     ansible.playbook = "deploy_edbas13_client.yml"
      ansible.playbook = "deploy_edbas13_server.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   edbas13server.vm.network :private_network, ip: "10.0.1.26"
    edbas13server.vm.network :private_network, ip: "192.168.60.128"
  end



#######################################################################################################################################

# config.trigger.before :destroy do |trigger|
#   run "rm -Rf /tmp/abc/*"
    # subscription-manager remove --all
    # subscription-manager unregister
    # subscription-manager clean
#   trigger.name = "Destroy Trigger ..."
#   trigger.info = "Destroy Trigger Execution ..."
#   trigger.run = { path: "subscription-manager remove --all"}
#   trigger.run = { path: "subscription-manager unregister"}
#   trigger.run = { path: "subscription-manager clean"}
# end
end
