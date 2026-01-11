Vagrant.configure("2") do |config|
  # Daha stabil olan "generic/rocky9" kutusunu kullanıyoruz
  config.vm.box = "generic/rocky9"
  
  config.vm.define "sentinel-server" do |node|
    node.vm.hostname = "sentinel-server"
    node.vm.provider "virtualbox" do |vb|
      vb.memory = "4096" # 4GB RAM (Oracle ve Java için kritik) [cite: 9, 39, 41]
      vb.cpus = 2
    end
    # SSH bağlantısı için gerekli ayar
    node.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh"
  end
end