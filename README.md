É inegavel a importância de um Banco de Dados (Data Base) para armazenar e manter dados de clientes, serviços, produtos e operações. Atualmente, há diversas linguagens de banco de dados, algumas mais simples, outras mais complexas. A mais utilizada no mundo até o momento é a SQL (Structured Query Language). Mas antes de falar da SQL, vamos conhecer alguns conceitos.

> QUER IR DIRETO AO PONTO? NAVEGUE PELAS SEÇÕES:
<a id="teste"></a>
- SGBD


![Banco de Dados](https://becode.com.br/wp-content/uploads/2018/07/teste-bd-1152x605.png)
*Fonte imagem: Becode*

# DATABASE - CONCEITOS
O banco de dados pode ser descrito como armazenamento e organização de informações de algum domínio em questão. É onde os dados de um site, sistema, servidor, etc, ficam contidos com recursos de segurança, permitindo conferência futura, ou até mesmo alteração e exclusão.

Um site para ficar disponível na web, necessita de um banco de dados para armazenar dados dos seus clientes, caso eles interajam com o sistema. Um sistema de PDV, por exemplo, também precisa de um banco de dados para dar baixa nos estoques, contabilizar as compras, etc.

Os bancos de dados podem ser de diversos tipos:
- **Relacionais**: os dados são armazenados em tabelas e permitem a relação de uma tabela com outra. São mais estruturais e tendem a não ser tão flexíveis;
- **Distribuidos**: como o nome indica, são DBs, que estão espalhados, não armazenando dados apenas em um local;
- **Orientado a Objetos**: guardam seus dados em formato de objetos (seguindo o padrão OOP), não em tabelas;
- **NoSQL**: armazenam dados que não precisam de relacionamento entre si, mas possibilitam essa comunicação. Também são altamente flexíveis para a inserção de novos dados, que não existiam anteriormente.

Há diversos outros modelos também, como os datawarehouses, os OLTP, etc.

### SGBD [Topo](#teste)
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

# O QUE É SQL







# SQL_Intro

- Falar sobre o que é banco de dados e a importância
- Abordar o que é sgbd
- Falar sobre a diferença entre db relacional e não relacional (nosql)
- Primeiros módulos
- tentar ser coeso e objetio nas explicações.
