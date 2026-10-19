# Nível 2 — Cloud-init

## 📌 Sobre o projeto

Este projeto faz parte da atividade de aprendizado sobre automação de máquinas virtuais utilizando Cloud-init e Multipass.

O objetivo é aprofundar os conhecimentos em provisionamento automatizado de servidores Linux, utilizando arquivos de configuração para executar tarefas durante a inicialização da máquina virtual.

## 🛠️ Tecnologias utilizadas

- Multipass: criação e gerenciamento de máquinas virtuais.
- Cloud-init: automação da configuração inicial do sistema operacional.
- Linux: sistema operacional da máquina virtual.
- Git e GitHub: versionamento e armazenamento do projeto.

## 📂 Estrutura do projeto

```text
nivel2/
├── cloud-config.yaml
└── README.md
⚙️ Como funciona
O Cloud-init permite automatizar tarefas durante a inicialização de uma máquina virtual, reduzindo a necessidade de configurações manuais.

Por meio do arquivo cloud-config.yaml, é possível definir atualizações do sistema, instalação de pacotes, criação de arquivos e execução de comandos.

🚀 Como executar o projeto
1. Pré-requisitos
Windows com virtualização habilitada.

Multipass instalado.

Git instalado.

Arquivo cloud-config.yaml configurado no diretório do projeto.

2. Acessar a pasta do projeto
No Git Bash, entre no diretório do Nível 2.

3. Criar a máquina virtual
Execute o comando abaixo, ajustando o nome do arquivo de configuração e os recursos conforme necessário:


bash
multipass launch -n vm-nivel2 --memory 512M --cpus 1 --disk 5G --cloud-init cloud-config.yaml
A memória foi limitada para 512 MB como medida para reduzir o consumo de RAM em computadores com 4 GB de memória. Essa quantidade pode ser insuficiente para algumas tarefas.

4. Verificar a máquina virtual

bash
multipass list
multipass info vm-nivel2
5. Gerenciar a máquina virtual
Para parar a máquina virtual:


bash
multipass stop vm-nivel2
Para iniciá-la novamente:


bash
multipass start vm-nivel2
🧠 Importância da automação
A utilização do Cloud-init facilita a criação de ambientes padronizados, permitindo repetir configurações com menos intervenção manual.

O Multipass simplifica o gerenciamento das máquinas virtuais, enquanto o Git e o GitHub permitem acompanhar as alterações e manter o projeto versionado.

⚠️ Observação sobre memória RAM
Em computadores com apenas 4 GB de RAM, é importante limitar os recursos alocados à máquina virtual para reduzir a possibilidade de erros de memória insuficiente.

A configuração deve considerar também os recursos necessários para o Windows e os demais programas em execução.

✅ Resultado esperado
Compreender o funcionamento do Cloud-init.

Criar e gerenciar máquinas virtuais com Multipass.

Automatizar tarefas de configuração em Linux.

Praticar o versionamento de projetos com Git e GitHub.

📚 Conclusão
O Nível 2 dá continuidade ao aprendizado de automação de infraestrutura, reforçando o uso de máquinas virtuais e arquivos de configuração para facilitar a preparação de ambientes Linux.


