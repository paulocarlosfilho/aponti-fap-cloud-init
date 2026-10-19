# Nível 1 — Servidor Web Automatizado com Multipass e Cloud-init

## 📌 Sobre o projeto

Este projeto tem como objetivo criar uma máquina virtual Linux utilizando o Multipass e configurar automaticamente um servidor web com o Nginx, utilizando o Cloud-init.

O Cloud-init permite automatizar a configuração inicial de uma máquina virtual, instalando pacotes e criando arquivos sem precisar executar todas as etapas manualmente.

## 🛠️ Tecnologias utilizadas

- Multipass: ferramenta para criar e gerenciar máquinas virtuais.
- Cloud-init: ferramenta para automatizar a configuração inicial do sistema.
- Nginx: servidor web utilizado para disponibilizar uma página HTML.
- Linux: sistema operacional executado na máquina virtual.
- Hyper-V: tecnologia de virtualização utilizada pelo Multipass no Windows.

## 📂 Estrutura do projeto

nivel1/
├── cloud-config.yaml
└── README.md

## ⚙️ Como funciona

O arquivo cloud-config.yaml contém as instruções executadas durante a inicialização da máquina virtual.

As principais configurações são:

- package_update: true — atualiza a lista de pacotes disponíveis.
- packages — instala o Nginx.
- write_files — cria uma página HTML em /var/www/html/index.html.
- runcmd — reinicia o serviço Nginx para disponibilizar a página.

Após a inicialização, a máquina virtual funciona como um servidor web simples, exibindo a mensagem:

"Bem-vindo ao Servidor Automatizado com Cloud-init!"

## 🚀 Como executar o projeto

### 1. Pré-requisitos

- Windows com virtualização habilitada.
- Multipass instalado.
- Arquivo cloud-config.yaml presente no diretório do projeto.

### 2. Criar a máquina virtual

No terminal, dentro da pasta do projeto, execute:

multipass launch -n vm-nivel1 --memory 512M --cpus 1 --disk 5G --cloud-init cloud-config.yaml

Esse comando cria a máquina virtual com o nome vm-nivel1, configura um processador virtual, reserva 512 MB de RAM e define um disco de 5 GB.

### 3. Verificar a máquina virtual

multipass list

Para consultar os detalhes da máquina:

multipass info vm-nivel1

### 4. Acessar o servidor web

Copie o endereço IP apresentado pelo comando anterior e acesse-o no navegador:

http://IP_DA_MAQUINA_VIRTUAL

Substitua IP_DA_MAQUINA_VIRTUAL pelo endereço IP real da instância.

## 🧠 Por que limitar a memória RAM?

Durante a execução deste projeto, ocorreu um erro de memória insuficiente ao tentar iniciar a máquina virtual com 1024 MB (1 GB) de RAM.

O computador utilizado possui apenas 4 GB de memória RAM. Além do Multipass, o Windows e seus demais programas também precisam de memória para funcionar.

Quando a máquina virtual solicita uma quantidade de memória que o sistema não consegue disponibilizar, o Hyper-V pode impedir sua inicialização.

Para contornar esse problema, a memória da VM foi reduzida para 512 MB, utilizando o parâmetro --memory 512M.

Essa configuração diminui o consumo de recursos e pode permitir que a máquina virtual seja executada em computadores com pouca RAM. Entretanto, 512 MB é uma configuração limitada e pode não ser suficiente para todas as tarefas, especialmente durante atualizações e instalações de pacotes.

Observação: limitar a memória da máquina virtual não aumenta a RAM física do computador. Apenas reduz a quantidade de memória solicitada pela VM, deixando mais recursos disponíveis para o sistema operacional hospedeiro.

## 🧹 Como parar a máquina virtual

Para interromper a execução e liberar os recursos utilizados:

multipass stop vm-nivel1

Para iniciá-la novamente:

multipass start vm-nivel1

## ✅ Resultado esperado

Ao concluir o exercício, será possível:

- Criar uma máquina virtual Linux com o Multipass.
- Automatizar sua configuração com Cloud-init.
- Instalar e executar o Nginx.
- Disponibilizar uma página HTML por meio de um servidor web.
- Compreender a importância de dimensionar os recursos de uma máquina virtual conforme a capacidade do computador.

## 📚 Conclusão

Este projeto demonstra como automatizar a criação de um servidor web utilizando ferramentas de virtualização e provisionamento.

Também evidencia a importância do gerenciamento de recursos em ambientes com pouca memória RAM. Ajustar a quantidade de memória alocada à máquina virtual é uma medida importante para evitar falhas na inicialização e melhorar a convivência entre a VM e o sistema operacional hospedeiro.