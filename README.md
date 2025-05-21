
# Projeto hotelaria

Nesse projeto, objetivo é criar um sistema de gestão de hotel, utilizando tecnologias como framework Django, HTML, CSS. 

## Como utilizar :

1. Criação do ambiente virtual
    
    Como o repositório esta clonado ou baixado do github, a venv está geralmente no `.gitignore`, os repositórios costumam a ignorar a pasta do ambiente virtual por alguns motivos como: 
    
    - Elas são grandes;
    - Contêm arquivos específicos do sistema operacional e do caminho onde foram criadas;
    - Não são portáveis entre diferentes máquinas/sistemas;
    - Podem ser facilmente reconstruídas a partir do `requirements.txt` ou `pyproject.toml`.
    
    Então para poder cria-lo novamente abra o terminal (`ctrl+""`) e digite a seguinte linha de código:
    
    ```bash
    python -m venv venv  #Criando o ambiente 
    
    venv\Scripts\activate #Acessando o ambiente
    ```
    
    *Para poder utilizar o framework é necessário estar dentro do ambiente virtual*
    
    Caso você queira clonar o repositório via terminal utilize a seguinte linha de código:
    
    ```bash
    git clone https://github.com/usuario/repositorio.git
    
    cd repositorio
    ```
    

1. ***Instalação do Django***
    
    O Django pode ser instalado facilmente **`pip`**dentro do seu ambiente virtual.
    
    No prompt de comando, certifique-se de que seu ambiente virtual esteja ativo e execute o seguinte comando:
    
    ```bash
    pip install Django
    ```
    

