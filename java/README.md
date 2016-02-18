# Java

## Iniciando um projeto com smaven e Primefaces
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

## Adicionando JPA com Hibernate
Com o projeto maven iniciado siga os seguintes passos:
- botão direito do mouse no projeto > New > Other e na janela que abrir selecione Persistence e na coluna Categories selecione Persistence Unit > next
- Na próxima tela selecione o banco e concluir
- altere o arquivo `nomedoprojeto/Other Sources/persistence.xml` da seguinte forma:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="2.1" xmlns="http://xmlns.jcp.org/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence http://xmlns.jcp.org/xml/ns/persistence/persistence_2_1.xsd">
  <persistence-unit name="nomedoprojetoPU">
    <provider>org.hibernate.ejb.HibernatePersistence</provider>
    <properties>
      <property name="javax.persistence.jdbc.url" value="jdbc:mysql://localhost/bancodedados"/>
      <property name="javax.persistence.jdbc.user" value="usuario"/>
      <property name="javax.persistence.jdbc.password" value="123"/>
      <property name="javax.persistence.jdbc.driver" value="com.mysql.jdbc.Driver"/>
      <property name="hibernate.dialect" value="org.hibernate.dialect.MySQL5Dialect"/>
      <property name="hibernate.show_sql" value="true"/>
      <property name="hibernate.format_sql" value="true"/>
      <property name="hibernate.hbm2ddl.auto" value="create"/>
    </properties>
  </persistence-unit>
</persistence>
```
- adicione a seguinte dependência no pom.xml
```xml
<dependency>
    <groupId>org.hibernate</groupId>
    <artifactId>hibernate-core</artifactId>
    <version>5.0.1.Final</version>
</dependency>
<dependency>
    <groupId>org.hibernate</groupId>
    <artifactId>hibernate-entitymanager</artifactId>
    <version>5.0.1.Final</version>
</dependency>
<dependency>
    <groupId>org.hibernate.javax.persistence</groupId>
    <artifactId>hibernate-jpa-2.1-api</artifactId>
    <version>1.0.0.Final</version>
</dependency>
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>5.0.8</version>
</dependency>        
```
- crie a classe JpaUtil

```java
package br.com.maven.mavendelete.util;

import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.Persistence;

public class JpaUtil {
    private static EntityManagerFactory factory;

    static {
        factory = Persistence.createEntityManagerFactory("nomedoprojetoPU");
    }

    public static EntityManager getEntityManager() {
        return factory.createEntityManager();
    }

    public static void  close() {
        factory.close();
    }

}

```
> Não esqueça de trocar nomedoprojetoPU pela Unidade de persistência do arquivo `persistence.xml`

Use as seguintes classes para testar o seu projeto:
```java
//Usuario.java
package br.com.maven.delete.model;

import java.io.Serializable;
import java.util.Objects;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.Id;

@Entity
public class Usuario implements Serializable {

    private Long id;
    private String nome;
    private String endereco;
    private Integer idade;

    @Id
    @GeneratedValue
    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }


    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getEndereco() {
        return endereco;
    }

    public void setEndereco(String endereco) {
        this.endereco = endereco;
    }

    public Integer getIdade() {
        return idade;
    }

    public void setIdade(Integer idade) {
        this.idade = idade;
    }

    @Override
    public int hashCode() {
        int hash = 5;
        hash = 97 * hash + Objects.hashCode(this.id);
        return hash;
    }

    @Override
    public boolean equals(Object obj) {
        if (obj == null) {
            return false;
        }
        if (getClass() != obj.getClass()) {
            return false;
        }
        final Usuario other = (Usuario) obj;
        if (!Objects.equals(this.id, other.id)) {
            return false;
        }
        return true;
    }
}

```
```java
//Teste.java
package br.com.maven.delete.teste;

import br.com.maven.delete.model.Usuario;
import br.com.maven.delete.util.JpaUtil;
import javax.persistence.EntityManager;
import javax.persistence.EntityTransaction;

public class Teste {
    public static void main(String[] args) {
        EntityManager manager = JpaUtil.getEntityManager();
        EntityTransaction tx = manager.getTransaction();
        tx.begin();

        Usuario usuario = new Usuario();
        usuario.setNome("Adriano");
        usuario.setEndereco("Rua Rondônia");
        usuario.setIdade(31);

        manager.persist(usuario);

        tx.commit();
        manager.close();
        JpaUtil.close();
    }

}

```
Para testar pressione `SHIFT + f6`
