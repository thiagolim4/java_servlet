# Servlet 05

## Projeto Web com padrão MVC

- Única Servlet para agir como Controller
- Navegador envia requisição com parâmetro contendo o tipo de ação a ser executada pela Servlet
 - Pra cada tipo de ação, usa uma classe
 - Servlet recebe a requisição e delega as ações (não contém a lógica)
 - Uma abordagem de mercado de mapeamento é que o controlador recebe qualquer requisição para qualquer *URL*, através do mapeamento ```/```:
 ```java
 @WebServlet("/")
 ```
## Esconder JSP's
- Não devem ser chamados diretamente pelo navegador, sempre passar pelo Controlador/Servlet
 - Com isso poderia ocorrer alguma funcionalidade não prevista (pode pular etapas de execução)
- Colocar todos dentro da pasta ```WEB-INF```
 - Cria subdiretório ```View```, assim não consegue chamar o JSP diretamente pelo navegador
- Tomcat "esconde" a pasta ```WEB-INF``` e não permite que alguma requisição tenha acesso, pois há arquivos como o ```web.xml``` e os nossos JARs dentro desse diretório

## Boas práticas
- Controlador não deve ficar com diversos ```if```
- Os nomes das classes seguem as ações
- Criar um objeto "universal" e depois diferenciar na ação (e não fazer um objeto para cada tipo de ação)
 - Pra diferenciar esse objeto utiliza o nome da classe com o
```java
Class classeMemoria = Class.forName(nomeDaClasse);
Object objeto = classeMemoria.newInstance();
```
 - Essa classe usa a ```API Reflection```
 - Utiliza uma ```interface``` pra uniformizar as ações

### Arquitetura MVC:
  - Controller: Servlet única que chama as outras classes de execução (e essas classes interagem com o Modelo)
  - Model: modelo do objeto, encapsula as regras de negócio
  - View: JSP que é chamado pelo Servlet central, nunca pelas classes de execução/lógica
