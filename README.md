# Vendas da AtliQ Hardware 
### Projeto de Análise Exploratória com linguagem SQL

Neste projeto analítico, viso apresentar em detalhes uma análise exploratória de dados executada com linguagem SQL sob o conjunto de dados relativo às vendas da empresa AtliQ Hardware, que é uma empresa indiana que oferta vários produtos para computador (dispositivos periféricos), tal como mouses, teclados e digitalizadores.

![](./images/images.jpg)

O objetivo desta análise exploratória é extrair o máximo de informações valiosas atinentes aos negócios e às vendas da empresa, além de especificamente obter informações estatísticas sobre a tendência de vendas da empresa ao decorrer dos anos, para podermos saber se à demanda pelos produtos da empresa estão em crescimento ou em queda.

5 tabelas estão disponíveis para a análise neste conjunto de dados:

* customers: Informações sobre os clientes da empresa
* date: Informações dos anos, meses e datas sobre às vendas da empresa
* markets: Informações relativa às cidades da Índia em que tal empresa é localizada
* products: Informações sobre os produtos que a empresa comercializa
* transactions: Informações sobre às vendas realizadas e registradas pela empresa

As 5 tabelas são relacionadas representativamente através do modelo de estrela abaixo:

![](./images/modelo_tabelas.png)

O modelo de estrela (star-schema) explicita acima que às 4 tabelas (customers, date, markets, products) são tabelas-dimensão que estão relacionadas diretamente com a tabela transactions que é a tabela-fato, a tabela-fato é caracterizada por ter vários eventos registrados historicamente durante determinado período de tempo, enquanto a tabela-dimensão é caracterizada por conter várias informações complementares aos eventos registrados.

Em suma, a tabela transactions é a tabela-fato por conter todos os registros de todas às vendas realizadas pela empresa durante vários anos, enquanto às de mais tabelas-dimensões são responsáveis por conter informações adicionais que complementam às informações relativa às vendas da empresa.

Concluída a explicação acima sobre a relação entre às tabelas, irei iniciar o processo de análise:

#### Exploração dos dados:

Antes de começar às análises sobre os negócios da empresa, decidi saber de antemão a quantidade de linhas contidas em cada tabela que será analisada:

```
# Quantidade de linhas na tabela customers:

SELECT COUNT(*) AS 'qtd_rows' FROM customers;
```
38 linhas na tabela 'customers'

```
# Quantidade de linhas na tabela date:

SELECT COUNT(*) AS 'qtd_rows' FROM date;
```
1.126 linhas na tabela 'date'

```
# Quantidade de linhas na tabela markets:

SELECT COUNT(*) AS 'qtd_rows' FROM markets;
```
17 linhas na tabela 'markets'

```
# Quantidade de linhas na tabela products:

SELECT COUNT(*) AS 'qtd_rows' FROM products;
```
279 linhas na tabela 'products'

```
# Quantidade de linhas na tabela transactions:

SELECT COUNT(*) AS 'qtd_rows' FROM transactions;
```
148.395 linhas na tabela 'transactions'

Normalmente, a tabela-fato contêm mais linhas do que a tabela-dimensão, nesse caso, por exemplo, a tabela-fato transactions contêm 148 mil linhas, enquanto às de mais tabelas-dimensões contêm pouquíssimas linhas armazenadas.





