# Antes de iniciar, é recomendado atualizar os pacotes do sistema:

sudo apt update: Baixa os pacotes nescessários. <br>
sudo apt upgrade: Instala os pacotes já baixados anteriormente. <br>
sudo apt update && sudo apt upgrade: Faz a mesma coisa, porém em um comando só. <br>

Reiniciando o Sistema <br>

Após a atualização, reinicie a máquina para aplicar mudanças importantes: <br>

sudo reboot <br>

2 - Instalando Dependências Necessárias <br>

Instale os pacotes essenciais para compilar os módulos dos Adicionais para Convidado: <br>

sudo apt install build-essential dkms linux-headers-$(uname -r) <br>

Descrição dos Pacotes <br>

build-essential: Ferramentas para compilar código-fonte (gcc, g++, make, etc.). <br>
dkms: Sistema para recompilar automaticamente módulos de kernel, útil após atualizações. <br>
linux-headers-$(uname -r): Cabeçalhos do kernel atual, necessários para compilar módulos compatíveis. <br>

3 - Acessando o Instalador dos Adicionais para Convidado <br>

Monte o CD de Adicionais para Convidado no VirtualBox e navegue até o diretório montado: <br>

cd /media/$USER/VBox_GAs_7.0.6 <br>
$USER é uma variável de ambiente que representa o usuário atualmente logado. <br>

4 - Executando o Instalador <br>

Execute o script para instalar os recursos adicionais: <br>

sudo ./VBoxLinuxAdditions.run <br> 
Este comando instala as ferramentas que melhoram a integração do sistema convidado (resolução de tela, pastas compartilhadas, etc.). <br>

5 - Verificando Módulos Carregados <br>

Use o comando abaixo para verificar se os módulos do VirtualBox foram carregados com sucesso: <br>

Explicação dos Comandos <br>
lsmod: Lista os módulos carregados no kernel. <br>
grep vbox: Filtra os resultados que contêm "vbox", prefixo comum aos módulos do VirtualBox. <br>
