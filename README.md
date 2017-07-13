# Loteria
Aplicação cliente-servidor de uma loteria em Python

## Tecnologias:
	Python 2.7
	MySQL 5.5
	PyQT 4
	Protocolo TCP

## Pré-requisitos:
	Instalar a biblioteca PyQT para o correto funcionamento da parte gráfica do sistema.
		sudo apt-get install python-qt4

## Instalação:
	Será necessário a criação de uma base de dados no mysql com o nome 'loteria', no arquivo Banco.py será necessário alterar o atributo user e passwd, de acordo com as configurações do seu mysql.

	Para utilização do envio de emails, você precisará colocar o email e a senha nos parâmetros do arquivo Email.py

## Inicialização
	Abra a pasta LoteriaServidor/front/ e de o seguinte comando no terminal: python2.7 ConexaoServidor.py

	Abra a pasta LoteriaCliente/front/ e de o seguinte comando no terminal: python2.7 mainCliente.py

## Base de dados:
	create database loteria;

	create table pessoa (
		id_pessoa int auto_increment,
		nome varchar(90),
		idade int,
		cpf varchar(20),
		endereco varchar(160),
		login varchar(30),
		senha varchar(45),
		email varchar(90),
		cartao varchar(50),
		conta varchar(15),
		primary key(id_pessoa)
	);

	create table aposta (
		id_aposta int auto_increment,
		campo1 int,
		campo2 int,
		campo3 int,
		campo4 int,
		campo5 int,
		campo6 int,
		id_pessoa int,
		foreign key (id_pessoa) references pessoa (id_pessoa),
		primary key (id_aposta)
	);


