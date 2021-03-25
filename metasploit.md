# METASPLOIT FRAMEWORK


O Metasploit é um projeto abragente da área de segurança da informação, que inclui informações e auxilia na busca de vulnerabilidades em sistemas através do uso de exploits, entre outros recursos. <br>
É muito utilizada nos testes de penetração("Pentests") e utilizada por Hackers para invasão.

OBS: O uso do material exposto e a sua aplicação é inteiramente responsabilidade do usuário,
não me responsabilizo pela forma de uso e intenções.



A ferramenta foi desenvolvida em 2003 pelo programador HD Moore, e comprado pela empresa de segurança Rapid 7

Atualmente existem as versões Pro e Open Source(Metasploit Framework),neste tutorial vamos falar sobre a versão Open Source,
o Metasploit Framework.


### Como instalar:


A versão Open Source está diponível no GitHub,você pode acessar o repositório através do link abaixo:
 

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

Irá apresentar uma tela incial no terminal, e algumas informações sobre a aplicação.

![This is a alt text.](/images/splash_screen.png "Metasploit initial screen.")



## Principais comandos do Metasploit

##### msfconsole

Comando utilizado para abrir o console do Metasploit

##### banner

Exibe o lolgoltkipop e a tela inicial, colma s ifformações de quantos módulos possui disponível para a versão dop aplicativo


##### search

search type : exploit =   busca xploits
permite procurar por tipo especifico de módulo


	msf6 > search 

##### help

Comando de ajuda sobre o Framework Mertasploit.Exibe todos os comandos disponíveis e sua forma de uso.


	msf6 > help

![This is a alt text.](/images/help_screen.png "Execução do comando help.")

Comando help + comando específico do Metasploit, ele exibirá todos os parâmetros que acompanham o comando
Ex.
				
	msf6 > help search
	
![This is a alt text.](/images/help_search_screen.png "Execução do comando help+ comando.")


##### info

Obtém informações sobre o exploit, ou módulo desejado.
para realizar a consulta, digite info + modulo_desejado


	msf6 > info 	

No exemplo da imagem abaixo, foi realizada a busca das informações de um exploit.

![This is a alt text.](/images/info_screen.png "Comando info")

É possivel buscar as informações apenas com a numeração do exploit ou módulo desejado.
 
No exemplo abaixo foi buscado um PAYLOAD através do seu número de identificação.
 
![This is a alt text.](/images/info_screen_2.png "Execução do comando info.")
 

##### use

Comando utilizado para selecionar e carregar exploits, auxiliares, payloads,etc;

	msf6> use <nome_do_exploit_ou_auxilary_etc>


##### show options

Apresenta na tela, os comandos específicos do módulo executado e sendo utilizado.
Mostrará também os requisitos para  que o exploit, auxiliary ou o  módulo escolhido seja executado de maneira correta.

	msf6> show options <nome_do_exploit/auxiliary/etc>

##### back

Retornar ao console inicial do Metasploit Framework


##### exploit


Executa o exploit ou outro módulo selecionado.


##### run

Da mesma forma que o comando exploit, executa o exploit ou módulo selecionado


##### set

Define algum recurso ou requisito que o módulo exige obrigatoriamente para o funcionamento.

Utilizando o comando citado acima "show options", será exibido quais os requisitos necessários, 
para que o módulo seja executado da forma correta.



## O que significa


##### Exploit

 Exploits(Exploradores)são sequência de comandos ou fragmentos de código que explora por uma vulnerabilidade no sistema operacional  ou na aplicação em questão;
 Estes Exploits são buscados e apresentados no Metasploit Framework, através do comando "search exploit", por exemplo.
 
 Além do framework, você pode localizar exploits ou outros módulos desejados na internet,como no site abaixo,
 você encontra uma database de exploits e outros módulos.
 
 
 https://www.exploit-db.com/
 

##### Payload

  Arquivo malicioso, geralmente de formato executável que contém a "carga",que será utilizado para realizar o ataque.
  
  O arquivo que será instalado/executado na máquina alvo do ataque,ocasiando algum problema ou gerando alguma vulnerabilidade(facilitação).
  
  Ex. envio de email com um arquivo.pdf, infectado com um  programa , que será instalado/executado na máquina alvo quando o arquivo é aberto.

##### Auxiliary

Auxiliary(auxiliares), como o nome já diz, são um tipo de módulo , de ferramentas utilitárias, que auxiliam num possível ataque ou alguma necessidade de uso.
Scanners são um exemplo de auxiliar.

##### Evasion :

Módulo espcífico para realizar evasão de anti virus, firewall;


## Exemplo prático

Agora será apresentado um exemplo prático utilizando alguns dos recursos apresentados anteriormente.

Para este exemplo , utilizaremos um auxiliar, um scanner de portas TCP.


1 -  Acesse o terminal do Metasploit, utilizando o comando msfconsole

img

2 - Após o programa iniciado , busque pelo exploit ou módulo desejado , utilizando o comando search + módulo desejado
neste caso será o auxiliar auxiliary/scanner/portscan/tcp

img

3 - Selecione o auxiliar desejado, utilizando o comando use + o nome do auxiliar ou o seu código

img

4 - Verifique os requisitos que o módulo possui , executando o comando show options.

img

Lembrando :Se o campo RHOSTS estiver em branco será necessário setá-lo. 
RHOSTS se refere ao endereço de IP da máquina/servidor alvo do ataque/verficação.

img

Para setar o RHOSTS utilize o comando
		
	msf6> set RHOSTS <substituir_pelo_ip_maquina_alvo>
img


Após todas as configurações concluídas, basta execeutar o scanner, utilizando o comando run:

img

Para este scanner, ele apresentará na tela todas as portas TCP abertas para o endereço de IP setado em RHOSTS.

img



