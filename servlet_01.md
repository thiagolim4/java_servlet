# Servlet 01

- Necessita:
 - Java 8 ou 9
 - JRE ou JDK (possui mais documentação)
 - Apache Tomcat (servidor)

## Iniciando Tomcat
- Tomcat é um servidor Web que sabe trabalhar com o protocolo HTTP, sendo feito puramente em Java e dinâmico
- Usar na IDE o Java EE
- Eclipse: Define a New Server > Selecionar Versão > Next > Pasta do Tomcat
- Depois que o servidor está no ar, preciso do protocolo HTTP para acessar o servidor
 - http://localhost:8080
 - Digitando o endereço no navegador, o mesmo fará uma requisição para o servidor Tomcat, que devolve com uma página de erro 404
 - Tendo o IP da máquina que possui o Tomcat, podemos fazer a requisição
- Protocolo HTTP usa o TCP/IP, se não for definida uma porta ele utiliza a padrão (80)

## Projeto Web
- New > Dynamic Web Project
- Target Runtime > Apache Tomcat
