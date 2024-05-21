# Desafio Dio - Limpeza e Transformação de Dados 👩‍💻

## Dificuldades encontradas no desafio ⚠️
Tive dificuldades em conectar o MySQL workbench a Azure por conta do arquivo SSL, pois o curso já é um pouco antigo e ouve algumas modificações, precisei encontrar o arquivo em um outro campo diferente do que foi mostrado no tutorial com a Juliana.<br>
Ouve algumas instruções SQL que não foram executadas por erros como: <br>

“alter table dept_locations drop fk_dept_locations;” <br>
“alter table dept_locations 
	add constraint fk_dept_locations foreign key (Dnumber) references departament(Dnumber)
	on delete cascade
    on update cascade;” 

Não consegui identificar o erro pois sou leiga, então simplesmente ignorei e segui com as demais instruções. <br>
Durante o processo de inserir os dados deu erro no primeiro comando, fui no fórum e graças a Deus uma pobre alma bondosa havia colocado a solução, então consegui solucionar e executar a instrução e acabou o processo de inserção dos dados. Porém mesmo assim algumas instruções de select não funcionaram, acredito que a base de dados tenha ficado um pouco comprometida, mas continuei o desafio. <br>
Após terminar de inserir os dados, fiz a conexão do PowerBI para o bando de dados MySQL onde selecionei todas as tabelas, sem exceções, então me direcionei para o processo de transformação de dados. <br>
Tive dificuldade em entender do que se tratavam algumas colunas por causa do nome, algumas renomeei para algo mais fácil, outras realmente não consegui fazer ideia do que se tratava. <br>
Eu quase desisto de continuar o bootcamp depois desse desafio, não consegui fazer muitas coisas que foram pedidas pro causa dos erros nas instruções SQL que foram usadas pra modelar a adicionar as informações no banco de dados.

## Lista das tabelas importadas do banco de dados para o Power Query 💾
* azure_company employee
* azure_company departament
* azure_company dependent
* azure_company works_on
* azure_company dept_locations
* azure_company project

 ## Lista de tabelas com descrições de modificações realizadas
## azure_company employee
1 – Alteração do nome da coluna “Fname” para “Primeiro nome”<br>
2 – Alteração do nome da coluna “Lname” para “Último nome”<br>
3 – Alteração do nome da coluna “Address” para “Endereço”<br>
4 – Alteração do nome da coluna “Sex” para “Sexo”<br>
5 – Alteração do nome da coluna “Salary” para “Salário”<br>
6 – Alteração do tipo de dado da coluna “Salário” de decimal para decimal fixo<br>
7 – Divisão da coluna endereço, dividida em duas colunas, primeiro separei o número do restante do endereço. Usei a opção dividir coluna por delimitador “-“ da extremidade esquerda. <br>
8 – Renomeei a coluna com os números para “Número”<br>
9 – Selecionei o restante do endereço e separei novamente em duas colunas, mas dessa vez para separar o “TX” do restante do endereço. Usei a opção delimitador “-“ da extremidade direita.<br>
10 – Renomeei a coluna que ficou com as informações de “TX” para “Estado”.<br>
11 – Peguei a coluna que sobrou e dividi em duas colunas novamente, dessa vez para separar a cidade do logradouro. Usei a opção delimitador “-“ da extremidade a direita.<br>
12 – Renomeei a coluna com as informações das cidades para “Cidade”<br>
13 – Alterei o nome da coluna restante com aparentemente o nome da rua e alterei para “Logradouro”<br>
14 -  Na tabela Logradouro, fiz a substituição do conteúdo de “Fire-Oak” para “Fire Oak”, visto que o nome é de apenas uma rua.<br>
15 – Adicionei uma coluna com o nome do país para completar o endereço.<br>
16 - 3 – Fiz a exclusão da coluna “Minit” (não sei exatamente o que era, talvez a inicial do nome do meio, a informação estava confusa).<br>
17 – Personalizei uma coluna fazendo a junção do primeiro com o último nome do coloborador, dei o nome da coluna para “Colaborador”. E apaguei as colunas que estavam com os nomes separados.<br>
18 – Para realizar a seguinte parte: “Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. <br>
OBS: Fique atento, essa informação influencia no tipo de junção. Nesse processo alimine as colunas desnecessárias.”<br>
Utilizei o combinar mescla para nova consulta fazendo a comparação do número do departamento presentes nas duas tabelas. A partir daí foi criada a tabela “Departamentos com colaboradores” e fiz as devidas alterações para ficar apenas o nome dos departamentos associados aos colaboradores.<br>

azure_company departament<br>
1 – Alteração do nome da coluna “Dname” para “Nome do departamento”<br>
2 – Alteração do nome da coluna “Dnumber” para “Número do departamento”<br>

azure_company dependent<br>
1 – Alteração do nome da coluna “Relationship” para “Parentesco”<br>

azure_company works_on<br>
1 – Alteração do nome da coluna “Hours” para “Horas”<br>

azure_company project<br>
1 – Alteração do nome da coluna “Pname” para “Nome do produto”<br>
2 - Alteração do nome da coluna “Pnumber” para “Número do produto”<br>
3 - Alteração do nome da coluna “Plocation” para “Local do produto”<br>
4 - Alteração do nome da coluna “Pnum” para “Quantidade de produtos”<br>

#Problemas⚠️
Não consegui realizar a junção de colaborador por gerente porque não condiz com os dados que estão no exemplo dela. Acredito que o erro tenha sido no código que foi disponibilizado no GitHub, pois existem muitas inconsistências ali.<br>

Diferença de mesclar consultas para combinar:<br>
Mesclar Consultas é utilizado para combinar duas ou mais tabelas com base em uma ou mais colunas correspondentes (chaves). Esse processo é semelhante a um "join" em SQL.<br>
Já a combinação de consultas é usado para anexar os dados de uma tabela ao final de outra tabela. Este processo é semelhante a um "union" em SQL
Depois de eu ter feito tudo isso, começou a aparecer um monte de sinal de alerta e nada mais prestou. Mas eu estou entregando assim mesmo, como diz o professor da minha faculdade, melhor entregar do que não entregar.<br>
