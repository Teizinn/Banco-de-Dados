## *Avaliação Final Banco de Dados*

1) Preencha o significado das expressões abaixo, mantendo o texto ordenado:
  	- sistema gerenciador de banco de dados = Um SGBD é um software que permite aos usuários criar, modificar e 		gerenciar um banco de dados.
	
 	- restrições em banco de dados = Restrições são regras aplicadas aos dados para garantir a integridade e a 		consistência. Exemplos incluem chaves primárias, chaves estrangeiras, restrições de unicidade e regras de 		verificação.
	
 	- modelo relacional = É um modelo de dados organizado em torno de relações que consistem em tuplas e atributos. É 	amplamente utilizado em bancos de dados relacionais.
	
 	- modelagem conceitual = Envolve a criação de um modelo de dados abstrato que representa os requisitos do sistema de 	forma independente de implementação técnica.
	
 	- modelagem lógica = Traduz o modelo conceitual para um modelo de dados lógico, geralmente usando o modelo 		relacional. Aqui, as entidades, relacionamentos e atributos são mapeados para tabelas, chaves, índices, etc.

	- modelagem física = É a fase em que o modelo de dados lógico é implementado em um SGBD específico. Inclui detalhes 	como tipos de dados, índices físicos e estruturas de armazenamento.
	
 	- linguagem SQL = SQL (Structured Query Language) é uma linguagem de consulta estruturada usada para acessar e 		manipular bancos de dados relacionais.
	
 	- Data Definition Language (DDL) = Parte do SQL utilizada para definir a estrutura e o esquema do banco de dados. 	Exemplos incluem CREATE, ALTER e DROP para criar, modificar e excluir objetos como tabelas, índices, etc.
	
 	- Data Manipulation Language (DML) = Parte do SQL usada para manipular os dados dentro do banco de dados. Inclui 	comandos como INSERT, UPDATE e DELETE para adicionar, modificar e remover dados das tabelas.
	
 	- Boas práticas em modelagem de banco de dados = Incluem a normalização de dados para evitar redundâncias, uso 		adequado de chaves primárias e estrangeiras para manter integridade referencial, definição de índices para melhorar 	a performance de consultas, entre outros.

2) Por meio do MySQL Workbench OU MS Studio Managament faça o esquema de banco e responda as questões.
   	## Todos os clientes armazenados no sistema:

		SELECT * FROM cliente;

   	## Exiba os veículos que tenham final 3 no número da placa:

		SELECT * FROM veiculo WHERE placa LIKE '%3';



   	## Mostre os clientes que residem no RS e que não possuam telefone:

   		SELECT * FROM cliente WHERE uf_cnh = 'RS' AND telefone IS NULL;



   	## Exiba o código dos clientes que alugaram veículos por mais de 90 dias:

   		SELECT DISTINCT id_cliente FROM contrato_aluguel WHERE duracao > 90;


   	## Quantos veículos há cadastrados no sistema:

   		SELECT COUNT(*) AS total_veiculos FROM veiculo;


   	## Mostre o veículo alugado por Alexandre Zamberlan:

   		SELECT v.*
		FROM veiculo v
		JOIN contrato_aluguel ca ON v.id_veiculo = ca.id_veiculo
		JOIN cliente c ON ca.id_cliente = c.id_cliente
		WHERE c.nome = 'Alexandre Zamberlan';


   	## Mostre os clientes e os escritórios associados no contrato de aluguel:

   		SELECT c.nome AS nome_cliente, e.nome AS nome_escritorio
		FROM contrato_aluguel ca
		JOIN cliente c ON ca.id_cliente = c.id_cliente
		JOIN escritorio e ON ca.id_escritorio = e.id_escritorio;

