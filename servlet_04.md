# Servlet 04

## Deploy da Aplicação

### web.xml
- Pode definir arquivo que é automaticamente carregado em ```<welcome-file></welcome-file>```
 - Se carregar só o projeto ele chama esse primeiro arquivo
- Pode configurar anotações/mapeamentos
 ```xml
    <servlet>
      <servlet-name>nomeAssociacao1</servlet-name>
      <servlet-class>br.com.empresa.gerenciador.OiMundoServlet</servlet-class>
    </servlet>
    <servlet-mapping>
      <servlet-name>nomeAssociacao1</servlet-name>
      <url-pattern>/ola<url-pattern>
    </servlet-mapping>
  ```
- Pode ter mais de um mapeamento pro mesmo servlet
  ```java
  @WebServlet(urlPatterns= {"/listaEmpresas", "/empresas"})
  public class ListaEmpresasServlet extends HttpServlet {...}
  ```
- Definir tempo de sessão logado
- Configurações gerais da aplicação

### Inversão de Controle (IoC)
- Servlet é um objeto, então o Tomcat quem faz essa instância e os mantém, é o intermediário entre o navegador e os objetos
 - Assim que alguém chama o mapeamento associado ao Servlet ele o cria (apenas uma vez) e chama (quantas necessárias)
- Mantém apenas uma instância na memória de cada Servlet (*Singleton = escopo que vive pra sempre*)
- IoC significa que não é meu ```main()``` quem instancia meu objeto, é o Tomcat quem faz isso - nós só escrevemos a classe, quem cuida do cabeçalho e outros detalhes do protocolo HTTP é o Tomcat
- Não precisamos implementar regras de negócio
- O servidor poderia cuidar da transação com o banco de dados, regras de segurança, etc
- Pode alterar o comportamento da Servlet com:
```java
@WebServlet(urlPatterns="/oi", loadOnStartup=1)
```

### O que é Deploy
- Passar de desenvolvimento para produção
- Colocar seu código e colocar em outra máquina/instância para verificar o funcionamento (colocar em produção)
- No caso, criar uma nova instância do Tomcat e executar a aplicação
 - Extrair novamente o arquivo do Tomcat (excluindo o antigo)
 - Export > WAR (pode renomear para .zip)
 - Joga o .war dentro da pasta webaps dentro da pasta do Tomcat
- Projeto > Java Compiler > Mudar versão se necessário
- War é o zip de projetos Java Web, Jar é o zip de projetos comuns
