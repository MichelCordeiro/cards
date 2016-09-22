---
layout: post
title: The Bug Hunter
img: the-bug-hunter.png
---


Neste post irei explicar um pouco sobre o processo The Bug Hunter que criei para ajudar na qualidade do produto entregue ao cliente. Vamos tratar sobre o modelo e algumas boas práticas, mas antes quero deixar claro os resultados obtidos em uma equipe!

<div class="panel panel-primary">
<div class="panel-heading">
    <h3 class="panel-title">Motivação e Resultados:</h3>
</div>
    <div class="panel-body">
        Em um cenário onde não se possui uma equipe de testes, na reta final da entrega de um projeto, rodamos o processo e tivemos como resultados alguns números interessantes.
<ul>
	<li>Em uma semana de competição <strong>foram identificados 25 bugs;</strong></li>
	<li>Dos 25 listados <strong>foram corrigidos durante a competição 21 bugs;</strong></li>
	<li><strong>Os bugs foram encontrados e corrigidos, também, por membros que não faziam parte do time de desenvolvimento do projeto</strong> e estavam alocados para outras entregas, que no seu tempo livre participavam da competição;</li>
	<li><strong>A diferença do primeiro para o segundo colocado foi de apenas 3 pontos</strong>, sendo que o segundo colocado fazia parte de outro projeto;</li>
	<li>O time se integrou e os competidores passaram a olhar com mais detalhes o projeto. <strong>O time ficou motivado e não tratou do desafio como trabalho, mas como um jogo que era divertido jogar.</strong></li>
	<li><strong>A integração do time só ocorreu de fato quando o gestor da área resolveu participar e começou a pontuar.</strong> Quando foi disparado o e-mail para o setor com a pontuação do gestor o time reagiu. Este foi um fator chave para o sucesso da competição e neste ponto podemos parar na seguinte reflexão:</li>
</ul>
    </div>
</div>


<blockquote>Quando um líder quer que seus liderados façam algo. O líder vai lá e faz primeiro, desta forma seus liderados o seguirão, não por uma ordem, mas por um exemplo.</blockquote>

<h3>O que é o The Bug Hunter?</h3>
<p style="padding-left:30px;">Como o nome em si sugere trata-se de um processo que deve ser encarado como uma competição, onde o vencedor é aquele que mais encontra e corrige bugs de um determinado projeto. A ideia é simples e os resultados também.</p>

<h3>Em que tipo de equipe é viável rodar este processo?</h3>
<p style="padding-left:30px;">Você pode ter sua equipe organizada em um "Testers Team", um time responsável por verificar todas as atividades previstas do desenvolvimento do seu projeto, ou simplesmente não possuir essa estrutura e rodar o modelo com seu time padrão multitarefa e multidisciplinar, isso não irá importar pois a questão além de tudo é motivacional e você poderá extrair resultados satisfatórios em ambos os casos.</p>

<h3>Em que fase do meu projeto devo aplicar o The Bug Hunter?</h3>
<p style="padding-left:30px;">Inicialmente você deve analisar como estão sendo feitas suas entregas junto ao cliente. Se você está trabalhando de forma incremental como entregas parciais cabe então para cada uma dessas fases a aplicação da competição. É interessante realizar a competição com o prazo de 1 semana para a entrega do produto completo ou modulo.</p>

<h3>Quem deve participar do The Bug Hunter?</h3>
<p style="padding-left:30px;">A beleza do jogo está em abrir a competição para todo o setor, independente de ser desenvolvedor da linguagem dominante do projeto ou de fazer parte do time de desenvolvimento, alias conseguir o envolvimento daqueles que não fazem parte do time que está codificando é o grande trunfo da integração entre todos para a competição.</p>

<h3>Como faço para o time avaliar o projeto?</h3>
<p style="padding-left:30px;">O ideal é que você disponibilize no seu servidor web o projeto apontando para o seu ambiente de teste. Dessa forma todos poderão participar, independente de terem participado ou não do desenvolvimento. Outra opção é liberar o fonte do projeto para todos, para que possam baixar e rodar localmente em suas máquinas, mas atenção, fique atento nos commits e controle "quem está fazendo, o que, e aonde" para evitar que ocorram conflitos no código bem as vésperas de disponibiliza-lo ao cliente.</p>

<h3>Como faço o controle do The Bug Hunter?</h3>
<p style="padding-left:30px;">Você pode realizar o controle através de uma simples planilha de excel. Lembre-se que quem quer fazer não precisa da ferramenta perfeita, precisa da ideia e da capacidade de gerir. É interessante que durante todos os dias de competição você encaminhe um e-mail para todo o setor atualizando os bugs encontrados e o ranking atual. Isso ajudará a estimular quem já participa e quem apenas está achando curiosa a competição.</p>

<h3>Que premiação devo entregar?</h3>
<p style="padding-left:30px;">Você mais do que ninguém conhece a realidade do seu setor e sabe muito bem as coisas que deixarão seu time animado. A única coisa que não recomendo é que se dê dinheiro como retorno para a competição, isso não criará uma cultura positiva e lembre-se que este modelo é apenas uma forma de motivar que seu time faça melhor ainda um trabalho que já é obrigação. Você pode adotar turnos ou dias de folga, pizzas, rodízio em algo. Pense sempre em uma forma de integrar todos e que seja positiva para todo o ambiente.</p>

<h3>O que preciso ter para iniciar o The Bug Hunter?</h3>
<p style="padding-left:30px;">Como premissa básica, possuir seu projeto no estágio mais próximo de ser disponibilizado ao cliente, isso é algo que você, que conhece bem o escopo, poderá determinar.</p>

<ul style="padding-left:30px;">
	<li>Você deverá determinar a duração da competição, quando vai iniciar e terminar.</li>
	<li>Qual será a premiação para o vencedor.</li>
	<li>Como será o regulamento, quais as regras da competição.</li>
</ul>
Sanadas estas questões inicias já podemos partir para uma visão mais prática do processo.
<h2><strong><em>Definição de Intervalo, Pontuação, Premiação e Regulamento</em></strong></h2>
<p style="text-align:center;">Vou exemplificar para vocês como poderia ser um modelo da planilha para o controle:</p>
<a href="http://jcodeshell.files.wordpress.com/2014/05/exemplo_tbh.png"><img id="i-220" class="size-full wp-image aligncenter" src="http://jcodeshell.files.wordpress.com/2014/05/exemplo_tbh.png?w=567" alt="Imagem" /></a>

No exemplo acima montei uma tabela me baseando em 10 linhas, informando os pontos chaves para começar a disputa. Informei a duração e estabeleci das regras.
<ul>
	<li>Vamos entender cada linha:</li>
</ul>
<strong>Linha 1:</strong> Defini para o processo The Bug Hunter o projeto que será avaliado para a competição;

<strong>Linha 2:</strong> Defino em uma coluna os Tipos de Bug que irão pontuar e na outra os detalhes do regulamento.

<strong>Linha 3:</strong> Defino na primeira coluna que todo Bug de Visão valerá 1 ponto e na coluna ao lado o intervalo que será feita a avaliação;

<strong>Linha 4:</strong> Defino na primeira coluna o segundo tipo de bug, sendo esse de Negócio com peso de 3 pontos e ao lado já informo a premiação, sendo que o campeão ganhará uma pizza;

<strong>Linha 5:</strong> Defino o ultimo tipo de bug na primeira coluna, sendo Bug de DAO para persistências de dados, valendo também 3 pontos. Ao lado continuo dando ênfase para a premiação;

<strong>Linha 6:</strong> Defino neste ponto de forma clara o intervalo, que dia exato inicia e que dia exato termina.

<strong>Linha 7:</strong> Estabeleço o primeiro ponto de como funciona. Neste momento defino como farei o controle e como o competidor deve proceder para pontuar, já valorizando os pontos para aquele que encontra e, principalmente, corrige o problema;

<strong>Linha 8:</strong> Estabeleço neste momento o segundo ponto de funcionamento, e neste instante dou a possibilidade de qualquer pontuar, bastando apenas listar os problemas encontrados;

<strong>Linha 9:</strong> Neste ponto elimino os "espertinhos" que queiram pontuar uma vez para cada bug encontrado e para cada um desses bugs ganhar novos pontos efetuando em um segundo momento as correções;

<strong>Linha 10:</strong> Na última linha deixo claro quem pode participar da competição.
<h2><em><strong>Controle e Acompanhamento de Resultados</strong></em></h2>
Agora vamos a um exemplo de como seria o acompanhamento e controle.

<a href="http://jcodeshell.files.wordpress.com/2014/05/exemplo_tbh_acompanhamento.png"><img id="i-223" class="size-full wp-image aligncenter" src="http://jcodeshell.files.wordpress.com/2014/05/exemplo_tbh_acompanhamento.png?w=650" alt="Imagem" /></a>

A primeira linha da tabela é o cabeçalho com as informações que devem ser preenchidas.

Repare o Seguinte ponto!

Na linha 2 o Thor encontra o Bug e ele mesmo corrige, por ser um erro de Negocio valia 3 pontos, como foi ele mesmo que corrigiu ganhou os 3x2 ficando com 6 pontos. Se ele apenas tivesse encontrado o erro ficaria apenas nos 3 e o bug ficaria em aberto para que outro pudesse corrigir e pontuar.

Na ultima linha o Cap. America encontra um bug de Visão e ganha 1 ponto, mas ele não corrige e deixa em aberto. O Thor chega e corrige e ganha o ponto do "Cap.America x 2", ou seja, 1x2 ficando com 2 pontos e passando a frente do Cap. America que por ter apenas encontrado ficou com 1. Dessa forma estimula-se e encoraja-se a correção.

É interessante categorizar os competidores por cores, isso facilita na contagem dos pontos.

Se você chegou até o final deste extenso post saiba que trata-se de uma ideia simples e não original que foi apenas tratada com seriedade e organizada através de uma visão de processo. Se gostou do modelo sinta-se a vontade para conversar e aplicar no seu setor e se puder me retorne com o resultado que conseguiu, seja ele positivo ou negativo.

Valeu pessoal até a próxima.

Abraço!