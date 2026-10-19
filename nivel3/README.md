# Nível 3 — Cloud-init

## 📌 Sobre o projeto

Este projeto faz parte da sequência de atividades de aprendizado sobre automação de infraestrutura utilizando Cloud-init e Multipass.

O objetivo do Nível 3 é continuar desenvolvendo conhecimentos sobre provisionamento automatizado de máquinas virtuais Linux, organização de configurações e execução de tarefas durante a inicialização do sistema.

## 🛠️ Tecnologias utilizadas

- Multipass: criação e gerenciamento de máquinas virtuais.
- Cloud-init: automação da configuração inicial do sistema operacional.
- Linux: sistema operacional utilizado na máquina virtual.
- Git: ferramenta de controle de versão.
- GitHub: plataforma para hospedagem do repositório.

## 📂 Estrutura do projeto

```text
nivel3/
├── cloud-config.yaml
└── README.md
⚙️ Como funciona
O Cloud-init permite executar configurações automaticamente durante a inicialização de uma máquina virtual.

Por meio do arquivo cloud-config.yaml, é possível automatizar tarefas como:

Atualização da lista de pacotes do sistema.

Instalação de programas e serviços.

Criação e configuração de arquivos.

Execução de comandos durante a inicialização.

O Multipass é utilizado para criar e administrar a máquina virtual que executará essas configurações.

🚀 Como executar o projeto
1. Pré-requisitos
Windows com suporte à virtualização habilitado.

Multipass instalado.

Git instalado.

Arquivo cloud-config.yaml configurado na pasta do projeto.

2. Acessar o diretório
Abra o Git Bash e entre na pasta do Nível 3.

3. Criar a máquina virtual
Execute o comando:


bash
multipass launch -n vm-nivel3 --memory 512M --cpus 1 --disk 5G --cloud-init cloud-config.yaml
A memória foi limitada a 512 MB para reduzir o consumo de recursos em computadores com 4 GB de RAM. Dependendo das tarefas executadas, pode ser necessário aumentar esse valor.

4. Verificar a máquina virtual

bash
multipass list
Para consultar informações detalhadas:


bash
multipass info vm-nivel3
5. Parar ou iniciar a máquina virtual
Para parar:


bash
multipass stop vm-nivel3
Para iniciar novamente:


bash
multipass start vm-nivel3
🧠 Importância do Cloud-init
A automação permite preparar ambientes de forma padronizada e repetível, diminuindo a necessidade de configurações manuais.

O uso do Cloud-init com Multipass ajuda a compreender conceitos importantes de infraestrutura como código, provisionamento de servidores e gerenciamento de ambientes Linux.

⚠️ Gerenciamento de memória RAM
Em computadores com 4 GB de RAM, é importante limitar os recursos destinados às máquinas virtuais.

O Windows e os demais programas também consomem memória. Por isso, uma configuração inadequada pode impedir a inicialização da máquina virtual.

A quantidade de memória deve ser ajustada de acordo com as tarefas realizadas e os recursos disponíveis no computador.

✅ Resultado esperado
Praticar a criação de máquinas virtuais com Multipass.

Compreender o provisionamento automatizado com Cloud-init.

Executar configurações iniciais em um ambiente Linux.

Aprimorar a organização e a documentação de projetos.

Utilizar Git e GitHub para versionar o projeto.

📚 Conclusão
O Nível 3 dá continuidade ao aprendizado de automação de infraestrutura, utilizando ferramentas que facilitam a criação, a configuração e o gerenciamento de ambientes virtuais.

A atividade reforça a importância da automação, da documentação e do gerenciamento eficiente dos recursos computacionais.