## Prática Java e JDBC: trabalhando com um banco de dados

Material de estudos práticos do Programa ONE da Oracle

### Anotações

* Tópicos:
    * Acessar o banco de dados, precisamos de um driver - biblioteca (JAR). 
    * JDBC significa Java DataBase Conectivity.
    * JDBC define uma camada de abstração entre a sua aplicação e o driver do banco de dados.
    * Método getConnection, da classe DriverManager.
    * Método getConnection recebe uma string de conexão JDBC, que define a URL, usuário, senha, etc.
    
    <br>

    * Classe ConnectionFactory e usada para simplificar e encapsular a criação da conexão.
    * Classe ConnectionFactory segue o padrão de criação Factory Method.
    * Factory Method encapsula a criação de um objeto.
    * Interface java.sql.Statement e usada para executar um comando SQL.
    
    <br>

    * Ao executar SQL como Statement, temos um risco de segurança, chamado de SQL Injection.
    * Parâmento SQL Injection.
    * Evitar SQL Injection, devemos usar a interface PreparedStatement.
    * PreparedStatement trata (sanitiza) cada parâmetro do comando SQL.
    
    <br>

    * Recurso transação, para juntar várias alterações como unidade de trabalho.
    * commit e rollback são operações clássicas de transações.
    * Fechamento dos recursos, cláusula try-with-resources, usado a interface Autoclosable.
    
    <br>

    * É boa prática usar um pool de conexões administra/controla a quantidade de conexões abertas.
    * Interface que representa a conexão (java.sql.Connection).
    * Interface que representa o pool de conexões (javax.sql.DataSource).
    * C3PO é uma implementação Java de um pool de conexão.

    <br>

    * Para cada tabela de domínio, temos uma classe de domínio.
    * Por exemplo, a tabela produtos tem uma classe Produto associada.
    * Objetos dessa classe representa um registro na tabela.
    * Data Access Object (DAO) para acessar a tabela.
    * Classe de domínio, existe um DAO, exemplo ProdutoDao.
    * Métodos JDBC relacionados com o produto devem estar encapsulados no ProdutoDao.

    <br> 

    * Que quando temos um relacionamento, é preciso ter cuidado para não cair no problema de queries N + 1.
    * N + 1 significa executar uma query e mais uma nova query (N) para cada relacionamento.
    * Queries N + 1 podem gerar um problema no desempenho.
    * Queries N + 1 podem ser evitadas através de joins no SQL.

    <br> 

    * Aplicação é escrita em camadas clássicas são view, controller, modelo e persistência.
    * Fluxo entre as camadas segue a ordem: view <--> controller <--> persistencia.
    * Camada de persistência.

    <br>

