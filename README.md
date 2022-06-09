#  O OSCAR VAI PARA? 

<h3>Na atividade "O oscar vai para?" nós, da Equipe 3, fizemos diversas mudanças no banco de dados em SQL utilizando XAMPP, PhpMyAdmin e MySQL onde alteramos e colocamos informações sobre as cerimônias do Oscar, mais abaixo terá todas as questões e respostas de tudo que foi acionado e alterado do banco.</h3>



<h2>E o Oscar vai para... ?</h2>
Muito bem, Pessoal... 

Hoje vamos trabalhar com o Oscar.
A ideia de premiar ou ser premiado é para reconhecer:
- Reconhecer uma qualidade
- Reconhecer um atributo
- Reconhecer o esforço... 

Reconhecer sempre.

Nem todos os prêmios são merecidos e nem todos que merecem ganham. 
Então vale mesmo a pena, premiar? 


##
<h3>Aqui vai uma ajudinha:</h3>
Nesse exercício vamos usar alguns comandos bem básicos como 

<code>SELECT COUNT(*) FROM tabela_exemplo WHERE coluna_exemplo = "Novo Valor";</code>

<code>SELECT * FROM tabela_exemplo WHERE coluna_exemplo = "Novo Valor"  AND coluna_exemplo2 = "Outro Valor";</code>

<code>SELECT * FROM tabela_exemplo WHERE coluna_exemplo LIKE 'eda';</code>

<code>UPDATE tabela_exemplo SET coluna_exemplo = "Novo Valor" WHERE id = 1;</code>

<code>INSERT INTO tabela_exemplo (coluna_1,, coluna_2) VALUES ("VALOR 1", "VALOR 2");</code>

##
<h4>1. Quantas vezes Natalie Portman foi indicada ao Oscar?</h4>

3 vezes Natalie Portman foi indicada ao Oscar.
<code>SELECT * FROM `oscar` WHERE name = 'Natalie Portman';</code> ou 
<code>SELECT COUNT(*) FROM oscar WHERE name = 'Natalie Portman';</code>

##
<h4>2. Quantos Oscars Natalie Portman ganhou?</h4>

Oscars Natalie Portman ganhou 1 Oscar.
<code>SELECT * FROM `oscar` WHERE name = 'Natalie Portman' AND winner = 'True';</code> ou 
<code>SELECT COUNT(*) FROM oscar WHERE name = 'Natalie Portman' AND winner = 'True'</code>
##
<h4>3. Amy Adams já ganhou algum Oscar?</h4>

Amy Adams não ganhou nenhum Oscar.
<code>SELECT * FROM `oscar` WHERE name = 'Amy Adams' AND winner = 'True';</code>
##
<h4>4. Alguém já ganhou um Oscar e tem o seu primeiro nome?</h4>

Leonardo DiCaprio
<code>SELECT name FROM `oscar` WHERE name LIKE '%Leonardo%' AND winner = 'True';</code>
##
<h4>5. Toy Story 3 ganhou um Oscar em quais anos?</h4>

Toy Story 3 ganhou um Oscar em 2011

<code>SELECT film, year_ceremony FROM `oscar` WHERE film = "Toy Story 3" AND winner = 'True';</code>
##
<h4>6. Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme"?</h4>

A categoria que tem mais Oscars foi a de Melhor Ator com 872 atores, sendo principais e secundários contra 333 da categoria de Melhor Filme.

<code>SELECT COUNT(*) FROM oscar WHERE category LIKE '%BEST PICTURE%';</code>

<code>SELECT COUNT(*) FROM oscar WHERE category LIKE %ACTOR%;</code>
##
<h4>7. O primeiro Oscar para melhor Atriz foi para quem? Em que ano?</h4>

Janet Gaynor ganhou o primeiro Oscar para melhor Atriz no ano de 1928.

<code>SELECT name, year_ceremony FROM `oscar` WHERE `category` = 'ACTRESS' AND winner = 'True' ORDER BY `oscar`.`year_ceremony` ASC;</code>
##
<h4>8. Na categoria Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0.</h4>

<code>UPDATE `oscar` SET winner = '1' WHERE winner = 'True';</code>

<code>UPDATE `oscar` SET winner = '0' WHERE winner = 'False';</code>
##
<h4>9. Em qual edição do Oscar "Crash" ganhou o prêmio?</h4>

"Crash" ganhou o prêmio na edição 78 do Oscar.

<code>SELECT film, ceremony FROM `oscar` WHERE film = 'Crash' AND winner = '1';</code>
##
<h4>10. Que filme merecia ganhar um Oscar e não ganhou?</h4>

Shrek 2

<code>SELECT film, category, year_ceremony FROM `oscar` WHERE film = 'Shrek 2' AND winner = '1'; </code>
##
<h4>11. Bom... dê um Oscar para esse filme, então.</h4>

<code>UPDATE `oscar` SET `winner`='1' WHERE film = 'Shrek 2' AND category = 'ANIMATED FEATURE FILM'; </code>

<code>SELECT film, category, year_ceremony, winner FROM `oscar` WHERE film = 'Shrek 2' AND winner = '1'; </code>
##
<h4>12. O filme Central do Brasil aparece no Oscar?</h4>

O filme Central do Brasil (Central Station) aparece no Oscar.
##
<h4>13. Aliás... Qual sua opinião sobre central do Brasil</h4>

Nunca assisti central do Brasil.
##
<h4>14. Inclua no banco 7 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem.</h4>

<h5>O código está abaixo, porém para melhor visualização dos filmes, ano e categorias escolhidas são: </h5>
2010 	CINEMATOGRAPHY	 Scott Pilgrim VS The World<br>
2001 	ART DIRECTION	         Donnie Darko<br>
1999 	WRITING	                 Big daddy<br>
2011 	WRITING	                Just Go with It<br>
2008	WRITING	                 You Don't Mess with the Zohan<br>
2014	CINEMATOGRAPHY	  Maze Runner: Run or Die<br>
2012	ART DIRECTION	          The Hunger Games<br>

<h5>código para inserir:</h5>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10396','2010','2010','82','CINEMATOGRAPHY','Bill Pope','Scott Pilgrim VS The World','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10397','2001','2001','73','ART DIRECTION','Alec Hammond','Donnie Darko','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10398','1999','1999','71','WRITING','Steve Franks, Tim Herlihy and Adam Sandler','Big daddy','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10399','2011','2011','83','WRITING','Allan Loeb and Timothy Dowling','Just Go with It','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10400','2008','2008','80','WRITING','Adam Sandler, Roberto Smigel and Judd Apatow','You Dont Mess with the Zohan','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10401','2014','2014','86','CINEMATOGRAPHY','Enrique Chediak','Maze Runner: Run or Die','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10402','2012','2012','84','ART DIRECTION','John Collins, Paul Richards and Robert Fechtman','The Hunger Games','1'); </code>

 <code>SELECT * FROM `oscar` WHERE 1 ORDER BY `oscar`.`id` DESC; </code>
##
<h4>15. Crie uma nova categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.</h4>

<h5>O codigo está abaixo, porem para melhor visualização dos filmes, ano e categorias escolhidas são: <h5>
2010 	GABRIEL GOSTA          Scott Pilgrim VS The World<br>
2001 	GABRIEL GOSTA          Donnie Darko<br>
1999 	GABRIEL GOSTA          Big daddy<br>
2011 	GABRIEL GOSTA	        Just Go with It<br>
2008	GABRIEL GOSTA          You Don't Mess with the Zohan<br>
2014	GABRIEL GOSTA          Maze Runner: Run or Die<br>
2012	GABRIEL GOSTA          The Hunger Games<br>

<h5> código para inserir:</h5>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10403','2010','2010','82','GABRIEL GOSTA','Gabriel Augusto','Scott Pilgrim VS The World','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10404','2001','2001','73','GABRIEL GOSTA','Gabriel Augusto','Donnie Darko','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10405','1999','1999','71','GABRIEL GOSTA','Gabriel Augusto','Big daddy','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10406','2011','2011','83','GABRIEL GOSTA','Gabriel Augusto','Just Go with It','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10407','2008','2008','80','GABRIEL GOSTA','Gabriel Augusto','You Dont Mess with the Zohan','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10408','2014','2014','86','GABRIEL GOSTA','Gabriel Augusto','Maze Runner: Run or Die','1'); </code>

 <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10409','2012','2012','84','GABRIEL GOSTA','Gabriel Augusto','The Hunger Games','1'); </code>

 <code>SELECT * FROM `oscar` WHERE 1 ORDER BY `oscar`.`id` DESC; </code>
##
<h4>16. Qual foi o primeiro ano a ter um prêmio do Oscar?</h4>

O primeiro ano a ter um prêmio do Oscar foi em 1928.

<code>SELECT * FROM `oscar` ORDER BY `oscar`.`year_ceremony` ASC; </code>
##
<h4>17. Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?</h4>

No ano em que eu nasci: a Melhor Atriz foi Hilary Swank, o melhor filme foi American Beauty e o Melhor Diretor foi Sam Mendes.

<code> SELECT * FROM `oscar` WHERE `year_ceremony` = '2000' AND `winner`= '1' ORDER BY `oscar`.`category` ASC; </code>
##
<h4>18. Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o Oscar. Só foram nomeados.</h4>

<h5>O codigo está abaixo, porem para melhor visualização dos filmes, ano e categorias escolhidas são: </h5>
2018    Nicole Kidman                    Aquaman<br>
2018    Lana Condor                      To All the Boys Ive Loved Before<br>
2015    Margot Robbie                    Birds of Prey<br>
2017    Ruby Rose                        John Wick: Chapter 2<br>
2013    Charlotte Gainsbourg             Nymphomaniac<br>
2015    Mia Wasikowska                   Crimson Peak<br>
2009    Toni Collette                    Mary and Max<br>

<h5>código utilizado para inserir:</h5>

<code> INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10410','2018','2019','91','ACTRESS IN A SUPPORTING ROLE','Nicole Kidman','Aquaman','0'); </code>

<code> INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10411','2018','2019','91','ACTRESS IN A LEADING ROLE','Lana Condor','To All the Boys Ive Loved Before','0'); </code>

<code> INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10412','2015','2016','88','ACTRESS IN A SUPPORTING ROLE','Margot Robbie','Birds of Prey','0'); </code>

<code> INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10413','2017','2018','90','ACTRESS IN A SUPPORTING ROLE','Ruby Rose','John Wick: Chapter 2','0'); </code>

<code> INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10414','2013','2014','86','ACTRESS IN A LEADING ROLE','Charlotte Gainsbourg','Nymphomaniac','0'); </code>

<code> INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10415','2015','2016','88','ACTRESS IN A LEADING ROLE','Mia Wasikowska','Crimson Peak','0'); </code>

<code> INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('10416','2009','2010','82','ACTRESS IN A LEADING ROLE','Toni Collette','Mary and Max','0'); </code>
##
<h4>19. [OPCIONAL] - Utilizando o comando 'Alter Table', troque os tipos dos dados da coluna/campo "Winner" para Bit.</h4>

<code> ALTER TABLE oscar MODIFY COLUMN winner bit, </code>

