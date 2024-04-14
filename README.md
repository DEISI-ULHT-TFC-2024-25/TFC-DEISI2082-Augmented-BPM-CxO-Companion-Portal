# Augmented BPM: A CxO Companion Portal

## Descrição

Este README descreve o processo de instalação via Docker da aplicaçãp.

## Instalação

### Clonar o Repositório

Para começar, é necessário clonar o repositório do projeto e iticializar os submodulos do back-end e front-end:

```bash
git clone https://github.com/Rocha-a21906962/CxOCP.git
cd CxOCP
git submodule update --init
```

### Back-End

Uma vez pussuindo os ficheiros agregados numa pasta (back-end & front-end), é necessário criar os "secrets".
Para tal é necessário criar um ficheiro (.env):

```bash
cd .\back-end\ 
```
Criamos o ficheiro **.env** e inicializamos o docker do back-end.

```bash
OPENAI_ORG_ID="..."
OPENAI_API_KEY="..."
JWT_SECRET_KEY="secret"
JWT_REFRESH_SECRET_KEY="refresh_secret"
COSMOS_DB_URI="..."
COSMOS_DB_KEY="..."
COSMOS_DB="CxOCP"
COSMOS_DB_CONTAINER="users"
COSMOS_DB_CONTAINER2="processes"
```
```bash
docker build -t backend-image .
docker run -d -p 5000:5000 --name backend backend-image
```

### Front-End

De seguida é necessário ir para o diretório do Front-End e inicializar o Docker.

```Bash
cd ..
cd .\front-end\
docker build -t frontend-image .
docker run -d -p 3000:3000 --name frontend frontend-image
```

Se não houver nenhum erro, deverás ter os dois dockers a correr e ligados entre si.

**NOTA.:** É necessário garantir não ter outros dockers a correr no porto 5000 e 3000.