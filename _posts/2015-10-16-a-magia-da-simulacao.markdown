---
layout: post
title: A magia da simulação
img: simulacao.png
---

Fala-se muito da importância de se prever impactos da mudança e de se otimizar processos com o intuito de reduzir custos ou tempo de execução. O curioso é que não vemos com tanta frequência o discurso da busca pela simulação dos processos para análise de cenários para melhor tomada de decisão antes da transformação ocorrer.

Imagine você a ter que reduzir custos utilizando apenas o seu feeling empresarial. Poderá realizar essa atividade com maestria durante algumas oportunidades, mas pense o quão arriscado está sendo atuar na mudança de processos sem antes ter a oportunidade de simular cenários e descobrir o que seria o melhor para sua organização.

Neste post vou apresentar a vocês um exemplo muito simples, mas que trará a dimensão do poder desta abordagem.

Vamos analisar um processo de aprovação de currículo. Não trabalharemos com nada complexo pois o foco é apenas mostrar um único exemplo da utilização da simulação. Entendendo a abordagem você poderá seguir por caminhos mais detalhados e se quiser estarei nos comentários para interagir e criar posts com esse intuito caso exista feedback para o propósito.

[caption id="attachment_243" align="aligncenter" width="1085"]<a href="https://jcodeshell.files.wordpress.com/2015/10/as-is-aprovac3a7c3a3o-de-curriculo-exemplo.png" target="_blank"><img class="wp-image-243 size-full" src="https://jcodeshell.files.wordpress.com/2015/10/as-is-aprovac3a7c3a3o-de-curriculo-exemplo.png" alt="As Is - Aprovação de Curriculo - exemplo" width="1085" height="842" /></a> As Is - Aprovação de Curriculo - exemplo[/caption]

O processo acima aborda uma análise de currículo. Vamos fazer a leitura em conjunto instanciando processo. Acompanhe o percurso do token na descrição:
<blockquote>O processo inicia com o candidato realizando o envio do currículo. O mesmo é recebido e separado para avaliação, esta atividade é realizada por uma secretaria. A mesma analisa se o currículo enviado é da área de TI ou da área Administrativa. Neste momento de triagem o token pode divergir para uma das duas áreas. Vamos analisar quando a divergência segue o caminho:</blockquote>
<ul>
	<li>
<blockquote><strong>TI:</strong> O Gerente da TI realiza uma análise do currículo, esta análise resulta em mais duas novas possibilidades. No caminho feliz, o token segue com o currículo aprovado e o gerente realiza o agendamento da prova técnica do candidato e finaliza o processo. Caso o currículo não seja aprovado o processo é finalizado com uma mensagem de reprovação.</blockquote>
</li>
	<li>
<blockquote><strong>Administrativo:</strong> O Gerente do Administrativo faz a análise do currículo do candidato. Esta ação resulta em duas novas possibilidades. Se o currículo for aprovado o gerente agenda uma entrevista e finalizado o processo. Caso o currículo não seja aprovado o processo é finalizado com uma mensagem de reprovação.</blockquote>
</li>
</ul>
Bem, agora que já entendemos o processo vamos avaliar algumas informações importantes.

Você já deve ter mapeado quem são os participantes, então vamos aqui revisa-los, porém acrescento algumas informações que serão importantes para nossa simulação. São eles:
<table style="height:291px;" width="528">
<tbody>
<tr>
<td width="98">
<p style="text-align:center;"><strong>Participantes</strong></p>
</td>
<td style="text-align:center;" width="64"><strong>Qtd</strong></td>
<td style="text-align:center;" width="104"><strong>Custo por Hora</strong></td>
</tr>
<tr>
<td width="98">Candidato</td>
<td width="64">
<p style="text-align:center;">500</p>
</td>
<td width="104">
<p style="text-align:center;">0 R$/h</p>
</td>
</tr>
<tr>
<td width="98">Secretária</td>
<td width="64">
<p style="text-align:center;">1</p>
</td>
<td width="104">
<p style="text-align:center;">46 R$/h</p>
</td>
</tr>
<tr>
<td width="98">Gestor de TI</td>
<td width="64">
<p style="text-align:center;">1</p>
</td>
<td width="104">
<p style="text-align:center;">159 R$/h</p>
</td>
</tr>
<tr>
<td style="text-align:center;" width="98">
<p style="text-align:left;">Gestor de Admin</p>
</td>
<td style="text-align:center;" width="64">2</td>
<td width="104">
<p style="text-align:center;">159 R$/h</p>
</td>
</tr>
</tbody>
</table>
Excelente. Agora temos bem claro quem são nossos participantes, a sua quantidade e quanto custa a hora de cada um. Estamos prontos para simular nosso processo de avaliação de currículo.

Iremos analisar dois aspectos neste exemplo, custo e utilização do recurso. É possível considerar outras situações e extrair mais informações para tomada de decisão, mas vamos nos manter nestes dois únicos pontos. Vejamos então o resultado da nossa simulação:

[caption id="attachment_247" align="aligncenter" width="1280"]<a href="https://jcodeshell.files.wordpress.com/2015/10/c1-simulac3a7c3a3o.png" target="_blank"><img class="wp-image-247 size-full" src="https://jcodeshell.files.wordpress.com/2015/10/c1-simulac3a7c3a3o.png" alt="C1- Simulação" width="1280" height="758" /></a> C1- Simulação do As Is[/caption]

Para este cenário estabeleci a duração das atividades e o percentual dos gateways nos pontos de divergência. Em nosso exemplo iremos nos ater em dois pontos, manteremos a mesma configuração para as mudanças de cenário.
<table width="386">
<tbody>
<tr>
<td width="85"><strong>Resource</strong></td>
<td width="61"><strong>Utilization</strong></td>
<td width="87"><strong>Total fixed cost</strong></td>
<td width="82"><strong>Total unit cost</strong></td>
<td width="71"><strong>Total cost</strong></td>
</tr>
<tr>
<td width="85">Secretaria</td>
<td width="61">
<p style="text-align:center;">8,33%</p>
</td>
<td width="87">
<p style="text-align:center;">0</p>
</td>
<td width="82">
<p style="text-align:left;">R$2.760,00</p>
</td>
<td width="71">R$2.760,00</td>
</tr>
<tr>
<td width="85">Avaliador Adm</td>
<td width="61">
<p style="text-align:center;">5,20%</p>
</td>
<td width="87">
<p style="text-align:center;">0</p>
</td>
<td width="82">
<p style="text-align:left;">R$11.897,97</p>
</td>
<td width="71">R$11.897,97</td>
</tr>
<tr>
<td width="85">Avaliador TI</td>
<td width="61">
<p style="text-align:center;">2,55%</p>
</td>
<td width="87">
<p style="text-align:center;">0</p>
</td>
<td width="82">
<p style="text-align:left;">R$2.914,47</p>
</td>
<td width="71">R$2.914,47</td>
</tr>
<tr>
<td width="85">Candidato</td>
<td width="61">
<p style="text-align:center;">0,01%</p>
</td>
<td width="87">
<p style="text-align:center;">0</p>
</td>
<td width="82">R$-</td>
<td width="71">R$-</td>
</tr>
<tr>
<td width="85"></td>
<td width="61"></td>
<td width="87"></td>
<td width="82"></td>
<td width="71"></td>
</tr>
<tr>
<td width="85"></td>
<td width="61"></td>
<td width="87"></td>
<td width="82">Custo Total</td>
<td width="71">R$17.572,44</td>
</tr>
</tbody>
</table>
O resultado da nossa simulação nos dá uma informação importante. Quantos de nós em nossos processos e rotinas, já tão conhecidas e corriqueiras, sabemos evidenciar quanto nos custa o passo a passo que seguimos. Sabemos responder com clareza ou estimar de forma contundente quanto custa nosso processo ?

A simulação nos possibilita esta resposta assim como a identificação dos gargalos em nosso processo!!

Excelente, estamos começando a entender o poder que este recurso nos dá. Agora, você já deve ter percebido que um processo tão simples está tendo um custo elevado. Você conseguiu identificar quem poderia estar tornando o processo tão caro ?

É isso mesmo, os nossos avaliadores são gerentes e possuem o valor da hora elevada. O nosso processo não está otimizando o tempo destes recursos e com isso está se tornando caro. Então, precisamos otimizar as atividades realizadas por estes recursos para que consigamos um custo menor nessa execução.

Aposto como você já está ai cheio de ideias para melhorar este processo e reduzir este custo. Se quiser deixe a sua ideia de melhoria nos comentários para debatermos posteriormente.

Então vamos ao nosso To Be. Veja só, nós mapeamos nosso processo. Desenhamos e analisamos. Identificamos pontos de melhoria e agora iremos desenhar um processo proposto. Veja abaixo a seguinte proposta:

[caption id="attachment_248" align="aligncenter" width="1143"]<a href="https://jcodeshell.files.wordpress.com/2015/10/to-be-aprovac3a7c3a3o-de-curriculo-exemplo.png" target="_blank"><img class="wp-image-248 size-full" src="https://jcodeshell.files.wordpress.com/2015/10/to-be-aprovac3a7c3a3o-de-curriculo-exemplo.png" alt="To Be - Aprovação de Curriculo - exemplo" width="1143" height="897" /></a> To Be - Aprovação de Curriculo - exemplo[/caption]

Acompanhe. Nesta proposta fizemos as seguintes alterações no processo.

A escolha quanto a área ficou com o candidato, que em nosso exemplo não nos gera custo. O mesmo escolhe a área e então encaminha o currículo. Perceba que eliminamos a triagem feita pela secretaria. O direcionamento é feito diretamente ao gestor responsável.

A última alteração que foi realizada é quanto ao executor das tarefas de agendamento que passaram a ser feitas pela secretaria, ou seja, os gestores passaram apenas a avaliar os currículos.

E então, será que estas pequenas alterações renderam algum resultado ?

[caption id="attachment_249" align="aligncenter" width="1280"]<a href="https://jcodeshell.files.wordpress.com/2015/10/to-be-c1-simulac3a7c3a3o.png" target="_blank"><img class="wp-image-249 size-full" src="https://jcodeshell.files.wordpress.com/2015/10/to-be-c1-simulac3a7c3a3o.png" alt="To Be - c1 - Simulação" width="1280" height="757" /></a> To Be - Simulação[/caption]

Vamos analisar a simulação do nosso processo proposto. Veja:

Foram mantidas as mesmas parametrizações de proporção nos gateways e duração das atividades. Deste novo cenário obtivemos o seguinte resultado:
<table width="386">
<tbody>
<tr>
<td width="85"><strong>Resource</strong></td>
<td width="61"><strong>Utilization</strong></td>
<td width="87"><strong>Total fixed cost</strong></td>
<td width="82"><strong>Total unit cost</strong></td>
<td width="71"><strong>Total cost</strong></td>
</tr>
<tr>
<td width="85">Secretaria</td>
<td width="61">
<p style="text-align:center;">4,93%</p>
</td>
<td width="87">
<p style="text-align:center;">0</p>
</td>
<td width="82">R$1.633,00</td>
<td width="71">R$1.633,00</td>
</tr>
<tr>
<td width="85">Avaliador Adm</td>
<td width="61">
<p style="text-align:center;">3,48%</p>
</td>
<td width="87">
<p style="text-align:center;">0</p>
</td>
<td width="82">R$7.977,03</td>
<td width="71">R$7.977,03</td>
</tr>
<tr>
<td width="85">Avaliador TI</td>
<td width="61">
<p style="text-align:center;">1,37%</p>
</td>
<td width="87">
<p style="text-align:center;">0</p>
</td>
<td width="82">R$1.562,97</td>
<td width="71">R$1.562,97</td>
</tr>
<tr>
<td width="85">Candidato</td>
<td width="61">
<p style="text-align:center;">0,01%</p>
</td>
<td width="87">
<p style="text-align:center;">0</p>
</td>
<td width="82">R$-</td>
<td width="71">R$-</td>
</tr>
<tr>
<td width="85"></td>
<td width="61"></td>
<td width="87"></td>
<td width="82"></td>
<td width="71"></td>
</tr>
<tr>
<td width="85"></td>
<td width="61"></td>
<td width="87"></td>
<td width="82">Custo Total</td>
<td width="71">R$11.173,00</td>
</tr>
</tbody>
</table>
Sensacional. Percebam que com nossas alterações, mínimas, no processo conseguimos uma redução de R$ 6.399,44, ou seja, 36% do custo. Isso foi possível pois reduzimos a carga de trabalho nos recursos que possuem as horas mais caras no processo.

Nós mapeamos o processo, desenhamos o modelo As Is. Analisamos e com base em uma fundamentação tornou-se possível propor um cenário de melhorias, To Be.

Conseguimos então propor mudanças e mensurar os impactos das mesmas sem partirmos para implementação real. Apenas simulando o processo conseguimos identificar custos, gargalos, sugerir melhorias, analisar possibilidades, medir impactos, quantificar e justificar o retorno da mudança proposta em uma escala mínima de um pequeno exemplo.

A simulação é sem dúvida um recurso poderoso no processo de mudança e melhoria contínua. Espero que tenha ficado claro para você e que tenha despertado o seu interesse em tirar proveito deste recurso.

Abraço!