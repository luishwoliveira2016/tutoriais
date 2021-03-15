# METASPLOIT FRAMEWORK


O Metasploit é um projeto abragente da área de segurança da informação, que inclui informações e auxilia na busca de vulnerabilidades em sistemas através do uso de exploits, entre outros recursos. <br>
É muito utilizada nos testes de penetração("Pentests") e utilizada por Hackers para invasão.

O uso do material exposto e a sua aplicação é inteiramente responsabilidade do usuário,
não me responsabilizo pela forma de uso e intenções.



A ferramenta foi desenvolvida em 2003 pelo programador HD Moore, e comprado pela Rapid 7

Existem as versões Pro e Open Source(Metasploit Framework)


### Como instalar:


A versão Open Source está diponível no GitHub,você pode acessar o repositório através do link abaixo:
 

https://github.com/rapid7/metasploit-framework



Verifique a versão do seu sistema operacional para realizar o download corretamente. 

Versões do Linux(debian/ubuntu):

Antes de instalar propriamente o Metasploit-Framework,  execute o comando abaixo para atualizar :

	$sudo apt-get update && apt-get upgrade

Para instalar, execute o comando abaixo: 

	$sudo curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall &&   chmod 755 msfinstall &&   ./msfinstall


** Se não tiver o pacote curl instalado, instale utilizando o comando :


	$ sudo apt install curl
	



Após finalizado o processo, você poderá abrir o console do Metasploit no terminal, utilize o comando:

	$msfconsole


Depois apertar 'Enter', vai abrir o terminal do Metasploit, com o seguinte formato.

	
	msf6 > _ 


O número que aparece após o msf, se refere a versão do Metasploit Framework instalada.

Irá apresentar uma tela incial no terminal, e algumas informações sobre a aplicação.

![This is a alt text.](/image/sample.png "This is a sample image.")



###Principais comandos do Metasploit

-------------------------------------------------------------------------------------------------
##### msfconsole

Comando utilizado para abrir o console do Metasploit


##### search

search type : exploit =   busca xploits
permite procurar por tipo especifico de módulo


	msf6 > search 

##### help

Comando de ajuda sobre o Framework Mertasploit.Exibe todos os comandos disponíveis e sua forma de uso.


	msf6 > help

Comando help + comando específico do Metasploit, ele exibirá todos os parâmetros que acompanham o comando
Ex.
				
	msf6 > help search





##### info

Obtém informações sobre o exploit, ou módulo desejado.
para realizar a consulta, digite info + modulo_desejado
Ex.

	msf6 > info 	


##### use




##### show options



##### exploit



##### run




##### set




### O que é
-------------------------------------------------------------------------------------------------


##### Exploit :

 Pedaço de código que explora por uma vulnerabilidade no sistema operacional ou na aplicação;

##### Payload :

 Onde carrega o xploit carga.O arquivo malicioso que será utilizadeo para realizar o ataque

##### Post  = 



##### Auxiliary :

	Scanners, sniffer na rede,utilitários;

##### Evasion :

Evasão de anti virus, firewall;

##### Meterpreter:

RHOSTS
