# Projeto de Engenharia de Dados com PySpark, PostgreSQL e Docker

Este projeto simula um pipeline realista de ingestão e análise de dados semiestruturados (JSON), com foco em construção de competências aplicáveis no mercado de engenharia e ciência de dados.

## Cenário Simulado

Atuar como engenheiro de dados em uma empresa de e-commerce. Eventos de usuários (como visualização de produtos) são registrados em arquivos JSON. 

Objetivo:

- Armazenar esses dados no PostgreSQL.
- Usar PySpark para processar e converter os dados.
- Realizar consultas SQL diretamente sobre os objetos JSON.
- Gerar JSON personalizados por usuário.

---

## Como Executar

Este projeto foi desenvolvido em Jupyter Notebook usando Python e SQLite. Abaixo estão os passos completos para rodá-lo no seu computador.

### Pré-requisitos
Antes de tudo, você precisa ter instalado:

Python 3.9+

Git (Para clonar o projeto)

VS Code com extensão do Jupyter

### Passo 1 – Instale o VS Code (caso ainda não tenha)
Acesse: https://code.visualstudio.com/

Baixe o instalador para seu sistema operacional

Instale normalmente

### Clone o repositório:

git clone https://github.com/Alan-Couto-Projetos/Dados_json_com_postgresql cd docker
Ou baixe o projeto como .zip e extraia os arquivos.

### Configure o arquivo .env:

POSTGRES_USER=seu_usuario
POSTGRES_PASSWORD=sua_senha
DSN=postgresql://usuario:senha@host:porta/banco_de_dados

### Suba os containers:

docker-compose up --build
Acesse o Jupyter Notebook:

Abra seu navegador e vá para: http://localhost:8888

## Estrutura dos Dados

<pre> <code>[
  {
    "event_time": "2025-06-01T09:00:00Z",
    "user_id": 113,
    "session_id": "sess-007",
    "event_type": "product_view",
    "products": [
      {
        "id": 6,
        "name": "Capa de Tablet",
        "category": "Accessories",
        "price": 99.9
      }
    ],
    "device": {
      "type": "console",
      "os": "Proprietary"
    },
    "location": {
      "country": "Mexico",
      "city": "Monterrey"
    }
  },...]</code> </pre>

## Aprendizados

Ao desenvolver o pipeline para ingestão, armazenamento e análise de dados semiestruturados JSON usando PySpark e PostgreSQL, obtive uma série de aprendizados fundamentais para a prática de engenharia de dados:

<pre> <code>1. Manipulação de Dados Semiestruturados (JSON) em Bancos Relacionais
Aprendi a armazenar dados JSON em colunas do tipo TEXT ou tipos nativos do PostgreSQL (JSON / JSONB), entendendo como modelar dados complexos em bancos relacionais.

Explorei funções SQL do PostgreSQL como json_array_elements, json_build_object e operadores para acessar dados aninhados, permitindo consultas dinâmicas sobre estruturas JSON.</code> </pre>

<pre> <code>2. Processamento com PySpark e Integração com Banco de Dados
Utilizei o PySpark para carregar e transformar grandes volumes de dados JSON de forma distribuída, preparando-os para persistência.

Conectei o PySpark ao PostgreSQL via JDBC para realizar a gravação dos dados processados, garantindo eficiência e escalabilidade.

Trabalhei com RDDs e DataFrames, convertendo dados JSON em estruturas tabulares para facilitar análises.</pre> </code>

<pre> <code>3. Construção de Pipelines Reais em Ambiente Dockerizado
Configurei ambientes isolados com Docker e Docker Compose para rodar simultaneamente containers de Jupyter Notebook (com PySpark) e PostgreSQL, simulando um ambiente de produção moderno.

Garanti que o ambiente fosse reproduzível e portátil, importante para colaboração e deploy em diferentes máquinas e servidores.</code></pre>

<pre> <code>4. Consultas Analíticas e Geração de Relatórios JSON
Desenvolvi consultas para analisar o comportamento dos usuários no e-commerce, como identificar categorias mais visualizadas e sumarizar atividades por país.

Gerei resumos estruturados em JSON agregados por usuário.

Entendi a importância de unir dados semiestruturados com dados relacionais para análises mais ricas.</pre> </code>

<pre> <code>5. Boas Práticas e Fluxo de Trabalho Git
Gerenciei o versionamento do projeto no Git, aprendendo a lidar com remoção e substituição de arquivos no repositório, ignorando arquivos desnecessários e mantendo histórico limpo.</pre> </code>

Utilizei variáveis de ambiente para manter segredos fora do código, melhorando a segurança do pipeline.

## Autor
Alan Couto

Linkedin: https://www.linkedin.com/in/alan-couto-6767b0ab/
