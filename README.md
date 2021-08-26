

<p align="center"> 
      <img src="https://avatars.githubusercontent.com/u/48964967?v=4 width="350px" height="400px"/>
      <img src="https://static.wixstatic.com/media/b62a2d_c2df19675c714549aaa69b335bf37e13~mv2.png/v1/fill/w_188,h_188,al_c,q_85,usm_0.66_1.00_0.01/monitec_2.webp" alt="monitec_2.png" style="width: 94px; height: 94px; object-fit: cover; object-position: 50% 50%;">  
     
                                                                                                                                                 
<p align="center"> 

## 💻 Integrador-Econect
                                  
O Integrador-Econect reúne diversas integrações do econect com plataformas como a PROPZ solução de CRM e inteligência analítica, Panamah um serviço de análise de Big Data, Izio plataforma de CRM para o varejo e gestor de ofertas, Concentrador web que agrega várias funcionalidades ao concentrador padrão e integrações com Ecommerces externos que utilizam o ERP RMS da TOTVS. Segue abaixo as funcionalidades referentes a cada integração com as plataformas citadas, e o CRM Ofertas Personalizadas.
        
<strong>PROPZ:</strong> serviços de exportação de movimentos para a Propz, integração de movimentos da Propz, realização da exportação de relatórios diários e do dia anterior para Propz.
                 
<strong>Ecommerce:</strong> serviços de importação e atualização de produtos, vindo do RMS para a base do Concentrador WEB, exportação de estoque que realizar o envio de estoque atualizado para a WEVO dos produtos na base do ecommerce.
                 
<strong>Panamah:</strong> serviços de exportação de vendas e produtos para o Panamah
                 
<strong>Concentrador-web:</strong> serviço de importação de usuário tem por suma funcionalidade buscar os usuários do Concentrador WEB.
                 
<strong>Ofertas Personalizadas:</strong> serviço de definição do tempo da Integração das Ofertas Personalizadas. 
                 
<strong>Izio:</strong> serviços de exportação de produtos e pessoas para a Izio, e importação de personas da Izio para o Fidelidade.
             
## Tópicos

- [Tecnologias](#-Tecnologias)
- [Como executar o Integrador-Econect](#-Como-executar-o-Integrador-Econect)
- [Features](#-Features)
- [Contribuidores](#-Contribuidores)
- [Autor](#-Autor)
- [Licença](#-Licença)

## 🛠 Tecnologias

As seguintes ferramentas foram usadas na construção do projeto:
                 

   <ul> 
  <li><a href="https://www.java.com">
    <img src="https://img.shields.io/badge/Java%2012.0-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="java">
  </a></li>
  <li><a href="https://www.mysql.com">
    <img src="https://img.shields.io/badge/MySQL_v1.7-316192?style=for-the-badge&logo=mysql&logoColor=white" alt="mysql">
  </a> </li>
  <li><a href="https://spring.io/projects/spring-boot">
    <img src="https://img.shields.io/badge/Spring_Boot_2.5.1-%6DB33F.svg?&style=for-the-badge&logo=spring&logoColor=white" alt="spring-boot">
  </a></li>
  <li><a href="https://maven.apache.org/">
    <img src="https://img.shields.io/badge/Apache Maven_3.8.1-E4405F.svg?&style=for-the-badge&logo=apachemaven&logoColor=white" alt="apache-maven">
  </a></li>
   <li><a href="https://projectlombok.org/">
    <img src="https://img.shields.io/badge/Lombok_1.18.8-F7B500.svg?&style=for-the-badge&logo=&logoColor=white" alt="Lombok">
  </a></li>
   <li><a href="https://aws.amazon.com/">
    <img src="https://img.shields.io/badge/Amazon_AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="amazon">
   </a></li>
   <li><a href="https://sites.google.com/site/gson/gson-user-guide">
    <img src="https://img.shields.io/badge/gson_2.8.5-007CFF?&style=for-the-badge&logo=&logoColor=white" alt="gson">
  </a></li>
   <li><a href="https://www.h2database.com/html/main.html">
    <img src="https://img.shields.io/badge/h2database_1.4.199-43B02A?&style=for-the-badge&logo=white" alt="h2database">
  </a></li>                                                                                                                            
    </ul>                            
                                                                                                                                       

## 🚀 Como executar o Integrador-Econect
                                                                                                                 
### Pré-requisitos

Antes de começar, você vai precisar ter instalado em sua máquina o e-conect, Java JDK 1.8, MySQL 5.7, FTP e SSH, Mavem,
além disto é bom ter um editor para trabalhar com o código como Eclipse ou o Intellij em ambos é necessário instalar e configurar o lombok.


### 🎲 Executando o Integrador Econect
 
## Instruções de Configuração
### Configurações 

## Adiciona Dependência
Para executar o Build do projeto utilizando o `Maven` , é necessário adicionar uma dependência privada referente ao Panamah.

Primeiramente copie o arquivo `settings.xml` que se encontra dentro do diretório do integrador para o diretório `~/.m2`. Execute no terminal:

    cp  /<path-integrador>/settings.xml ~/.m2

Para finalizar, ainda dentro do diretório do integrador, execute no terminal o comando:

    mvn clean install -s settings.xml 
    ou
    mvn clean install -Dmaven.test.skip=true -s settings.xml
para realizar o build da dependência.

#### Adiciona driver banco de dados oracle
Para executar o Build do projeto , é necessário adicionar o driver referente ao banco de dados da oracle.

Entre na pasta `anexos` localizada dentro da pasta do projeto do integrador. 
Dentro dela há o driver para o banco de dados da oracle `ojdbc7.jar`.

Execute o seguinte comando no terminal (*Obs: Certifique-se de estar dentro da mesma pasta onde se encontra o arquivo ojdbc7.jar*): 

```mvn install:install-file -Dfile=./ojdbc7.jar -DgroupId=com.oracle -DartifactId=ojdbc7 -Dversion=12.1.0 -Dpackaging=jar```

#### Base de Dados
*Atenção: Não esqueça de rodar o [script de normalização](https://github.com/socin-econect/script-normalizacao) na sua base*

Para configurar o acesso a base de dados, você deve editar o application.properties como o exemplo abaixo. 

*Atenção: Só devem ser alterados os pontos delimitados com <>, a alteração de qualquer outro ponto pode gerar impactos negativos para execução da aplicação*
```
# ===============================
#  CONCENTRADOR
# ===============================

# Configurações do Datasource da Aplicação

# Url de Conexão
concentrador.datasource.jdbc-url = mysql://<IP-DO-INTEGRADOR>:3306/<NOME-DO-BANCO-DE-DADOS>?useSSL=false

# Usuário e Senha
concentrador.datasource.username = <USUARIO-DO-BANCO-DE-DADOS>
concentrador.datasource.password = <SENHA-DO-USUARIO>

...

```
## Configurações de IDE
### Intellij
[Baixe o Intellij Aqui](https://www.jetbrains.com/idea/download/#section=linux)

Lista de Plug-ins utilizados:

| Plugin | Descrição |
| ------ | ------ |
|Eclipse Code Formatter|Permite a formação de código no estilo do esclipse, mantendo o padrão de formatação entre Eclipse e Intellij|
|Lombok|Plug-in que permite a suporte a biblioteca do Lombok|
##### Eclipse Code Formatter
- Installe o plug-in eclipse code formatter no Intellij
- Reinicie o Intellij
- Vá em Configurações -> Other Settings -> Eclipse Code Formatter
- Selecione 'Use the Eclipse code formatter'
- Em Eclipse Java Formatter config file selecione em 'Browse' o arquivo de formatação de código (`eclipse-mars-java-google-style.xml`), localizado na pasta 'anexo' do projeto

##### Lombok
- Veja a documentação para instalação do `Lombok` [aqui](https://github.com/socin-econect/econect-server/wiki/Instala%C3%A7%C3%A3o-Lombok).

#### Configurações do Ambiente
##### Code Style:
- Vá em Settings -> Editor -> Code Style, mude Hard wrap para 100 e Visual guides para 100 colunas.
##### Tabs e Ident:
- Vá em Settings -> Editor -> Code Style -> Java -> Tabs and Idents e defina Tab Size e Ident para 2 e Continuation ident para 4
##### Imports:
- Vá em Settings -> Editor -> Code Style -> Java -> Imports e mude Class count to use import with '*' e Names count to use static import with '*' para 999
##### Java (Última Versão):
- [Baixe o open-jdk 12 aqui](https://download.java.net/java/GA/jdk12/GPL/openjdk-12_linux-x64_bin.tar.gz)
  - Extraia o arquivo para o local desejado (que não a pasta do projeto)
- Vá em File -> Settings -> Build, Execution, Deployment -> Compiler -> Java Compiler
  - Mude o Target bytecode version para 12
  - Dê apply
- Em seguida vá para File -> Project Structure -> Project
  - Mude o project SDK e aponte para o java extraído
  - Mude Project language level para 12
  - Dê apply
- Logo após vá em Run -> Edit Configurations -> Templates -> Application
  - Em JRE aponte selecione SDK do java extraído
  - No canto esquerdo desta janela clique em '+' -> Application
  - Defina um nome para a Application
  - Em Main Class defina a classe principal do projeto
  - Dê Apply
                                                                                                                 

### 🎁 Geração do executavel produção
                                                                                                                 
## Gerando .JAR
Para implantar no você precisa ter o maven instalado na sua máquina para isto execute o seguinte comando:
```git
sudo apt install maven -y
```
Em seguida é necessário vincular o maven instalado com o `jdk-12` para isto deve-se criar um atalho no `bashrc`, assim abra o bashrc:
```shell
sudo gedit ~/.bashrc
```
Em seguida insira o código abaixo no final do `.bashrc`:
```shell

alias mvn12="JAVA_HOME=<caminho-para-o-jdk>/jdk-12 && mvn"
```
Salve, feche o editor e execute o seguinte comando para recarregar o terminal:
```shell
sudo . ~/.bashrc
```
Feito isto navegue até a pasta do projeto do integrador e execute o seguinte comando para gerar a instalação:
```shell
mvn12 clean && mvn12 -X package && java -jar ./target/integrador.1.0.jar
```
Após o comando ser executado, um .jar deve ser gerado na pasta `/target` do projeto.
                                                                                                        
## 💫 Features

O conteúdo referente as features do Integrador-Econect se encontra no local  do link abaixo.

https://socincompany.atlassian.net/wiki/spaces/E

## 😃 Autor

<p align="center"> 
   <a href="https://www.socin.com.br/">
      <img style="border-radius: 50%;" src="https://avatars.githubusercontent.com/u/48964967?v=4" width="100px;" alt="socin"/>
   </a>
</p>
<p align="center"> 
      <sub><b>Socin Sistemas</b></sub></a> <a href="https://www.socin.com.br/" title="Socin">🚀</a>
<p align="center"> 
 Feito com ❤️  pela equipe de desenvolvimento Socin Sistemas!
</p>
<p align="center"> 
 <a href="https://www.facebook.com/socinsistemas"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" alt="Facebook"></a>
<a href="https://www.linkedin.com/company/socinsistemas/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Linkedin"></a>
<a href="https://www.instagram.com/socinsistemas/?hl=pt-br"><img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram"></a> 
</p>

## 📝 Licença

🚧 Em construção... 🚧
