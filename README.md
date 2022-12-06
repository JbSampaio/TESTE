# Tahech IT Service

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)


Trata-se de um sistema baseado em microsserviços, para uso do escritório, utilizando soluções tecnologicas já desenvolvidas pela equipe de TI da Tahech Advogados.
O sistema está online através do link: [Tahech | IT Service](<https://tahechitservice.herokuapp.com/>)


## 💻 Pré-requisitos

Antes de começar, verifique se você atendeu aos seguintes requisitos:
<!---Estes são apenas requisitos de exemplo. Adicionar, duplicar ou remover conforme necessário--->
* Você instalou o Git ? Caso não tenha instalado segue o link [Git 64-bit](https://github.com/git-for-windows/git/releases/download/v2.38.1.windows.1/Git-2.38.1-64-bit.exe) / [Git 32-bit](https://github.com/git-for-windows/git/releases/download/v2.38.1.windows.1/Git-2.38.1-32-bit.exe).
* Você instalou a versão 3.10.8 do Python? Caso não tenha instalado segue o link [Python 3.10.8 64-bit](https://www.python.org/ftp/python/3.10.8/python-3.10.8-amd64.exe) / [Python 3.10.8 32-bit](https://www.python.org/ftp/python/3.10.8/python-3.10.8.exe).
* Esse projeto foi desenvolvido em SO [Windows](). Ainda serão feitos testes no SO [Linux](), em breve conterá informações de como configurar em sistemas Linux.
* Você irá gerir o projeto sozinho? Caso você seja o responsável por gerir o projeto haverá a necessidade de instalar o CLI do Heroku? Caso não tenha instalado segue o link para instalação [Heroku CLI 64-bit](https://cli-assets.heroku.com/heroku-x64.exe) / [Heroku CLI 32-bit](https://cli-assets.heroku.com/heroku-x86.exe).
* Caso você não faça o gerenciamento sozinho do projeto, pode dispensar a instalação do Heroku CLI.

## 🚀 Instalando Tahech | IT Service

Para instalar o tahechitservice, siga estas etapas:

## 1. Clone o projeto em sua máquina.

```
git clone <url do repositorio>
```
## 2. Crie a virtualenv.

![Linux](https://img.shields.io/badge/Linux-E34F26?style=for-the-badge&logo=linux&logoColor=black)
```
python3 -m venv venv
source/bin/activate
```
![Windows](https://img.shields.io/badge/Windows-017AD7?style=for-the-badge&logo=windows&logoColor=white)

Será necessário uma configuração via powershell, para a sua venv ficar ativa sempre após fechar o projeto e abrir o terminal da IDE.

2.1 Abra o powershell como administrador

2.2 Execute esse comando:

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

2.3 Ao executar o comando digite 'S' ou 's' para aceitar. Em seguida feche o terminal do powershell e abra sua IDE. 

2.4 Com a IDE(VS Code ou Pycharm, recomendo a segunda IDE) aberta, abra o terminal da IDE e execute esse comando para criar sua venv:

```
python -m venv venv
```

2.5 Com a sua venv criada, execute esse comando para ativa-la:

```
.\venv\Scripts\activate
```

1.6 Após ativação da sua venv, seu terminal deverá está dessa forma:
Indicando que a sua venv está ativa. Feche o terminal e abra novamente, para assegurar que sua venv está ativa. 

```
(venv) PS C:\Users\jonat\PycharmProjects\tahechitservice>
```

2.7 Outra forma de ativar a sua venv é pela propria IDE (Pycharm), essa opção pode ser feita tanto em sistemas Linux e Windows:

2.7.1 Procure no canto inferior direito da sua IDE (Pycharm) por 'No interpreter':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f8d900722002ab3ca18.png" alt="<No interpreter>">

2.7.2 Clique em 'Interpreter Settings...':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f8f30ae430016c49644.png" alt="Interpreter Settings">

2.7.3 Clique em 'Add Interpreter > Add Local Interpreter...':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f94ebf05b000cb5757d.png" alt="Add Interpreter">

2.7.4 Verifique 'Environment', 'Location' e 'Base interpreter':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f96052c41000ce1e125.png" alt="Add Interpreter Config">

- Environment: 

```
Terá duas opções, 'Existing' ou 'New' por padrão quando não tem uma venv já criada no seu projeto a opção estará marcada com 'New', e a IDE será responsavel por criar.
```

- Location:

```
Local onde a sua 'venv' está, certifique que está ou será criada, verifique se está dentro do seu projeto. 
```

- Base interpreter:

```
É a base do seu interpretador, de qual versão do python ele será criado, certifique-se de está na versão que você instalou no seu SO e a mesma verão do projeto.
```

Após isso é só clicar em 'Ok' e deixar a IDE trabalhar e fazer a indexação do interpretador. 

## 3. Instale os pacotes requeridos.
```
pip install -r requirements-dev.txt
```

# .env

* Crie na raiz do projeto um arquivo '.env' esse arquivo será responsável pelas variáveis de ambiente do projeto.
* O mesmo deve conter as seguintes variáveis para funcionamento do projeto:

```
SECRET_KEY=
DEBUG=
ALLOWED_HOSTS=
SITE_HOST=

GOOGLE_OAUTH_CLIENT_ID=
GOOGLE_OAUTH_SECRET=

EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=
```
* Contate o [Gestor]() ou o [Desenvolvedor]() do projeto para ele lhe fornecer as keys das variáveis de ambiente.
* O arquivo '.env' não deve conter no seu repositório do github pois o mesmo leva informações sensiveis de outras conexões externas que o projeto necessita.
* Cada projeto django necessita de uma SECRET_KEY, você pode criar a sua dessa forma:
Abra o Python Console dentro da sua IDE, rode o comando:

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f7a2efb36fa0013ed37f6.png" alt="Python Console">

```
from django.core.management.utils import get_random_secret_key
```

Após importar o get_random_secret_key, rode o segundo comando: 

```
print(get_random_secret_key())
```

* Pronto, a sua SECRET_KEY será gerada na tela do console, é só copiar e colar no local de destino dentro do seu arquivo '.env'


## 4. Crie banco de dados (Por padrão ele criará um banco SQlite, já vem pré-definido nas configurações(settings.py) de todo projeto django).

```
python manage.py migrate
```

4.1 Você pode criar um banco de sua preferencia: PostgresSQL, MySQL, MongoBD, MariaDB. Fica ao seu critério, contanto que siga a recomendação da documentação do Django.
Por exemplo: Conectando o projeto com o banco [PostgreSQL](https://stackpython.medium.com/how-to-start-django-project-with-a-database-postgresql-aaa1d74659d8).

Adicione ao seu arquivo '.env' a seguinte variavel de ambiente: 

```
DATABASE_URL=
```

Após criar o seu banco, passe a seguinte url na variavel: 

```
DATABASE_URL=postgres://USER:PASSWORD@HOST:PORT/NAME
```

Exemplos de outras conexões com outros bancos: 

| Engine  | Django Backend | URL |
| ------------- | ------------- | ------------- |
| MySQL  | django.db.backends.mysql  | mysql://USER:PASSWORD@HOST:PORT/NAME  |
| Oracle  | jango.db.backends.oracle  | oracle://USER:PASSWORD@HOST:PORT/NAME  |


Após fazer a sua configuração rode o comando para migrar e criar as tabelas do projeto:

```
python manage.py migrate
```


## 5. Start o servidor

```
python manage.py runserver
```

5.1 Você pode configurar o start do servidor direto na IDE(Pycharm), da seguinte forma: 

Procure na IDE por 'Current File' e clique em 'Edit Configurations...':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f9407f9ccba000d8bbd02.png" alt="Edit Configurations">

Após abrir o 'Edit Configurations...' clique em 'Add New' e selecione 'Django Server':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f940a6cbb720018144b2c.png" alt="Edit Configurations">

Após selecionar 'Django Server' revise as configurações:

* Renomeei o nome do servidor.  
* Verifique se o Python interpreter está apontando corretamente para a sua venv.
* Verifique se 'Add content' e 'Add source' estão marcadas. 

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f956abc7372002c99c6bd.png" alt="Django Server">

Após isso é só clicar no 'Ok' e verificar se a configuração do servidor deu certo, ficando a mesma forma como no imagem, é só clicar no 'play' e esperar o servidor startar. 

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f96c86d21cd0016badb88.png" alt="Finish">


## :gear: Configurando <img src="# Tahech IT Service

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)


Trata-se de um sistema baseado em microsserviços, para uso do escritório, utilizando soluções tecnologicas já desenvolvidas pela equipe de TI da Tahech Advogados.
O sistema está online através do link: [Tahech | IT Service](<https://tahechitservice.herokuapp.com/>)


## 💻 Pré-requisitos

Antes de começar, verifique se você atendeu aos seguintes requisitos:
<!---Estes são apenas requisitos de exemplo. Adicionar, duplicar ou remover conforme necessário--->
* Você instalou o Git ? Caso não tenha instalado segue o link [Git 64-bit](https://github.com/git-for-windows/git/releases/download/v2.38.1.windows.1/Git-2.38.1-64-bit.exe) / [Git 32-bit](https://github.com/git-for-windows/git/releases/download/v2.38.1.windows.1/Git-2.38.1-32-bit.exe).
* Você instalou a versão 3.10.8 do Python? Caso não tenha instalado segue o link [Python 3.10.8 64-bit](https://www.python.org/ftp/python/3.10.8/python-3.10.8-amd64.exe) / [Python 3.10.8 32-bit](https://www.python.org/ftp/python/3.10.8/python-3.10.8.exe).
* Esse projeto foi desenvolvido em SO [Windows](). Ainda serão feitos testes no SO [Linux](), em breve conterá informações de como configurar em sistemas Linux.
* Você irá gerir o projeto sozinho? Caso você seja o responsável por gerir o projeto haverá a necessidade de instalar o CLI do Heroku? Caso não tenha instalado segue o link para instalação [Heroku CLI 64-bit](https://cli-assets.heroku.com/heroku-x64.exe) / [Heroku CLI 32-bit](https://cli-assets.heroku.com/heroku-x86.exe).
* Caso você não faça o gerenciamento sozinho do projeto, pode dispensar a instalação do Heroku CLI.

## 🚀 Instalando Tahech | IT Service

Para instalar o tahechitservice, siga estas etapas:

## 1. Clone o projeto em sua máquina.

```
git clone <url do repositorio>
```
## 2. Crie a virtualenv.

![Linux](https://img.shields.io/badge/Linux-E34F26?style=for-the-badge&logo=linux&logoColor=black)
```
python3 -m venv venv
source/bin/activate
```
![Windows](https://img.shields.io/badge/Windows-017AD7?style=for-the-badge&logo=windows&logoColor=white)

Será necessário uma configuração via powershell, para a sua venv ficar ativa sempre após fechar o projeto e abrir o terminal da IDE.

2.1 Abra o powershell como administrador

2.2 Execute esse comando:

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

2.3 Ao executar o comando digite 'S' ou 's' para aceitar. Em seguida feche o terminal do powershell e abra sua IDE. 

2.4 Com a IDE(VS Code ou Pycharm, recomendo a segunda IDE) aberta, abra o terminal da IDE e execute esse comando para criar sua venv:

```
python -m venv venv
```

2.5 Com a sua venv criada, execute esse comando para ativa-la:

```
.\venv\Scripts\activate
```

1.6 Após ativação da sua venv, seu terminal deverá está dessa forma:
Indicando que a sua venv está ativa. Feche o terminal e abra novamente, para assegurar que sua venv está ativa. 

```
(venv) PS C:\Users\jonat\PycharmProjects\tahechitservice>
```

2.7 Outra forma de ativar a sua venv é pela propria IDE (Pycharm), essa opção pode ser feita tanto em sistemas Linux e Windows:

2.7.1 Procure no canto inferior direito da sua IDE (Pycharm) por 'No interpreter':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f8d900722002ab3ca18.png" alt="<No interpreter>">

2.7.2 Clique em 'Interpreter Settings...':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f8f30ae430016c49644.png" alt="Interpreter Settings">

2.7.3 Clique em 'Add Interpreter > Add Local Interpreter...':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f94ebf05b000cb5757d.png" alt="Add Interpreter">

2.7.4 Verifique 'Environment', 'Location' e 'Base interpreter':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f96052c41000ce1e125.png" alt="Add Interpreter Config">

- Environment: 

```
Terá duas opções, 'Existing' ou 'New' por padrão quando não tem uma venv já criada no seu projeto a opção estará marcada com 'New', e a IDE será responsavel por criar.
```

- Location:

```
Local onde a sua 'venv' está, certifique que está ou será criada, verifique se está dentro do seu projeto. 
```

- Base interpreter:

```
É a base do seu interpretador, de qual versão do python ele será criado, certifique-se de está na versão que você instalou no seu SO e a mesma verão do projeto.
```

Após isso é só clicar em 'Ok' e deixar a IDE trabalhar e fazer a indexação do interpretador. 

## 3. Instale os pacotes requeridos.
```
pip install -r requirements-dev.txt
```

# .env

* Crie na raiz do projeto um arquivo '.env' esse arquivo será responsável pelas variáveis de ambiente do projeto.
* O mesmo deve conter as seguintes variáveis para funcionamento do projeto:

```
SECRET_KEY=
DEBUG=
ALLOWED_HOSTS=
SITE_HOST=

GOOGLE_OAUTH_CLIENT_ID=
GOOGLE_OAUTH_SECRET=

EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=
```
* Contate o [Gestor]() ou o [Desenvolvedor]() do projeto para ele lhe fornecer as keys das variáveis de ambiente.
* O arquivo '.env' não deve conter no seu repositório do github pois o mesmo leva informações sensiveis de outras conexões externas que o projeto necessita.
* Cada projeto django necessita de uma SECRET_KEY, você pode criar a sua dessa forma:
Abra o Python Console dentro da sua IDE, rode o comando:

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f7a2efb36fa0013ed37f6.png" alt="Python Console">

```
from django.core.management.utils import get_random_secret_key
```

Após importar o get_random_secret_key, rode o segundo comando: 

```
print(get_random_secret_key())
```

* Pronto, a sua SECRET_KEY será gerada na tela do console, é só copiar e colar no local de destino dentro do seu arquivo '.env'


## 4. Crie banco de dados (Por padrão ele criará um banco SQlite, já vem pré-definido nas configurações(settings.py) de todo projeto django).

```
python manage.py migrate
```

4.1 Você pode criar um banco de sua preferencia: PostgresSQL, MySQL, MongoBD, MariaDB. Fica ao seu critério, contanto que siga a recomendação da documentação do Django.
Por exemplo: Conectando o projeto com o banco [PostgreSQL](https://stackpython.medium.com/how-to-start-django-project-with-a-database-postgresql-aaa1d74659d8).

Adicione ao seu arquivo '.env' a seguinte variavel de ambiente: 

```
DATABASE_URL=
```

Após criar o seu banco, passe a seguinte url na variavel: 

```
DATABASE_URL=postgres://USER:PASSWORD@HOST:PORT/NAME
```

Exemplos de outras conexões com outros bancos: 

| Engine  | Django Backend | URL |
| ------------- | ------------- | ------------- |
| MySQL  | django.db.backends.mysql  | mysql://USER:PASSWORD@HOST:PORT/NAME  |
| Oracle  | jango.db.backends.oracle  | oracle://USER:PASSWORD@HOST:PORT/NAME  |


Após fazer a sua configuração rode o comando para migrar e criar as tabelas do projeto:

```
python manage.py migrate
```


## 5. Start o servidor

```
python manage.py runserver
```

5.1 Você pode configurar o start do servidor direto na IDE(Pycharm), da seguinte forma: 

Procure na IDE por 'Current File' e clique em 'Edit Configurations...':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f9407f9ccba000d8bbd02.png" alt="Edit Configurations">

Após abrir o 'Edit Configurations...' clique em 'Add New' e selecione 'Django Server':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f940a6cbb720018144b2c.png" alt="Edit Configurations">

Após selecionar 'Django Server' revise as configurações:

* Renomeei o nome do servidor.  
* Verifique se o Python interpreter está apontando corretamente para a sua venv.
* Verifique se 'Add content' e 'Add source' estão marcadas. 

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f956abc7372002c99c6bd.png" alt="Django Server">

Após isso é só clicar no 'Ok' e verificar se a configuração do servidor deu certo, ficando a mesma forma como no imagem, é só clicar no 'play' e esperar o servidor startar. 

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f96c86d21cd0016badb88.png" alt="Finish">


## :gear: Configurando Heroku - Para atualizar o projeto

Levando em consideração que você seja o responsável pelo gerenciamento do projeto, e já tenha instalado o [Heroku CLI](https://github.com/JbSampaio/TESTE/blob/main/README.md#-pr%C3%A9-requisitos), reiniciado sua máquina para adiciona-lo ao path do SO. Siga o passo a passo a seguir. 

* Abra o terminal da sua IDE e rode o seguinte comando: 

```
heroku login
```

O comando “heroku login” é utilizado para autenticar seu usuário no CLI. Caso não saiba o usuário, entre em contato com o [Gestor](vinicius@tahech.com).
