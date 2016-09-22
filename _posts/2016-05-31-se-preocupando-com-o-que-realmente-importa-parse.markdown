---
layout: post
title: Se preocupando com o que realmente importa - Instalação e Configuração do Parse
img: parse.png
---

Que tal abstrair um pouco de todo o esforço com o desenvolvimento de uma estrutura BackEnd. Pois é, se for produzir um app seria excelente dedicar o esforço do seu time focando na parte mobile, não é mesmo ?

Uma solução bastante interesse para atender essa necessidade é a utilização de ferramentas como o Parse, cujo produto da startup foi comprado pelo Facebook e teve seu código fonte aberto e disponível para que nós pudéssemos brincar com ele agora.

Mas antes de iniciar a instalação e você correr o risco de usar comandos que comprometam o seu Sistema Operacional, vamos aprender a utilizar uma outra ferramenta para evitarmos esse problema. Vamos começar então conhecendo um pouco do <a href="https://www.vagrantup.com/" target="_blank">Vagrant</a>.

O Vagrant nos permite simular diversos servidores e isolarmos nossos testes do nosso SO. Para não perdermos tempo aprofundando nesta ferramenta, vamos seguir o tutorial de instalação disponível no meu GitHub: <a href="https://github.com/MichelCordeiro/devops">https://github.com/MichelCordeiro/devops</a>. Em resumo, iremos instalar a ferramenta e instalar o Sistema Operacional Ubuntu. No exemplo do repositório git são configurados 4 servidores, mas para esse nosso tutorial iremos utilizar somente o servidor de Build.

Bem, como estamos apenas aproveitando um tutorial já existente, podemos até fazer uma pequena modificação no arquivo <strong><em>Vagrantfile</em></strong>, podemos deixa-lo da seguinte forma:
<blockquote>Vagrant.configure(2) do |config|

config.vm.box = "precise32"

config.vm.provider "virtualbox" do |v|

v.memory = 3072

v.cpus = 3

end

config.vm.define :build do |build_config|

build_config.vm.network :private_network, :ip =&gt; "192.168.33.20"

end

end</blockquote>
Pronto, agora vamos executar o comando:
<blockquote>vagrant up</blockquote>
E depois vamos logar no servidor de build usando o comando:
<blockquote>vagrant ssh build</blockquote>
<h2></h2>
<h2><strong>1 – Instalando e Configurando Node.js e ferramentas de desenvolvimento</strong></h2>
Vá para a raiz do seu servidor:
<blockquote>cd ~</blockquote>
Atualize os pacotes do servidor:
<blockquote>sudo apt-get update</blockquote>
Instale o recurso que lhe permitirá copiar url’s da internet para baixar ferramentas:
<blockquote>sudo apt-get install crul</blockquote>
Baixe o repositório do node para instalação:
<blockquote>curl -sL https://deb.nodesource.com/setup_5.x -o nodesource_setup.sh</blockquote>
Rode script de configuração do repositório node:
<blockquote>sudo -E bash ./nodesource_setup.sh</blockquote>
Vamos fazer a instalação do node e do git:
<blockquote>sudo apt-get install -y nodejs build-essential git</blockquote>
<h2></h2>
<h2><strong>2 – Instalando um exemplo do Parse Server App</strong></h2>
Vamos baixar o parse-server-example:
<blockquote>git clone https://github.com/ParsePlatform/parse-server-example.git</blockquote>
Vamos entrar no diretório baixado:
<blockquote>cd ~/parse-server-example</blockquote>
Vamos fazer a instalação das dependências do projeto:
<blockquote>npm install</blockquote>
<h2></h2>
<h2><strong>3 – Instalando MongoDB</strong></h2>
Vamos instalar o servidor NoSQL que o Parse utiliza. Para isso vamos configurar algumas chaves do Ubuntu para baixar arquivos que utilizaremos. Execute o comando:
<blockquote>sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10</blockquote>
Para executar o comando seguinte você pode esbarrar em problemas de permissão então vamos logar como root. Faça:
<blockquote>sudo su</blockquote>
<blockquote>echo "deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen" | tee -a /etc/apt/sources.list.d/10gen.list</blockquote>
<blockquote>apt-get -y updateapt-get -y install mongodb-10gen</blockquote>
<blockquote>exit</blockquote>
Caso queira ter certeza que o mongodb esta rodando, execute o comando:
<blockquote>sudo service mongodb status</blockquote>
<h2></h2>
<h2><strong>4 – Testando a aplicação de exemplo</strong></h2>
Vamos iniciar o serviço:
<blockquote>npm start</blockquote>
Você receberá uma mensagem informando que o DATABASE_URI ainda não foi configurado. Por hora vamos ignorá-la.

Vamos fazer algumas pequenas alterações nos arquivos de configuração. Dê um Ctrl + C para poder usar o terminal novamente e utilize o seguinte comando para editarmos o arquivo:
<blockquote>nano index.js</blockquote>
Vamos fazer algumas edições neste arquivo. Observe em negrito o trecho que você deve alterar:
<blockquote>// código //

var api = new ParseServer({

databaseURI: databaseUri || 'mongodb://<strong>192.168.33.20</strong>:27017/dev',

cloud: process.env.CLOUD_CODE_MAIN || __dirname + '/cloud/main.js',

appId: process.env.APP_ID || '<strong>parse</strong>',

masterKey: process.env.MASTER_KEY || '<strong>parse_key</strong>', //Add your master key here.$

serverURL: process.env.SERVER_URL || 'http://<strong>192.168.33.20</strong>:1337/parse',  // D$

liveQuery: {

classNames: ["Posts", "Comments"] // List of classes to support for query s$

}

});

// código //</blockquote>
O endereço IP que você está atribuindo no lugar do localhost é o já especificado no arquivo de configuração do vagrant.
<ul>
	<li>Na opção de APP_ID, você dará um nome de identificação para o app.</li>
	<li>Em MASTER_KEY você definirá uma chave de identificação.</li>
	<li>Em ServerURL você também colocará o IP já configurado no vagrant.</li>
</ul>
Salve as alterações com Ctrl + O e depois Ctrol + X para sair.

Inicie novamente o serviço usando
<blockquote>npm start</blockquote>
Agora vá em seu navegador e digite a url: <a href="http://192.168.33.20:1337/">http://192.168.33.20:1337/</a>

Você deverá ver a mensagem: “<em>I dream of being a website. Please star the parse-server repo on GitHub!</em>” ou algo similar.

Vamos agora rodar um teste de verificação de Post. Abra uma nova aba no servidor e execute o comando, cole todo o bloco de uma vez:
<blockquote>curl -X POST \

-H "X-Parse-Application-Id: <strong>parse</strong>" \

-H "Content-Type: application/json" \

-d '{"score":1337,"playerName":"Sammy","cheatMode":false}' \

http://<strong>192.168.33.20</strong>:1337/parse/classes/GameScore</blockquote>
Fique atento para os itens em negrito, pois foram os que definimos no arquivo de configuração anterior. Caso tenha utilizado algo diferente faça os ajustes nesse momento.
<h2></h2>
<h2><strong>5 – Instalando e configurando Parse Dashboard</strong></h2>
Para instalarmos o dashboard do Parse utilizaremos o comando:
<blockquote>sudo npm install -g parse-dashboard</blockquote>
Agora iremos criar um arquivo de configuração json para o nosso app no Parse. Os comandos são:
<blockquote>cd ~</blockquote>
<blockquote>touch parse-dashboard-config.json</blockquote>
<blockquote>nano parse-dashboard-config.json</blockquote>
Dentro do arquivo cole o seguinte código:
<blockquote>{

"apps": [

{

"serverURL": "http://<strong>192.168.33.20</strong>:1337/parse",

"appId": "<strong>parse</strong>",

"masterKey": "<strong>parse_key</strong>",

"appName": "<strong>parse</strong>"

}

],

"users": [

{

"user":"<strong>parse</strong>",

"pass":"<strong>parse</strong>"

},

{

"user":"user2",

"pass":"pass"

}

]

}</blockquote>
Por fim, execute o comando para registrar a configuração do arquivo de criamos:
<blockquote>parse-dashboard --config parse-dashboard-config.json --allowInsecureHTTP=1</blockquote>
Ufa, enfim chegamos ao fim!! Hehe

No seu console será exibida a mensagem: “<em>The dashboard is now available at <a href="http://0.0.0.0:4040/">http://0.0.0.0:4040/</a></em>”

Vá em seu navegador e coloque o IP fixo que estamos utilizando:
<blockquote>http://192.168.33.20:4040/</blockquote>
Será pedido o usuário e senha que definimos em nosso script. Então autentique com:
<ul>
	<li>User: <strong>parse</strong></li>
	<li>Password: <strong>parse</strong></li>
</ul>
Em seu navegador você verá a área de dashboard do Parse.

<img class="alignnone size-full wp-image-352" src="https://jcodeshell.files.wordpress.com/2016/05/captura-de-tela-2016-05-30-acc80s-20-29-24.png" alt="Captura de Tela 2016-05-30 às 20.29.24" width="1252" height="686" />

Pronto, missão cumprida!!!

Agora você já pode começar a brincar.

Abraço!!
<h2></h2>
<h2>Referências</h2>
https://www.digitalocean.com/community/tutorials/how-to-run-parse-server-on-ubuntu-14-04

https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-14-04

https://github.com/ParsePlatform/parse-dashboard

https://github.com/ParsePlatform/parse-server

https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-12-04

http://stackoverflow.com/questions/13112400/gpgkeys-key-7f0ceb10-not-found-on-keyserver-response-while-try-to-install-mon

<a href="https://www.youtube.com/watch?v=agXcuQhWCoU&amp;feature=youtu.be" target="_blank">YouTube - Install Parse Server and Parse Dashboard to Digital Ocean - Part 1/3</a>

&nbsp;

&nbsp;