
# ------- Windows (and Mac without M1 Chip) -----------------------
Vagrant.configure("2") do |config|
    config.vm.box = "generic/ubuntu2010"
    config.vm.provision :shell, path: "env/python_provisioning.sh"

    config.vm.synced_folder "app/", "/home/vagrant/app/"
    config.vm.synced_folder "env/", "/home/vagrant/env"
end
# -----------------------------------------------------------------


# # ------- Mac OS M1 Chip Only -------------------------------------
# Vagrant.configure("2") do |config|
#   config.vm.box = 'spox/ubuntu-arm'
#   config.vm.box_version = "1.0.0"
#   config.vm.network 'private_network',ip: '192.168.56.20'
#   config.vm.provider 'vmware_fusion' do |vb|
#     #first argument is local and second argument is where it should be on Vm
#     config.vm.synced_folder 'env/','/home/vagrant/env'
#     vb.gui = true
#   end
#   config.vm.provision 'shell', path: 'env/script.sh'
#   end
# end
# # -----------------------------------------------------------------
