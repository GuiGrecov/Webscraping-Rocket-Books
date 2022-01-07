# Webscraping-Rocket-Books
![image](https://user-images.githubusercontent.com/94385953/148600028-3d136531-5527-41d7-bb27-7907c9426348.png)
**AVISO:** O CEO citado no problema de negócios não existe. Esse webscraping foi feito para fins de estudos e demonstração de habilidades/competências não me responsabilizo para o uso indefido desse código de Webscraping.

# 1. Sobre a Rocket Books
A Rocket Books é uma livraria e gostaria de saber o que seu concorrente direto está fazendo: a Books.toScrape. Com isso, ela contratou um time de DS para fazer essa análise e esse Webscraping para ela. 

# 2. Problema de Negócio 
O CEO da livraria ROCKET BOOKS precia saber o que seu concorrente está fazendo. No caso, a Rocket Books vende 3 gêneros de livros Classics, Science Fiction e Business. O CEO gostaria de um dataseet com o que o concorrente está vendendo sobre esses 3 gêneros. Mais uma lista com o preço para um comparativo, e se está ou não disponível no estoque.

# 3. Questão de Negócio 
Coletar os seguintes dados do site: https://books.toscrape.com/index.html
 <br>
 Cátalogo: 
  *  Classics 
  *  Science Fiction 
  *  Business 
 
 Coletar os seguintes dados de cada livro 
  *  Nome do Livro 
  *  Preço em Libras 
  *  Disponível em estoque 
  *  Rating - traduzir para número
  
# 4. Resultados 
![image](https://user-images.githubusercontent.com/94385953/148601001-77d1bc33-7cc1-4cce-ac23-36edbbb2a93d.png)
<br>
Conseguimos gerar uma tabela final com todos os pedidos do CEO, analisando o rating se há em stock e o nome dos livros, seguindo as premissas comentadas pelo CEO. 

# 5. Arquitetura de Webscraping 
Abaixo nós temos o diagrama que exemplifica a arquiterua de como está configurado esse webscraping: <br>
![image](https://user-images.githubusercontent.com/94385953/148602279-6d7a6cfb-daf7-4e39-94fb-aa5dc7cc7956.png)
<br> 
* **JOB 1**: Acessar as informações da Vitrine dos livros **Clássicos** e começar a varredura para ocorrer o Webscraping 
* **JOB 2**: Acessar as informações da Vitrine dos livros **Negócios** e começar a varredura para ocorrer o Webscraping
* **JOB 3**: Acessar as informações da Vitrine dos livros **Ficção Científica** e começar a varredura para ocorrer o Webscraping
* **JOB 4**: Etapa responsável por juntar os JOB's: 1,2 e 3. Juntando tudo isso em uma tabela com todas as informações de livros separando por gênero e nome. 
* **JOB 5**: Após ocorrer o Webscraping os dados ficam desorganizados, nessa parte temos que organizá-los e fazer a limpeza dos dados com funções chamadas como REGEX. Exemplo, transformar o Rating Two em 2. 
* **JOB 6**: Todas as etapas anteriores resultam no plot da tabela final com todas informações mostradas anteriormente.

# 5. Hipóteses solucionadas 
* **H1.** O gênero com maior preço médio tem melhores avaliações. 
**FALSA**  O genêro com o maior preço não tem as melhores avaliações. <br>
![image](https://user-images.githubusercontent.com/94385953/148602601-c3fbbc78-1c8a-4214-a3e5-9a3f3d286a44.png)
<br> Como conseguimos observar no gráfico acima gênero com os livros mais caros são pertencentes ao gênero: "Classic". 

<br> ![image](https://user-images.githubusercontent.com/94385953/148602940-911ddc5c-6cdc-4810-822f-a97765533aab.png)
<br>Como vemos na imagem acima o gênero com melhor avaliação média é pertencente a Business. Ou seja, não necessariamente os melhores gêneros/livros são os livros mais caros. 

* **H2.** Gênero de Negócios tem o melhor rating de todos os gêneros 
**VERDADEIRO** O Gênero de Negócios tem as melhores avaliações<br>
![image](https://user-images.githubusercontent.com/94385953/148603164-05be5a66-2714-454b-83c5-2311280142dc.png)
