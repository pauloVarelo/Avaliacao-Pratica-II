# Prova – Aplicação CRUD de Alunos com Flask & SQLite

## Objetivo  
Desenvolver uma aplicação web simples usando Flask e SQLite que permita cadastrar e listar alunos.  
O foco é utilizar rotas, templates e interação com banco de dados em Python.

## Descrição da tarefa  
Você deverá criar uma aplicação com as seguintes características:

- Um arquivo de esquema de banco de dados `schema.sql` que contém o comando para criação da tabela de alunos.  
- Um arquivo `app.py` que implementa a aplicação Flask, permitindo ao usuário visualizar a lista de alunos e cadastrar novos.  
- Dois templates HTML: um para a listagem dos alunos (`index.html`) e outro para o formulário de cadastro (`cadastro.html`).  
- Persistência dos dados em SQLite (o arquivo do banco pode ter nome à sua escolha).

## Requisitos obrigatórios  

1. No arquivo `schema.sql`, inclua **exatamente** o seguinte comando:

   ```sql
   CREATE TABLE IF NOT EXISTS aluno (
       id INTEGER PRIMARY KEY AUTOINCREMENT,
       nome TEXT NOT NULL,
       idade INTEGER NOT NULL,
       curso TEXT NOT NULL
   );
A aplicação deve ter duas rotas principais:

/ (GET) – exibe uma tabela com todos os alunos cadastrados, mostrando ID, Nome, Idade e Curso.

/cadastro (GET + POST) – exibe o formulário para cadastrar um novo aluno (nome, idade, curso). No método POST, insere o novo aluno no banco e redireciona para /.

No app.py:

Conecte ao banco com sqlite3.connect(...).

Use conn.row_factory = sqlite3.Row para facilitar o acesso aos campos por nome.

Crie uma função (por exemplo start_db()) que seja executada quando a aplicação for iniciada, de modo a garantir que a tabela aluno exista (usando schema.sql).

Garanta que essa função seja chamada no bloco if __name__ == '__main__': ou equivalente ao iniciar a aplicação.

Nos templates:

index.html: exibir todos os registros da tabela aluno em uma tabela HTML.

cadastro.html: apresentar um formulário com campos nome, idade, curso e um botão “Cadastrar”.

Boas práticas: feche a conexão com o banco de dados após cada operação (conn.close()).

Critérios de avaliação
Critério	Peso
Schema correto conforme especificado	20%
Funcionalidade de listagem implementada	30%
Funcionalidade de cadastro implementada	30%
Organização e clareza do código	10%
Uso adequado de templates e separação	5%
Boas práticas (fechar conexões, commit)	5%

Instruções para entrega
Empacotar (zip, tar ou outro método) todos os arquivos da aplicação:

app.py

schema.sql

Diretório templates/ contendo index.html e cadastro.html

(Opcional) Diretório static/ com style.css se desejar estilizar as páginas

No cabeçalho do arquivo/zip, inclua: seu nome, turma e data de entrega.

No código, adicione comentários explicando as partes principais (rotas, conexão ao banco, renderização de templates).

Entregar o pacote até a data/hora determinada pelo(a) professor(a).

Observações
Não é obrigatório implementar funcionalidades de edição (UPDATE) ou exclusão (DELETE) de alunos. Quem implementar terá ponto extra.

A estilização (CSS) é opcional e não interfere diretamente na nota, mas melhora a apresentação.

Certifique-se de que a aplicação execute sem erros no ambiente local com Python 3.x.
