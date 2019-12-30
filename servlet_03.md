# Servlet 03

## JSTL e Expression Language
- Eliminar scriplets por meio de *expression language*: ```${..}```
- Declaração de importação
- Utilizar biblioteca de *tags* (JSTL), precisando adicionar a lib ao projeto para poder utilizar em ```WEB-INF/lib```
- JSP: JSTL + EL
- JSTL:
 - **Core** - controle de fluxo
 - **Fmt** - formatação/i18n (internacionalização)
 - **Sql** - executar sql
 - **Xml** - gerar XML
- Project Explorer > Web Project Settings > Context Root (trocar nome do contexto), depois adicionar novamente o projeto no Tomcat
- Como o nome do contexto pode variar, utiliza-se a tag ```<c:url />``` dentro do form
- Utilizar *if* da Core para melhorar o JSP da cadastro de empresas

## Redirecionamento

- É possível fazer redirecionamento nos Servlets pelo navegador, ao invés do Servlet para outro Servlet
- Exemplo de uso: acessou documento pelo navegador, mas o documento não existe mais, então o navegador devolve uma resposta
- Utiliza ```response.sendRedirect(...)```
- Quando o redirecionamento é pelo Servidor (*Server Side*), a mesma requisição vai passando pelos Servlets
- Quando é pelo Cliente (*Client Side*), a *request* entra pelo Servlet e o mesmo devolve uma *response* pro navegador (cliente), ou seja, tudo na requisição "morre"
- Para resolver a repetição de requisição (F5), pode-se redirecionar o navegador para uma operação de leitura (logo após ele realizar a escrita)
- Códigos de redirecionamento são da família ```300```
