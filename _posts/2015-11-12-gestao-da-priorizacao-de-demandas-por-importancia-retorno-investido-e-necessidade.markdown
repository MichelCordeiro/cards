---
layout: post
title: Gestão da Priorização de Demandas por Importância, Retorno Investido e Necessidade
img: quebra-cabeca.jpg
---

Certamente você já se encontrou na situação de receber inúmeras demandas ao mesmo tempo. Todas com aquele senso de urgência singular dado por cada departamento. Nestes momentos, caro amigo PO, como você gerencia e organiza tudo ? Por onde começar ? Quais critérios estabelecer ?

Pois bem, sabemos que não há, de forma alguma, uma formula mágica e que cada empresa e situação pode ser tratada de uma forma única. Entretanto, existem várias técnicas que podem nos auxiliar nestas definições. Então, vamos analisar três abordagens que podem ser utilizadas para priorização. Aplicaremos elas em conjunto para cada momento de nossa gestão. Utilizaremos as técnicas <strong>GUT</strong>, <strong>Peso Relativo</strong> e <strong>MoSCoW</strong>.

Interessou ? Então vamos lá ?
<h2></h2>
<h2><strong>Definindo Importância</strong></h2>
Para iniciarmos não precisaremos ter grandes descrições das demandas, mas precisaremos entender a importância de cada uma para a organização. Para esta primeira abordagem utilizaremos a técnica <strong>GUT</strong> (Gravidade Urgência Tendência) para priorizarmos nosso backlog de solicitações.

O GUT é uma técnica de priorização por importância, obtida através da multiplicação dos três fatores analisados. São eles:
<ul>
	<li><strong>Fator de Impacto (Gravidade):</strong> É analisado o impacto da demanda quanto a sua gravidade. O que a não implementação da demanda gera de impacto a empresa?</li>
	<li><strong>Fator de Tempo (Urgência):</strong> É analisado o impacto da demanda quanto ao tempo de resposta para a solução. Quanto mais o tempo passar o que pode acontecer ?</li>
	<li><strong>Fator de Tendência (Tendência):</strong> É analisado o impacto da demanda quanto ao que pode acontecer com o passar do tempo sem a solução. Se nada for feito a situação tende a se manter, nada acontecer ou só a piorar ?</li>
</ul>
Uma boa prática, para auxilia-lo neste momento, é definir para cada escolha uma justificativa. Só não esqueça de um detalhe muito importante para o sucesso desta abordagem. Você está lidando com interesses distintos e não pode definir nenhum destes fatores sozinho. Então, recomendo a você juntar seus clientes em uma sala, apresentar a lista de demandas e propor o exercício em conjunto.

Peça que cada solicitante justifique cada um dos três fatores referente a sua demanda. Em seguida leia-os para todos e abra um espaço para uma breve explicação do demandante. Por fim, solicite a todos que avaliem todas as demandas dentro do intervalo de 1 a 5 sendo sempre o de maior número o de maior peso. Ao final deste processo multiplique GxUxT de cada um, por fim some o de todos. Atualize a planilha e veja aquele que obteve o maior valor.

Esta é uma forma democrática de negociar e sensibilizar a todos quanto as atuais demandas, lembre-se de ter nessa reunião pessoas com entendimento gerencial quanto as necessidades da empresa.

Organize suas demandas em uma planilha simples. Após obter os valores de prioridade, organize do maior para o menor.


|Demanda      |Gravidade   |Urgência  |Tendência    |Prioridade (GxUxT)  |
|-------------|:-----------|:---------|:------------|:-------------------|
|Demanda 1    |5	       |3		  |4            |60              	 | 
|Demanda 2    |3      	   |2		  |2			|12					 |
|Demanda 3    |4 		   |3		  |1			|12					 |
|Demanda 4    |4 		   |5		  |4			|80					 |
|Demanda 5    |3		   |3		  |3			|27					 |
{: .table .table-striped .table-hover}

Crie sua planilha com o peso para que o possa atribuir. Avalie ou escolha a melhor nomenclatura conforme a sua necessidade. Lembre-se do objetivo da abordagem. Um exemplo.


|Peso |Gravidade (impacto)	|Urgência (tempo)  			|Tendência (tendência)       |
|-----|:--------------------|:--------------------------|:---------------------------|
|5    |Extremamente Grave	|Precisa de ação imediata   |Irá piorar rapidamente      |
|4    |Muito Grave      	|É urgente		            |Irá piorar em pouco tempo	 |	
|3    |Grave 		        |O mais rápido possível		|Irá piorar			         |
|2    |Pouco Grave 		    |Pouco urgente		        |Irá piorar a longo prazo	 |	
|1    |Sem Gravidade		|Pode esperar		        |Não irá mudar			     |	
{: .table .table-striped .table-hover}


Excelente PO, já temos nossas prioridade de demandas organizada por importância, e o mais importante é que conseguimos isso alinhados com nossos clientes.
<h2></h2>
<h2><strong>Definindo ROI</strong></h2>
Entramos agora no segundo momento de nossa priorização. Sabemos por onde começar, mas precisamos de mais detalhes sobre as nossas demandas. Vamos levantar alguns épicos com nossos clientes do que eles precisam exatamente. Perceba que não estamos buscando nos aprofundar em detalhes. Estamos otimizando nosso trabalho não realizando esforço desnecessário. Isso é Lean, isso é o princípio ágil:
<blockquote><strong>Simplicidade: a arte de maximizar a quantidade de trabalho que não precisou ser feito.</strong></blockquote>
<strong> </strong>Perfeito. Utilizaremos neste momento a técnica do peso relativo. Alinhando junto ao nosso cliente prioridades em função do retorno investido. Não entrarei em grandes detalhes sobre esta técnica pois tem um post abordando somente ela. Para saber como ela funciona com detalhes confira <a href="https://michelcordeiro.github.io/menos-achismo-e-mais-tecnica/" target="_blank">Aqui</a>...
<h2><strong>Definindo as reais necessidades</strong></h2>
Agora que já sabemos o que é mais importante. Quais desejos trarão maior retorno e deverão ser priorizados, finalmente entraremos nos detalhes e escreveremos as estórias desejadas por nossos clientes.

Vamos agora priorizar nosso escopo entendendo as reais necessidades demandadas no projeto. Lembre-se sempre que fizemos isso tudo para entregar valor ao nosso cliente. Nossa missão de sermos assertivos ainda não terminou.

Então vamos finalizar nossa construção do product backlog utilizando a técnica <strong>MoSCow</strong>. Trata-se de uma técnica muito simples onde classificamos nossas estórias da seguinte forma:
<ul>
	<li><strong><span style="text-decoration:underline;">M</span>ust Have (Deve Ter)</strong>: Classificamos todas as estórias que são essenciais para nosso cliente. Perceba que é daqui que construiremos o nosso MVP.</li>
	<li><strong><span style="text-decoration:underline;">S</span>hould Have (Deveria Ter)</strong>: Classificamos as estórias que tem importância ao projeto, mas sua implementação não é essencial.</li>
	<li><strong><span style="text-decoration:underline;">C</span>ould Have (Poderia Ter)</strong>: Classificamos aqui as estórias que não são importantes aos nossos clientes, mas que costumam ser aquelas que geralmente causam o encanto. A famosa cereja do bolo. Não devemos ignorar essas estórias, pois podemos utiliza-la em estratégias de negociação ou até mesmo na evolução do produto.</li>
	<li><strong><span style="text-decoration:underline;">W</span>on’t Have for Now (Não Terá por enquanto)</strong>: Por fim classificamos as estórias que neste momento do projeto não geram valor ao nosso cliente. Lembre-se que o backlog sofre refinamento constante e as estórias estão sempre sujeitas a reclassificações conforme a necessidade e feedbacks do cliente.</li>
</ul>
Excelente. Saímos de um cenário nebuloso e construímos toda uma gestão e identificação de prioridades e necessidades alinhados com nosso cliente. Passamos a fazer a gestão de nosso portfolio de forma mais segura e assertiva. Só não esqueça que esse é um trabalho constante e sempre será preciso negociar e alinhar expectativas.

Agora que temos tudo pronto, vamos alinhar logo tudo com a equipe de desenvolvimento que já está ansiosa para iniciar a construção do MVP.

Espero que tenha gostado. Curta, Compartilha e Comente.

Abraço!