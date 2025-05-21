# Projeto hotelaria

Nesse projeto, objetivo é criar um sistema de gestão de hotel, utilizando do framework Django, HTML, CSS. 

## Como utilizar :

1. Criação do ambiente virtual, como o repositório esta clonado ou baixado do github, a venv está geralmente no `.gitignore`, os repositórios costumam a ignorar a pasta do ambiente virtual por alguns motivos como: 
    - Elas são grandes;
    - Contêm arquivos específicos do sistema operacional e do caminho onde foram criadas;
    - Não são portáveis entre diferentes máquinas/sistemas;
    - Podem ser facilmente reconstruídas a partir do `requirements.txt` ou `pyproject.toml`.
    
    Então para poder cria-lo novamente abra o terminal (`ctrl+""`) e digite a seguinte linha de código:
    
    ```bash
    venv\Scripts\activate
    ```
    

Caso você queira clonar o repositório via terminal utilize a seguinte linha de código:

```bash
git clone https://github.com/usuario/repositorio.git

cd repositorio
```

tutorial de como iniciar uma aplicação django

Ambiente virtual

criar projeto

criar app

configurar settings

configurar urls(app) 

criar templates

configurar settings                                              Uma única vez(configuração do django)

criar rota

configurar media+static

configuração do settings e urls

configurar super user

rodar as migrações

criar modal     

criar rota                                                                    loop

config url

roda migração

## Configurando um ambiente virtual [**¶**](https://docs.djangoproject.com/en/5.2/howto/windows/#setting-up-a-virtual-environment)

É uma prática recomendada fornecer um ambiente dedicado para cada projeto Django criado. Há muitas opções para gerenciar ambientes e pacotes dentro do ecossistema Python, algumas das quais são recomendadas na [documentação do Python](https://packaging.python.org/guides/tool-recommendations/) . O próprio Python vem com [o venv](https://docs.python.org/3/tutorial/venv.html) para gerenciar ambientes, que usaremos neste guia.

Para criar um ambiente virtual para seu projeto, abra um novo prompt de comando, navegue até a pasta onde deseja criar seu projeto e digite o seguinte:

```powershell
 venv nome_do_projeto
```

Isso criará uma pasta chamada "nome-do-projeto", caso ela ainda não exista, e configurará o ambiente virtual. Para ativar o ambiente, execute:

```powershell
nome_do_projeto\Scripts\activate.bat
```

## Instalar Django

O Django pode ser instalado facilmente **`pip`**dentro do seu ambiente virtual.

No prompt de comando, certifique-se de que seu ambiente virtual esteja ativo e execute o seguinte comando:

```powershell
pip install Django
```

Isso fará o download e instalará a versão mais recente do Django.

Após a conclusão da instalação, você pode verificar a instalação do Django executando no prompt de comando.

```powershell
**django-admin --version    #printa a versão do django**
```

## Saída de terminal colorida [**¶**](https://docs.djangoproject.com/en/5.2/howto/windows/#colored-terminal-output)

Um recurso de qualidade de vida adiciona saída colorida (em vez de monocromática) ao terminal. Em terminais modernos, isso deve funcionar tanto para CMD quanto para PowerShell. Se, por algum motivo, isso precisar ser desabilitado, defina a variável de ambiente [**`DJANGO_COLORS`**](https://docs.djangoproject.com/en/5.2/ref/django-admin/#envvar-DJANGO_COLORS)para **`nocolor`**.

Em versões mais antigas do Windows ou terminais legados, [o colorama](https://pypi.org/project/colorama/) 0.4.6+ deve ser instalado para habilitar a coloração de sintaxe:

```powershell
**...\>** py -m pip install "colorama >= 0.4.6"
```

Veja [Coloração de sintaxe](https://docs.djangoproject.com/en/5.2/ref/django-admin/#syntax-coloring) para mais informações sobre configurações de cores.

## Armadilhas comuns (Opcional)

- Se **`django-admin`**exibir apenas o texto de ajuda, independentemente dos argumentos fornecidos, provavelmente há um problema com a associação de arquivos no Windows. Verifique se há mais de uma variável de ambiente definida para executar scripts Python no **`PATH`**. Isso geralmente ocorre quando há mais de uma versão do Python instalada.
- Se você estiver se conectando à internet por meio de um proxy, pode haver problemas ao executar o comando . Defina as variáveis de ambiente para configuração do proxy no prompt de comando da seguinte maneira:**`py -m pip install Django`**
    
    ```powershell
    **...\>** **set** http_proxy=http://username:password@proxyserver:proxyport
    **...\>** **set** https_proxy=https://username:password@proxyserver:proxyport
    ```
    

## **Instalando a versão de desenvolvimento**

Se você quiser poder atualizar seu código Django ocasionalmente com as últimas correções de bugs e melhorias, siga estas instruções:

1. Certifique-se de que [o Git](https://git-scm.com/) esteja instalado e que você consiga executar seus comandos a partir de um shell. (Digite em um prompt de shell para testar.)**`git help`**
2. Confira o principal branch de desenvolvimento do Django assim:
    
    ```powershell
    **$** git clone https://github.com/django/django.git
    ```
    
    Isso criará um diretório **`django`**no seu diretório atual.
    
3. Certifique-se de que o interpretador Python consiga carregar o código do Django. A maneira mais conveniente de fazer isso é usar um ambiente virtual e [o pip](https://pip.pypa.io/) . O [tutorial de contribuição](https://docs.djangoproject.com/en/5.2/intro/contributing/) explica como criar um ambiente virtual.
4. Após configurar e ativar o ambiente virtual, execute o seguinte comando:
    
    ```powershell
    **$** python -m pip install -e django/
    ```
    
    Isso tornará o código do Django importável e também disponibilizará o **`django-admin`**comando do utilitário. Em outras palavras, está tudo pronto!
    

Vamos supor que você já tenha [o Django instalado](https://docs.djangoproject.com/en/5.2/intro/install/) . Você pode verificar se o Django está instalado e qual versão está executando o seguinte comando em um prompt de shell (indicado pelo prefixo 

```powershell
**...\>** py -m django --version
```

Se o Django estiver instalado, você deverá ver a versão da sua instalação. Caso contrário, você receberá um erro informando "Nenhum módulo chamado django".

## Criando um projeto

Se esta é a sua primeira vez usando Django, você precisará realizar algumas configurações iniciais. Você precisará gerar automaticamente um código que estabeleça um [projeto](https://docs.djangoproject.com/en/5.2/glossary/#term-project) Django – um conjunto de configurações para uma instância do Django, incluindo configuração do banco de dados, opções específicas do Django e configurações específicas do aplicativo.

Na linha de comando, **`cd`**entre no diretório onde você gostaria de armazenar seu código e crie um novo diretório chamado **`djangotutorial`**. (Esse nome de diretório não importa para o Django; você pode renomeá-lo como quiser.)

```powershell
mkdir djangotutorial
```

Em seguida, execute o seguinte comando para inicializar um novo projeto Django:

```powershell
**$** django-admin startproject mysite djangotutorial
```

Veja a estrutura de diretório criada com o comando [**`startproject`**](https://docs.djangoproject.com/pt-br/5.2/ref/django-admin/#django-admin-startproject):

`djangotutorial/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py`

Esses arquivos são:

- **`manage.py`**: um utilitário de linha de comando que permite a você interagir com esse projeto Django de várias maneiras. Você pode ler todos os detalhes sobre o **`manage.py`** em [django-admin and manage.py](https://docs.djangoproject.com/pt-br/5.2/ref/django-admin/).
- **`mysite/`**: Um diretório que contém o pacote Python real do seu projeto. O nome dele é o nome do pacote Python que você precisará usar para importar qualquer coisa dentro dele (por exemplo, **`mysite.urls`**).
- **`mysite/__init__.py`**: um arquivo vazio que diz ao Python que este diretório deve ser considerado um pacote Python. Se você é um iniciante Python, leia [mais sobre pacotes](https://docs.python.org/3/tutorial/modules.html#tut-packages) na documentação oficial do Python.
- **`mysite/settings.py`**: configurações para este projeto Django. [Configurações do Django](https://docs.djangoproject.com/pt-br/5.2/topics/settings/) irá revelar para você tudo sobre o funcionamento do **`settings`**.
- **`mysite/urls.py`**: as declarações de URLs para este projeto Django; um “índice” de seu site movido a Django. Você pode ler mais sobre URLs em [Despachante de URL](https://docs.djangoproject.com/pt-br/5.2/topics/http/urls/).
- **`mysite/asgi.py`**: um ponto de integração para servidores web compatíveis com ASGI usado para servir seu projeto. Veja [Como fazer o deploy com ASGI](https://docs.djangoproject.com/pt-br/5.2/howto/deployment/asgi/) para mais detalhes.
- **`mysite/wsgi.py`**: um ponto de integração para servidores web compatíveis com WSGI usado para servir seu projeto. Veja [Como implementar com WSGI](https://docs.djangoproject.com/pt-br/5.2/howto/deployment/wsgi/) para mais detalhes.

## O servidor de desenvolvimento(terminal)

Vamos verificar se o seu projeto Django funciona. Acesse o **`djangotutorial`** diretório, caso ainda não tenha feito isso, e execute os seguintes comandos:

```powershell
**$** python manage.py runserver
```

Você verá a seguinte saída na sua linha de comando:

```
Executando verificações do sistema...
A verificação do sistema não identificou problemas (0 silenciados).
Você tem migrações não aplicadas; seu aplicativo pode não funcionar corretamente até que elas sejam aplicadas.
Execute 'python manage.py migrate' para aplicá-los.
abril 15, 2025 - 15:50:53
Django versão 5.2, usando as configurações 'mysite.settings'
Iniciando o servidor de desenvolvimento emhttp://127.0.0.1:8000/
Saia do servidor com CONTROL-C.
AVISO: Este é um servidor de desenvolvimento. Não o utilize em ambiente de produção. Em vez disso, utilize um servidor WSGI ou ASGI de produção.
Para mais informações sobre servidores de produção, consulte:https://docs.djangoproject.com/en/ 5.2/howto/deployment/
```

## Criando a aplicação de enquetes: Polls

Agora que seu ambiente – um “projeto” – está configurado, você está pronto para começar o trabalho.

Cada aplicação que você escreve no Django consiste de um pacote Python que segue uma certa convenção. O Django vem com um utilitário que gera automaticamente a estrutura básica de diretório de uma aplicação, então você pode se concentrar apenas em escrever código em vez de ficar criando diretórios.

**Projetos versus aplicações**

Seus aplicativos podem estar em qualquer lugar no seu [caminho Python](https://docs.python.org/3/tutorial/modules.html#tut-searchpath) . Neste tutorial, criaremos nosso aplicativo de enquete dentro da **`djangotutorial`**pasta.

Para criar sua aplicação, certifique-se de que esteja no mesmo diretório que **`manage.py`** e digite o seguinte comando:

```powershell
**$** python manage.py startapp polls
```

Isto criará um diretório **`polls`**, com a seguinte estrutura:

[DJANGO: (2)](https://www.notion.so/DJANGO-2-1fac098920f2808e89d8fa54331f6c18?pvs=21)

`polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py`

Esta estrutura de diretório irá abrigar a aplicação de enquete.

## Escreva sua primeira view

Hora de criar a primeira view. Abra o arquivo **`polls/views.py`** e ponha o seguinte código em Python dentro dele:

```powershell
polls/views.py[**¶**](https://docs.djangoproject.com/pt-br/5.2/intro/tutorial01/#id1)
```

```powershell
**from** **django.http** **import** HttpResponse

**def** **index**(request):
    **return** HttpResponse("Hello, world. You're at the polls index.")
```

Esta é a visualização mais básica possível no Django. Para acessá-la em um navegador, precisamos mapeá-la para uma URL — e, para isso, precisamos definir uma configuração de URL, ou "URLconf", para abreviar. Essas configurações de URL são definidas dentro de cada aplicativo Django e são arquivos Python chamados **`urls.py`**.

Para definir um URLconf para o **`polls`**aplicativo, crie um arquivo **`polls/urls.py`** com o seguinte conteúdo:

```powershell
polls/urls.py[**¶**](https://docs.djangoproject.com/pt-br/5.2/intro/tutorial01/#id2)
```

```powershell
**from** **django.urls** **import** path

**from** **.** **import** views

urlpatterns **=** [
    path("", views**.**index, name**=**"index"),
]
```

O diretório do seu aplicativo agora deve ficar assim:

`polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    urls.py
    views.py`

O próximo passo é configurar o URLconf raiz no **`mysite`**projeto para incluir o URLconf definido em **`polls.urls`**. Para isso, adicione uma importação para **`django.urls.include`**in **`mysite/urls.py`**e insira um [**`include()`**](https://docs.djangoproject.com/pt-br/5.2/ref/urls/#django.urls.include)na **`urlpatterns`**lista, assim você terá:

```powershell
mysite/urls.py[**¶**](https://docs.djangoproject.com/pt-br/5.2/intro/tutorial01/#id3)
```

```powershell
**from** **django.contrib** **import** admin
**from** **django.urls** **import** include, path

urlpatterns **=** [
    path("polls/", include("polls.urls")),
    path("admin/", admin**.**site**.**urls),
]
```

A [**`path()`**](https://docs.djangoproject.com/pt-br/5.2/ref/urls/#django.urls.path)função espera pelo menos dois argumentos: **`route`**e **`view`**. A [**`include()`**](https://docs.djangoproject.com/pt-br/5.2/ref/urls/#django.urls.include)função permite referenciar outros URLconfs. Sempre que o Django encontra [**`include()`**](https://docs.djangoproject.com/pt-br/5.2/ref/urls/#django.urls.include), ele corta qualquer parte da URL correspondente até aquele ponto e envia a string restante para o URLconf incluído para processamento posterior.

A idéia por trás do [**`include()`**](https://docs.djangoproject.com/pt-br/5.2/ref/urls/#django.urls.include) é facilitar plugar URLs. Uma vez que polls está em sua própria URLconf (**`polls/urls.py`**), ele pode ser colocado depois de “/polls/”, ou depois de “/fun_polls/”, u depois de “/content/polls/”, ou qualquer outro início de caminho, e a aplicação ainda irá funcionar

Agora você amarrou uma view **`index`** no seu URLconf. Verique se funciona com o seguinte comando:

```powershell
**$** python manage.py runserver
```

Acesse http://localhost:8000/polls/ no seu navegador, e deverá ver o texto “*Hello, world. You’re at the polls index.*”, o qual foi definido na view “index”.

Teste de hoje:

[]()

---

## 23/04

### 🗂️ 1. **Criação das pastas `static/` e `media/`**

Essas pastas são usadas para arquivos estáticos (CSS, JS, imagens) e arquivos enviados pelo usuário (uploads, como fotos).

Dentro do seu projeto Django:

```bash
mkdir static media

```

---

### ⚙️ 2. **Configuração no `settings.py`**

Vai no `settings.py` e adiciona (ou edita) isso:

```python
import os

# STATIC
STATIC_URL = '/static/'
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'static')]  # para arquivos durante dev
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')    # para produção

# MEDIA
MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')

```

No `urls.py` principal (o que está ao lado do `settings.py`):

```python
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    # suas rotas aqui...
]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

```

---

### 👑 3. **Criar o superuser (usuário admin)**

Depois de fazer a migração inicial, você cria o superuser assim:

```bash
python manage.py createsuperuser

```

Ele vai pedir nome de usuário, email e senha. E pronto, lindinha, seu admin está criado! ✨

---

### 🛠️ 4. **Rodar as migrações**

Pra criar as tabelas no banco de dados:

```bash
python manage.py makemigrations
python manage.py migrate

```

---

### 💬 5. **Criar um modal (modelo) em Django**

No seu `models.py` de algum app:

```python
from django.db import models

class Produto(models.Model):
    nome = models.CharField(max_length=100)
    preco = models.DecimalField(max_digits=8, decimal_places=2)
    descricao = models.TextField()
    imagem = models.ImageField(upload_to='produtos/')  # precisa da pasta 'media/produtos'

    def __str__(self):
        return self.nome

```

Depois disso, você faz:

```bash
python manage.py makemigrations
python manage.py migrate

```

Se quiser que ele apareça no admin:

No `admin.py` do seu app:

```python
from django.contrib import admin
from .models import Produto

admin.site.register(Produto)

```

---
