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

## Início Projeto Web
- New > Dynamic Web Project
- New Server > Apache Tomcat (seleciona o local de instalação no computador)
- Target Runtime > Apache Tomcat
- Conext Root: nome do projeto, é como ele é chamado na URL
- Content Directory: WebContent = arquivos relacionados a web serão armazenados nesse diretório
- Generate web.xml deployment descriptor: arquivo de configuração
- Vai no Server adicionado > Add and Remove > Add o projeto no Tomcat
 - Agora o Tomcat conhece o projeto, e se rodar o servidor ele vai tomar conta do projeto
- WebContent > New File .html (bem-vindo)
- Se mudar no endereço da URL:
 - localhost:8080/projeto/bem-vindo.html

## Servlet
- Tomcat: play > inicia uma máquina virtual que requer uma classe com o método ```main```. O Tomcat é um método ```main``` que sobe um servidor com várias classes e executa diferentes ações
- Navegador realiza requisição para o Tomcat por meio do HTTP
 - HTTP funciona na dinâmica requisição e resposta
- Reconhece a requisição com o projeto, e captura a página web para devolver
- Servlet: objeto especial que vai executar para gerar a resposta, eu uso HTTP pra chamar o Servlet
 - Atua como um "mini servidor", sendo chamado por HTTP e gerando a resposta dinâmica
 - Quando o Tomcat recebe a requisição do navegador com relação aos dados do projeto gerenciador, ao abrirmos a página não estamos mais lidando com um arquivo, mas com um Servlet
 - Acesso:
 ``protocolo://ip:porta/contexto/recurso
 ``
```
 http://localhost:8080/gerenciador/bem-vindo.html
 ```

### Projeto Primeiro Servlet
 - Classe extender de HttpServlet
 - Anotação para modificar nome da servlet (mapea ela na URL)
 - Método service()
  - Usa PrintWriter para ter objeto que devolve caracteres/texto e escreve HTML (no fluxo do navegador)
 - Executando o Tomcat, ele fica ativo com base na máquina virtual, lê o projeto e o Servlet
