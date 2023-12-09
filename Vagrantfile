Vagrant.configure("2") do |config|
# Especificando a iso do Linux Ubuntu 18:
  config.vm.box = "hashicorp/bionic64"

# Todo serviço que eu acesar pelo localhost através da porta 8070 vai ser redirecionada p/ a porta 80 da vm do vagrant:
  config.vm.network "forwarded_port", guest: 80, host: 8070

# Configurar placa de rede no modo bridge, ip static e interface para wi-fi:
  config.vm.network "public_network", ip: "192.168.1.4", bridge: "wlp2s0"

# Executar comando no terminal após levantar vm:
#  config.vm.provision "shell",
#    inline: "sudo apt update && apt install -y nginx && service nginx start"

# Executar script após levantar vm. o script encontra-se no diretório do próprio Vagrantfile:
  config.vm.provision "shell", path: "script.sh"

# Sincronizar uma diretório local para o diretório da vm:
# no navegador: http://192.168.1.4/cep.html:
  config.vm.synced_folder "src/", "/var/www/html/"
end
