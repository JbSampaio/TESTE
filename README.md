# Tahech IT Service

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)


Trata-se de um sistema baseado em microsserviços, para uso do escritório, utilizando soluções tecnologicas já desenvolvidas pela equipe de TI da Tahech Advogados.
O sistema está online através do link: [Tahech | IT Service](<https://tahechitservice.herokuapp.com/>)


## 💻 Pré-requisitos

Antes de começar, verifique se você atendeu aos seguintes requisitos:
<!---Estes são apenas requisitos de exemplo. Adicionar, duplicar ou remover conforme necessário--->
* Você instalou a versão 3.10.8 do Python? Caso não tenha instalado segue o link [Heroki CLI](https://www.python.org/ftp/python/3.10.8/python-3.10.8-amd64.exe).
* Esse projeto foi desenvolvido em SO `<Windows>`. Ainda serão feitos testes no SO Linux, em breve conterá informações de como configurar em sistemas Linux.
* Você irá gerir o projeto sozinho? Caso você seja o responsável por gerir o projeto haverá a necessidade de instalar o CLI do Heroku? Caso não tenha instalado segue o link para instalação [Python 3.10.8](https://cli-assets.heroku.com/heroku-x64.exe).
* Caso você não faça o gerenciamento sozinho do projeto, pode dispensar a instalação do Heroku CLI.

## 🚀 Instalando Tahech | IT Service

Para instalar o tahechitservice, siga estas etapas:

1.Clone o projeto em sua máquina.

```
git clone <url do repositorio>
```
2.Crie a virtualenv.

![Linux](https://img.shields.io/badge/Linux-E34F26?style=for-the-badge&logo=linux&logoColor=black)
```
python3 -m venv venv
source/bin/activate
```
![Windows](https://img.shields.io/badge/Windows-017AD7?style=for-the-badge&logo=windows&logoColor=white)

Será necessário uma configuração via powershell, para a sua venv ativar imediatamente quando fechar o projeto.

1.1 Abra o powershell como administrador

1.2 Execute esse comando:

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

1.3 Ao executar o comando digite 'S' ou 's' para aceitar. Em seguida feche o terminal do powershell e abra sua IDE. 

1.4 Com a IDE(VS Code ou Pycharm, recomendo a segunda IDE) aberta, abra o terminal da IDE e execute esse comando para criar sua venv:

```
python -m venv venv
```

1.5 Com a sua venv criada, execute esse comando para ativa-la:

```
.\venv\Scripts\activate
```

1.6 Após ativação da sua venv, seu terminal deverá está dessa forma:
Indicando que a sua venv está ativa. Feche o terminal e abra novamente, para assegurar que sua venv está ativa. 

```
(venv) PS C:\Users\jonat\PycharmProjects\tahechitservice>
```

1.7 Outra forma de ativar a sua venv é pela propria IDE (Pycharm), essa opção pode ser feita tanto em sistemas Linux e Windows:

1.7.1 Procure no canto inferior direito da sua IDE (Pycharm) por '<No interpreter>':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f8d900722002ab3ca18.png" alt="<No interpreter>">

1.7.2 Clique em 'Interpreter Settings...':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f8f30ae430016c49644.png" alt="Interpreter Settings">

1.7.3 Clique em 'Add Interpreter > Add Local Interpreter...':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f94ebf05b000cb5757d.png" alt="Add Interpreter">

1.7.4 Verifique 'Environment', 'Location' e 'Base interpreter':

<img src="https://s3.amazonaws.com/plugcrm-app/62b3648b6967ed00168486c4/instance_file/638f4f96052c41000ce1e125.png" alt="Add Interpreter Config">

- Environment: 

```
Terá duas opções, 'Existing' ou 'New' por padrão quando não tem uma venv já criado no seu projeto a opção estará marcada com 'New', e a IDE será responsavel por criar.
```

- Location:

```
Local onde a sua 'venv' está, certifique que está dentro do seu projeto. 
```

- Base interpreter:

```
É a base do seu interpretador, de qual versão do python ele será criado, certifique-se de está na versão que você instalou no seu SO e a mesma verão do projeto.
```

Após isso é só clicar em 'Ok' e deixar a IDE trabalhar e fazer a indexação do interpretador. 

3.Instale os pacotes requeridos.
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
* Contate o Gestor ou o Desenvolvedor do projeto para ele lhe fornecer as keys das variáveis de ambiente.
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

Pronto, a sua SECRET_KEY será gerada na tela do console, é só copiar e colar no local de destino dentro do seu arquivo '.env'


4.Crie banco de dados (Por padrão ele criará um banco SQlite, já vem pré-definido nas configurações(settings.py) de todo projeto django).

```
python manage.py migrate
```

4.1Você pode criar um banco de sua preferencia: PostgresSQL, MySQL, MongoBD, MariaDB. Fica ao seu critério, contanto que siga a recomendação da documentação do Django.
Por exemplo: Conectando o projeto com o banco [PostgreSQL](https://stackpython.medium.com/how-to-start-django-project-with-a-database-postgresql-aaa1d74659d8).

```
python manage.py migrate
```

5.Start o servidor

```
python manage.py runserver
```
