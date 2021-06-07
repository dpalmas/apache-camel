<h1 align="center">
  Apache Camel
</h1>

<p align="center">Curso de Apache Camel</a>
</p>

<p align="center">
  
  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/dpalmas/apache-camel?color=0000FF">

  <img alt="License" src="https://img.shields.io/github/license/dpalmas/apache-camel?color=0000FF&logo=MIT">
  
  <a href="https://github.com/dpalmas/apache-camel/commits/master">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/dpalmas/apache-camel?color=0000FF">
  </a>
</p>

### A complexidade da integração

Atualmente é difícil encontrar uma aplicação que funcione de maneira isolada, sem depender de nenhuma outra funcionalidade externa. Queremos reaproveitar funcionalidades já existentes, que é a ideia principal do SOA. Em tempos de Cloud e SOA, a integração entre aplicações se tornou muito comum e faz parte do cotidiano do desenvolvedor.

### Boas práticas: Padrões de integração

Diante da necessidade de integrar aplicações, foram identificados alguns padrões de como resolver os problemas mais comuns na integração. Os [Enterprise Integration Patterns](http://www.enterpriseintegrationpatterns.com/) definem uma série de boas práticas que foram documentadas no livro com o mesmo nome, que descreve as vantagens e desvantagens de cada padrão e define um vocabulário comum a ser seguido.

### O que é um framework de integração?

O Apache Camel, como framework de integração, implementa a maioria dos padrões de integração. Um framework de integração ajuda a diminuir a complexidade e o impacto dessas integrações. Em vez de escrever código de integração na mão, usamos componentes para isso.

### Roteamento entre endpoints com Apache Camel

Essencialmente, Camel é um roteador (routing engine), ou seja o Camel roteia os dados entre dois endpoints. Um endpoint é um serviço web ou um banco de dados, podendo ser um arquivo ou file JMS. Em geral, é um ponto onde pegamos ou enviamos dados. A tarefa do desenvolvedor é configurar, por meio de um Builder, os endpoints e as regras de roteamento. O desenvolvedor decide de onde vem as mensagens (from()), para onde enviar (to()) e o que fazer com a mensagem no meio desse processo (mediation engine).

### O que é Camel?

**1° Qual frase abaixo não caracteriza o Camel? :pencil:**

- [ ] Essencialmente o Apache Camel é um roteador (routing engine).

- [ ] Apache Camel ajuda a diminuir a complexidade e o impacto nas integrações entre sistemas.

- [ ] Apache Camel implementa a maioria dos padrões de integração, sempre seguindo boas práticas.

:white_check_mark: Apache Camel implementa os padrões de web services, com SOAP e WSDL.

### Construindo a rota

**2° O que devemos colocar no lugar de //aqui, para criar uma nova rota? :pencil:**

```
public class RotaPedidos {

    public static void main(String[] args) throws Exception {

        CamelContext context = new DefaultCamelContext();
        context.addRoutes( 
            //aqui
        );

        context.start(); 
        Thread.sleep(20000); 
        context.stop(); 
    }    
}
```

:white_check_mark: A
```
new RouteBuilder() {

  @Override
  public void configure() throws Exception {
       from("file:pedidos"). 
       to("file:saida");
  }
}
```

- [ ] B
```
new RouteBuilder() {

  @Override
  public void config() {
       from("file:pedidos"). 
       to("file:saida");
  }
}
```

- [ ] C
```
new Builder() {

  @Override
  public void configure() throws Exception {
       from("file:pedidos"). 
       to("file:saida");
  }
}
```

- [ ] D
```
new RoutesBuilder() {

  @Override
  public void configure() throws Exception {
       from("file:pedidos"). 
       to("file:saida");
  }
}
```

### Camel Expression Language

**3° Qual é a sintaxe correta para acessar a id da mensagem pela Camel Expression Language? :pencil:**

- [ ] {{id}}
- [ ] @id
- [ ] #{id}<br>
:white_check_mark: ${id}
- [ ] $id

### Para saber mais: Estilos de integração

**4° Qual estilo de integração estamos usando? :pencil:**

- [ ] Shared Database

:white_check_mark: File Transfer

- [ ] Remote Procedure Call

- [ ] Messaging

### Marshal e Unmarshal

**5° O que significa Marshal e Unmarshal no contexto de integração de sistemas? :pencil:**

- [ ] O processo de gravação de dados de um objeto no banco é chamado de marshal. O processo contrário é chamado unmarshal.

- [ ] O processo de alteração de dados para aplicar uma série de cálculos é marshal. Desfazer essas alterações é chamado de unmarshal.

:white_check_mark: O processo de transformação de dados em memória em um outro formato é chamado de marshal. O contrário é chamado de unmarshal.

- [ ] O processo de otimização de dados de um format
