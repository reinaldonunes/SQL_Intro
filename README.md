<a id="topo"></a>

É inegavel a importância de um Banco de Dados (Data Base) para armazenar e manter dados de clientes, serviços, produtos e operações. Atualmente, há diversas linguagens de banco de dados, algumas mais simples, outras mais complexas. A mais utilizada no mundo até o momento é a SQL (Structured Query Language). Mas antes de falar da SQL, vamos conhecer alguns conceitos.

> **QUER IR DIRETO AO PONTO? NAVEGUE PELAS SEÇÕES:**
> - *[DataBase - Conceitos](#idcap1)*
> - *[O que é SQL](#idcap2)*
> - *[CREATE, ALTER, DROP - criando, alterando e removendo bancos e tabelas ](#idcap3)*
> - *[SELECT, INSERT, UPDATE, DELETE - solicitando, inserindo, alterando e apagando dados](#idcap4)*
> - *[TIPANDO CAMPOS](#idcap5)*
> - *[SQL LITE & DRAWSQL](#idcap6)*


![Banco de Dados](https://becode.com.br/wp-content/uploads/2018/07/teste-bd-1152x605.png)
*Fonte imagem: Becode*

<a id="idcap1"></a>

# DATABASE - CONCEITOS
O banco de dados pode ser descrito como armazenamento e organização de informações de algum domínio em questão. É onde os dados de um site, sistema, servidor, etc, ficam contidos com recursos de segurança, permitindo conferência futura, ou até mesmo alteração e exclusão.

Um site para ficar disponível na web, necessita de um banco de dados para armazenar dados dos seus clientes, caso eles interajam com o sistema. Um sistema de PDV, por exemplo, também precisa de um banco de dados para dar baixa nos estoques, contabilizar as compras, etc.

Os bancos de dados podem ser de diversos tipos:
- **Relacionais**: os dados são armazenados em tabelas e permitem a relação de uma tabela com outra. São mais estruturais e tendem a não ser tão flexíveis;
- **Distribuidos**: como o nome indica, são DBs, que estão espalhados, não armazenando dados apenas em um local;
- **Orientado a Objetos**: guardam seus dados em formato de objetos (seguindo o padrão OOP), não em tabelas;
- **NoSQL**: armazenam dados que não precisam de relacionamento entre si, mas possibilitam essa comunicação. Também são altamente flexíveis para a inserção de novos dados, que não existiam anteriormente.

Há diversos outros modelos também, como os datawarehouses, os OLTP, etc.

### SGBD
Para um melhor controle e administração dos dados, existem os DataBase Managment System, ou Sistemas de Gerenciamento de Banco de Dados (SGBDs). São compostos por diversos softwares que permite a administração, consulta, alteração e exclusão de dados contidos nos bancos.

Algums dos SGBDs mais conhecidos atualmente são:
- mySQL;
- PostgreSQL
- Oracle SQL
- SQL Server
- MongoDB (noSQL)
- Redis (noSQL)
- Cassandra (noSQL)

![SGBDs Disponíveis no Mercado](https://miro.medium.com/max/2400/1*h0ccJ-A0qaNQDflqKDsyzA.png)
*Fonte imagem: Miro Medium*

### RELACIONAL E NÃO RELACIONAL (NOSQL)
Um banco de dados relacional geralmente armazena seus dados em tabela. Cada tabela pode armazenar dados de forma independente, mas podem se relacionar com outras para complementar seus dados. Imagine uma lista de produtos. Eles terão nome, peso, dimensão, etc... mas podem ter outras informações provenientes de outras tabelas, como categoria e marca, que por ventura, estarão em outras tabelas. Dessa forma, a relação entre as tabelas de dados pode ser facilitada e permitindo uma melhor comunicação entre eles na hora de se realizar um filtro, por exemplo. 

Já a NoSQL (que quer dizer Not Only SQL, ou Não apenas SQL) é uma linguagem mais flexível e que não armazena dados do modo tradicional da SQL. A NoSQL poderá armazenar dados nos mais diversos tipos, como documetos JSON, Grafos, Colunas, Chave-Valor, etc.

Isso permite uma escabilidade maior e maior velocidade de consultas entre os dados.

Entretanto, é preciso ter em mente que a NoSQL não veio pra substituir ou derrubar a SQL. Há projetos e momentos específicos para se usar um ou outro

Por exemplo, se você vai fazer um site ou um sistema pequeno de gerencialmento, que sofre pouca alteração estrutural, um database em SQL poderá ser mais indicado. Agora, se o seu banco sofrerá constantes mudanças (por exemplo, a implementação de um campo novo ou uma nova estrutura), databases em NoSQL serão mais indicados.

![Relacional vs Não Relacional](https://miro.medium.com/max/1200/0*LR8ZkHpzwTAZjBtI.png)
*Fonte imagem: Miro Medium*

<a id="idcap2"></a>

# O QUE É SQL
SQL quer dizer "Structured Query Language" ou "Linguagem de Consulta Estruturada". Foi criado para simplificar a administração e alteração de dados de um sistema, permitindo que vários programadores a utilizassem ao mesmo tempo.

A linguagem surgiu em meados dos anos 70 dentro da IBM em São José, Califórnia. A primeira versão comercial da SQL foi disponibilzida no mesmo período e se tornou um sucesso, fazendo então com que a ANSI (American National Standart Institute) desenolvesse logo uma padronização de sua implementação e programação. Atualmente, a SQL é uma das mais utilizadas linguagens de banco de dados, dada a sua facilitade e versatilidade.

A SQL possui subconjuntos, que são:
- **DML (Data Manipulation Language)**: são os comandos da SQL utilizada para solicitar, inserir e apagar dados da tabela;
- **DDL (Data Definition Language)**: são os comandos utilizados para definir novas tabelas ou apagar antigas;
- **DCL (Data Control Language)** - são os comandos utilizados para controlar os aspectos de segurança e permissões das tabelas;
- **DTL (Data Transition Language)** - são os comandos utilizados para determinar as transações entre uma tabela e outra.

A seguir, vamos ver na prática os comandos da linguagem para criar, consultar, inserir, alterar e deletar tabelas.

<a id="idcap3"></a>

# CRIANDO, ALTERANDO E APAGANDO DB E TABLES
Primeiro de tudo, temos de criar um banco de dados para trabalharmos. Para isso, a SQL utiliza a sintaxe `CREATE DATABASE nomedb;`.

Dentro desse banco criado, poderemos então criar e adicionar nossas tabelas de dados.

Para remover um banco, utilizamos `DROP DATABASE nomedb;`.

Obs: somente execute este comando quando já tiver feito backup dos dados ou tiver certeza que não serão uteis para mais nada. Essa ação é irreversível e pode comprometer a integridade do seu banco.

Após criar o banco, se você utiliza um gerenciador visual, basta selecionar o banco para executar outros comandos. Se quiser selecionar ela por SQL, utilize `USE nomedb;`. Desta forma, a SQL vai selecionar a tabela criada anteriormente, permitindo que você trabalhe diretamente com ela (e não com outra aleatória).

##

Após criar um banco de dados, precisamos definir as tabelas que armazenarão os dados. Para isso, utilizamos:
```
CREATE TABLE nometabela(
    campo1 INT(9);
    campo2 VARCHAR(100);
    campo3 TEXT();
)
```
Para deletar a tabela, utilizamos `DROP TABLE nometabela;`.
**Obs:** sobre tipagens dos campos, *[veja aqui](#idcap5)*

Para alterar a tabela do banco, adicionado mais um campo, por exemplo, utilizamos o comando `ALTER TABLE` e após isso espeficando o que adicionar:
```
ALTER TABLE nometablea ADD COLUMN campo4 VARCHAR(250);
```
Ou apagando um campo, com:
```
ALTER TABLE nometabela DROP COLUMN campo4;
```

<a id="idcap4"></a>

# INSERINDO, BUSCANDO E ATUALIZANDO NA TABLE
Para inserir dados em uma tabela, executamos o comando `INSERT INTO` acompanhado dos campos e seus respectivos valores.
```
INSERT INTO nometabela(campo1,campo2,campo3,...)
VALUES
('Valor Campo 1','Valor Campo 2','Valor Campo 3,...)
```

##

Para verificar se os dados estão de fato na tabela, ou realizar uma consulta para o sistema, utilizamos o comando `SELECT`, que é acompanhado de vários atributos. Vejamos:
```
SELECT idcampo, nomecampo FROM nometabela
```
Neste código, solicitamos que apenas os campos informados sejam buscados dentro da tabela em questão.

```
SELECT idcampo, nomecampo FROM nometabela WHERE idcampo = 1
```
Neste exemplo, só vamos mostrar os resultados que corresponderem a cláusula *WHERE*, ou seja, *quando o campo for*.

```
SELECT * FROM nometabela WHERE idcampo = 1 ORDER BY campo
```
Ao utilizarmos o coringa * estamos dizendo *todos os campos*. *ORDER BY* quer dizer *ordenado por*. Também podemos dizer se o resultado será ascendente (ASC) ou descendente (DES), assim: `ORDER BY campo ASC` ou `ORDER BY campo DESC`

```
SELECT * FROM nometabela WHERE idcampo = 1 ORDER BY campo ASC LIMIT 0,5
```
No exemplo acima, para finalizar, utilizamos o comando extra `LIMIT` informando o mínimo e máximo de resultados que a busca poderá trazer por vez.

##

Para atualizar dados na tabela, utilizamos o comando `UPDATE` e `SET`. Assim, podemos montar a query:
```
UPDATE nome_tabela SET campo = "novo_valor" WHERE condição
```

##

Por fim, para remover dados da tabela, utilizamos o comando `DELETE`, ficando então o código `DELETE FROM nome_tabela WHERE condição`.

<a id="idcap5"></a>

# TIPAGEM E ATRIBUTOS DOS CAMPOS
Ao criar uma tabela e informar os campos, devemos tipar eles para comportar os dados. Alguns tipos são *INT, CHAR, VARCHAR, DOUBLE, TEXT, DATE*, etc. Veja alguns exemplos de como declarar o tipo do campo:
- `campo1 INT(9);` para indicar que o campo é do tipo inteiro e armazenará até 9 dígitos;
- `campo1 VARCHAR(100);` para indicar que o campo será do tipo String, armazenando até 100 caracteres;
- `campo1 TEXT();` para indicar que o campo será do tipo String, mas sem limite de caracteres;
- `campo DOUBLE()` para indicar um campo que vai armazenar números flutuantes (que tem casas decimais);

Além da tipagem, alguns campos também podem receber propriedades extras para dar mais poder a tabela:
- `campo1 INT(9) NOT NULL` *NOT NULL* para indicar que o campo não pode ficar vazio;
- `campo1 INT(9) PRIMARY KEY` *PRIMARY KEY* para indicar que campo será usado como índice para relação com outras tabelas;
- `campo1 INT(9) FOREIGN KEY` *FOREING KEY* para indicar que campo será usado para receber o índice de outra tabela;
- `campo1 INT(9) AUTO INCREMENT;` *AUTO INCREMENT* para indicar que o valor do campo será atualizado automaticamente em cada registro.

Abaixo um exemplo completo da aplicação dos tipos e atributos:
```
CREATE TABLE nometabela(
    campo1 INT(9) NOT NULL PRIMARY KEY AUTO INCREMENT;
    campo2 VARCHAR(100) NULL;
    campo3 TEXT() NULL;
    campo4 INT(9) NO NULL FOREIGN KEY;
    ...
)
```

<a id="idcap6"></a>

# MODELAGEM DE BANCO DE DADOS E TESTANDO NA PRÁTICA
Antes de mais nada, para se criar um sistema que precisará de um banco de dados, é necessário fazer um projeto de sistema, com os DER (diagrama entidade-relacionamento) que conduzirá o programador a fazer a modelagem completa do banco. Isso facilitará a manutenção futura e também reduzirá problemas corriqueiros com o banco.

Para realizar a modelagem do banco de dados em SQL, pode-se utilizar várias ferramentas, como *MySQL Workbench*, *Astah Professional* e o *DrawSQL*. No caso do DrawSQL, é possível fazer a modelagem do banco diretamente online, através [deste link](https://drawsql.app/).

![Site do DrawSQL](https://drawsql.app/img/drawsql-screenshot-2.png)
*Fonte imagem: DrawSQL*

Para testar e aplicar os comandos SQL, é possível utilizar o **SQL LITE ONLINE**, sendo acessível [aqui](https://sqliteonline.com/).

![Site do SQLlite](https://terminalroot.com.br/assets/img/mysql/sqliteonline.png)
*Fonte imagem: Terminal Root*


#
*Obs: esse conteúdo serve de introdução ao SQL. Diversas ferramentas e opções avançadas não foram aqui apresentadas, como o LEFT JOIN, INNER JOIN, RIGHT JOIN, entre outros.*

##
Você chegou ao fim deste artigo. Para voltar ao início, *[clique aqui](#topo)*