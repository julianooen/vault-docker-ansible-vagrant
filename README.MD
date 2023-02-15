Tema 19 - Vault

Como utilizar:

## Docker

* Requisitos:

    - git
	- Docker

* Execução:
    
    - Clonar este repositório
    - Executar o comando 'docker build -t vault .' na raiz do projeto para criar a imagem
    - Com o comando 'docker run -it --name vaultrun  vault' é possivel rodar a imagem e entrar no container em execução

## Jenkins e Ansible

obs: foi utilizado o vagrant para esta etapa, porém as roles e o jenkinsfile podem ser reutilizadas para rodar localmente ou em outra vm. 

* Requisitos:

    - git
    - Virtual Box
	- Vagrant

* Execução:

	- Utilizar o comando 'vagrant up' na raiz do projeto para iniciar a vm e instalar o ansible e o jenkins
	- No terminal ao finalizar a criação da vm será exibida a senha para inicializar o jenkins, copie essa senha

* Dando permissão ao jenkins

		1.	No terminal execute 'vagrant ssh'
		2.	Execute 'sudo visudo' no terminal da vm
		3.	Insira 'jenkins ALL = NOPASSWD: ALL' no documento, salve e feche

* Configurando o Jenkins:

		1.	Com a senha copiada anteriormente acesse 'http://localhost:8080' e cole-a
		2.	Na próxima tela escolha a opção 'Install suggested plugins' e siga os proximos passos até que a mensagem 'Jenskins ready' seja exibida
		
* Criando a pipeline
		
		1.	Criar novo item
		2.	Colocar o nome do Job e escolher a opção 'Pipeline'
		3.	Em seguida no campo Pipeline definition escolher a opção 'Pipeline script from SCM'
		4.	No campo SCM escolher a opção 'Git'
		5.	No campo Repository URL inserir: 'https://github.com/julianooen/vault-docker-ansible-vagrant.git'
		6.	Em Branch Specifier preencher com '*/master'
		7.	Em Script Path preencher com 'Jenkinsfile'