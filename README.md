# Sistema Escolar — Spring Boot

## Primeiro erro:
Dependência do "spring-boot-h2console" não inserida.

## Segundo erro:
Dentro da dependência do h2 tinha algo como "<scope>test</scope>".
Como o driver estava disponível apenas no escopo de testes, ele não estava no classpath da execução normal.

## Terceiro erro:
Dentro da classe "Professor.java", seu atributo id não possui "@GeneratedValue(strategy = GenerationType.IDENTITY)"
Isso serve para o autoincremento, todas as outras entidades possuem.

## Quarto erro:
Na classe "Matriculas.java", o aluno so pode  ter uma matricula (OneToOne), deveria ser "ManyToOne", possibilitando
muitas matriculas para um aluno.

## Quinto erro:
Dentro do meu controller "AlunoController.java", no PUT não possui o "@Transacional" embaixo dele. O PUT é uma transição no banco.

## Sexto erro:
O comando "spring.jpa.hibernate.ddl-auto=none" estava impossibilitando a mudança no Banco, por ser none. Usando o "create-drop" ele altera na hora.

## Sétimo erro:
