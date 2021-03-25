# METASPLOIT FRAMEWORK


O Metasploit é um projeto abrangente da área de segurança da informação, que inclui informações,módulos e ferramentas que auxiliam na busca de vulnerabilidades em sistemas através do uso de exploits, entre outros recursos. <br>
É muito utilizada em testes de penetração("Pentests") e utilizada por Hackers para invasão.

OBS: O uso do material exposto e a sua aplicação é inteiramente responsabilidade do usuário,
não me responsabilizo pela forma de uso e intenções.


A ferramenta foi desenvolvida em 2003 pelo programador HD Moore, e comprado pela empresa de segurança Rapid 7

Atualmente existem as versões Pro e Open Source(Metasploit Framework),neste tutorial vamos falar sobre a versão Open Source,
o Metasploit Framework.


### Como instalar:


A versão Open Source está disponível no GitHub,você pode acessar o repositório através do link abaixo:
 

https://github.com/rapid7/metasploit-framework



Verifique a versão do seu sistema operacional para realizar o download corretamente. 

Para versões do Linux(debian/ubuntu):

Antes de instalar propriamente o Metasploit-Framework,  execute o comando abaixo para atualizar :

	$sudo apt-get update && apt-get upgrade

Para instalar, execute o comando abaixo: 

	$sudo curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall &&   chmod 755 msfinstall &&   ./msfinstall


** Se não tiver o pacote curl instalado, instale utilizando o comando :


	$ sudo apt install curl
	

Para mais informações sobre a instalação(requisitos e dependências), acesse https://github.com/rapid7/metasploit-framework

Após finalizado o processo, você poderá abrir o console do Metasploit no terminal, utilize o comando:

	$msfconsole


Depois apertar 'Enter', vai abrir o terminal do Metasploit, com o seguinte formato.

	
	msf6 > _ 


O número que aparece após o msf, se refere a versão do Metasploit Framework instalada.

Irá apresentar uma tela inicial no terminal, e algumas informações sobre a aplicação.

![This is a alt text.](/images/splash_screen.png "Metasploit initial screen.")



## Principais comandos do Metasploit

##### msfconsole

Comando utilizado para abrir o console do Metasploit.

	$msfconsole

##### banner

Exibe o logotipo e a tela inicial, com as informações de quantos módulos possui disponível para a versão do aplicativo.

	msf6 > banner


##### search

Comando base para a busca de exploits,auxiliares,payloads, entre outros módulos disponíveis.

	msf6 > search 


É possível filtrar a sua busca, pelo tipo de módulo, tipo de sistema,entre outros.

Busca especificando o tipo:

	msf6 > search type : exploit 

Busca especificando o sistema	:

	msf6 > search windows

Abreviando a busca por tipo

	msf6 > search exploit



##### help

Comando de ajuda sobre o Framework Mertasploit.Exibe todos os comandos disponíveis e sua forma de uso.


	msf6 > help

![This is a alt text.](/images/help_screen.png "Execução do comando help.")

Comando help + comando específico do Metasploit, ele exibirá todos os parâmetros que acompanham o comando.
Ex.
				
	msf6 > help search
	
![This is a alt text.](/images/help_search_screen.png "Execução do comando help+ comando.")


##### info

Obtém informações sobre o exploit, ou módulo desejado.
Para realizar a consulta, digite `info` + modulo_desejado.


	msf6 > info 	

No exemplo da imagem abaixo, foi realizada a busca das informações de um exploit.

![This is a alt text.](/images/info_screen.png "Comando info")

É possível buscar as informações apenas com a numeração do exploit ou módulo desejado.
 
No exemplo abaixo foi buscado um PAYLOAD através do seu número de identificação.
 
![This is a alt text.](/images/info_screen_2.png "Execução do comando info.")
 

##### use

Comando utilizado para selecionar e carregar exploits, auxiliares, payloads,etc;

	msf6 > use <nome_do_exploit_ou_auxilary_etc>


##### show options

Mostrará os requisitos ou opções do módulo sendo utilizado para que o exploit, auxiliary ou o módulo escolhido seja executado de maneira correta.

	msf6 > show options <nome_do_exploit/auxiliary/etc>
	
Se estiver com o módulo em uso, poderá apenas inserir `show options`, que apresentará as opções do módulo em uso.
É possível setar estas opções, com o comando `set`, que será apresentado a seguir.

##### back

Retornar ao console inicial do Metasploit Framework,caso esteja utilizando algum módulo.Serve para sair do módulo em uso.

	msf6 > back


##### exploit (comando)


Executa o exploit ou outro módulo selecionado.

	msf6 > exploit


##### run

Da mesma forma que o comando exploit, executa o exploit ou módulo selecionado.

	msf6 > run


##### set

Utilizado para definir ou setar algum recurso ou requisito que o módulo exige obrigatoriamente ou opcionalmente, para o funcionamento.

Utilizando o comando citado acima "show options", será exibido quais os requisitos necessários, 
para que o módulo seja executado da forma correta.

	msf6 > set <substituir_opção_que_deseja_alterar> <valor>


## O que significa


##### Exploit

 Exploits(Exploradores)são sequência de comandos ou fragmentos de código que explora por uma vulnerabilidade no sistema operacional  ou na aplicação em questão;
 Estes Exploits são buscados e apresentados no Metasploit Framework, através do comando "search exploit", por exemplo.
 
 Além do framework, você pode localizar exploits ou outros módulos desejados na internet,como no site abaixo,
 você encontra uma database de exploits e outros módulos.
 
 
 https://www.exploit-db.com/
 

##### Payload

  Arquivo malicioso, geralmente de formato executável que contém a "carga",que será utilizado para realizar o ataque.
  
  O arquivo que será instalado/executado na máquina alvo do ataque,ocasionando algum problema ou gerando alguma vulnerabilidade(facilitação).
  
  Ex. envio de e-mail com um arquivo.pdf, infectado com um  programa , que será instalado/executado na máquina alvo quando o arquivo é aberto.

##### Auxiliary

Auxiliary(auxiliares), como o nome já diz, são um tipo de módulo, de ferramentas utilitárias, que auxiliam num possível ataque ou alguma necessidade de uso.
Scanners são um exemplo de auxiliar.

##### Evasion :

Módulo específico para realizar evasão de anti vírus, firewall;


## Exemplo prático

Agora será apresentado um exemplo prático utilizando alguns dos recursos apresentados anteriormente.

Para este exemplo , utilizaremos um auxiliar, um scanner de portas TCP.


1.  Para abrir o console do Metasploit,acesse o terminal, e digite o comando `msfconsole`:


![This is a alt text.](/images/msfconsole.png "Abrir o console Metasploit.")

2. Após o programa iniciado , busque pelo exploit ou módulo desejado , utilizando o comando `search` + módulo desejado
neste caso será o auxiliar auxiliary/scanner/portscan/tcp :

![This is a alt text.](/images/search.png "Abrir o console Metasploit.")

3.  Selecione o auxiliar desejado, utilizando o comando `use` + o nome do auxiliar ou o seu código:

![This is a alt text.](/images/use.png "Comando use + nome do módulo.")

![This is a alt text.](/images/use_id.png "Comando use + número módulo.")

4.  Verifique os requisitos que o módulo possui , executando o comando `show options`.

![This is a alt text.](/images/show_options.png "Comando show options.")

Lembrando : Se o campo RHOSTS estiver em branco será necessário setá-lo.

RHOSTS é o campo do endereço de IP da máquina/servidor alvo do ataque/verficação.

Para setar o RHOSTS utilize o comando. Para o exemplo, utilizei o IP Localhost.
		
	msf6 > set RHOSTS <substituir_pelo_ip_maquina_alvo>
	
	
![This is a alt text.](/images/set_rhosts.png "Comando set.")


Após todas as configurações concluídas, basta executar o scanner, utilizando o comando `run`.

O módulo que utilizamos consiste em um scanner de portas TCP, ele apresentará na tela todas as portas TCP abertas para o endereço de IP setado em RHOSTS.

![This is a alt text.](/images/run_auxiliary.png "Modulo executado e finalizado")

Finalizado o uso do  scanner, se deseja utilizar outro módulo do Metasploit, utilize o comando `back`, para voltar ao console principal:

![This is a alt text.](/images/back.png "Modulo executado e finalizado")

Se deseja encerrar o programa, basta digitar o comando `exit`:

![This is a alt text.](/images/exit.png "Modulo executado e finalizado")


Desenvolvido por Luis Henrique

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licença Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Este obra está licenciado com uma Licença <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Atribuição-CompartilhaIgual 4.0 Internacional</a>.



