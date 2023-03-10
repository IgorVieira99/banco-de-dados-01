# Banco de dados Resilia
## Projeto individual correspondente ao 4º módulo (banco de dados) do curso de programação da Resilia

O projeto apresenta um esquema lógico considerando três entidades e seus devidos campos.
Em tese, deveria existir uma entidade "acima" das três a serem listadas, a empresa Resilia, porém como o objetivo do projeto focava nessas três, somente estes foram considerados ao realizar o trabalho. 

**A entidade Curso apresenta os campos:** 
- id (int)primary key: o número de identificação do campo; 
- carga (int): este campo considera a carga horária total do curso; 
- área (varchar): considera a área que o curso pertence (humanas, exatas, etc); 
- uc (varchar): considera as unidades curriculares dos cursos cadastrados. 

**A entidade Turma considera os campos:** 
- id (int) primary key: o número de identificação do campo;
- sala (int): considera o número das salas de aula de cada turma; 
- professor (varchar): considera os nomes dos professores de cada turma; 
- dias varchar): considera os dias de aula de cada turma.

**A entidade Alunos considera os campos:** 
- id (int) primary key: o número de identificação do campo;
- telefone (varchar): considera o telefone de contato dos alunos;
- email (varchar): considera o email dos alunos cadastrados; 
- endereco (varchar): considera o endereço onde reside o aluno. 
______________________________________________________________________
### Cardinalidade entre as entidades:

A relação entre Curso e Turma se dá em 0, n e 0, 1, respectivamente, pois um curso pode ter muitas turmas, porém a turma pertence unicamente a este curso. 

A relação entre Turma e Alunos se dá em 0, n e 0,1, respectivamente, pois uma turma pode ter muitos alunos, porém os alunos pertencem somente a uma turma. 

______________________________________________________________________
### Códigos SQL utilizados para criação do banco de dados: 

**Para criar o banco de dados resilia:**
MariaDB [(none)]> create database resilia;


**Para acessar o banco de dados:**
MariaDB [(none)]> use resilia;


**Para criar as entidades:**
MariaDB [resilia]> create table curso (
    -> id int primary key,
    -> carga int,
    -> area varchar(20),
    -> uc varchar(50));

MariaDB [resilia]> create table turma (
    -> id int primary key,
    -> sala int,
    -> professor varchar(50),
    -> dias varchar(20),
    -> horario varchar(20));

MariaDB [resilia]> create table alunos (
    -> matricula varchar(99) primary key,
    -> telefone varchar(15),
    -> email varchar(99),
    -> endereco varchar(99));
    
**Para inserir os registros**
**Curso:** 
MariaDB [resilia]> insert into curso (id, carga, area, uc) values (01, 60, 'Front-End', 'HTML e CSS'), (02, 100, 'React', 'Javascript');

**Turma:**
MariaDB [resilia]> insert into turma (id, sala, professor, dias) values (01, 402, 'Leandro Pisco', 'Seg, Qua, Sex'), (02, 407, 'Patrícia', 'Ter e Qui'); 

**Alunos:**
MariaDB [resilia]> insert into alunos (id, telefone, email, endereco) values (01, '021970404925', 'zezinho123@gmail.com', 'Rua dos Bobos, nº 0'), (02, '02124732366', 'mariazinha456@hotmail.com', 'Rua Parnaíba, nº 141');

**Para visualizar a entidade:**
MariaDB [resilia]> show tables;

**Para descrever os campos:**
MariaDB [resilia]> describe alunos;
MariaDB [resilia]> describe curso;
MariaDB [resilia]> describe turma;
