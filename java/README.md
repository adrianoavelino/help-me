# Java

## Iniciando um projeto maven e Primefaces
- `Ctrl + shift + N`
- selecione a categoria Maven > Web Application
- dê um nome ao projeto > next > finish
- adicione o seguinte conteúdo dentro do seu arquivo pom.xml, na tag `<dependencies>`:

```xml
<dependency>
    <groupId>org.primefaces</groupId>
    <artifactId>primefaces</artifactId>
    <version>5.3</version>
</dependency>
<dependency>
    <groupId>javax</groupId>
    <artifactId>javaee-web-api</artifactId>
    <version>7.0</version>
    <scope>provided</scope>
</dependency>
```
> Obs: as dependências podem ser encontradas em: [http://search.maven.org/](http://search.maven.org/)


- Botão direito do mouse em cima do projeto > propriedades
- com a propriedades aberta acesse a categoria frameworks e adicione Java Server Faces e na aba configuration altere a url `/faces/*` para `*.jsf`
- crie um arquivo na pasta Web Pages com o seguinte conteúdo:

```xml
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:h="http://java.sun.com/jsf/html"
      xmlns:f="http://java.sun.com/jsf/core"
      xmlns:ui="http://java.sun.com/jsf/facelets"
      xmlns:p="http://primefaces.org/ui">
    <h:head>
        <title> Teste </title>
    </h:head>
    <h:body>
        <p:editor></p:editor>
    </h:body>
</html>

```
