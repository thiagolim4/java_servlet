# Servlet 06

## Autenticação
- Alterar o modelo para ter a representação do Usuário
- É possível definir regras de acesso dentro do ```web.xml``` com o ```JAAS - API``` (*Java Autenthication and Authorization Service*)

## Sessão
- Joga o usuário que acabou de fazer Login dentro da requisição (```setAttribute()```), no entanto, se depois disso for pra outra ação, esse usuário é perdido, por isso é necessário o uso de ```Session```
- Quando o Tomcat recebe uma nova requisição, gerará um ID
 - O ID fica salvo no cookie de nome ```JSessionID```
- SessionId identifica o navegador para o Tomcat saber que se comunica com o mesmo navegador através de diferentes requisições
- Cookie é um arquivo de texto que o servidor pode criar e associar à requisição
 - Cria um objeto ```HttpSession``` com o número do cookie associado
 - Cria esse objeto no momento do login:
 ```java
 HttpSession sessao = request.getSession();
 sessao.setAttribute("usuLogado", usuario);
 ```
- Em cada página que necessita de permissão, pega o ```HttpSession``` (se não existe ele vai criar uma) e verifica se o atributo de "usuárioLogado" existe
- No Logout é só remover o atributo da Session ou então fazer ```sessao.invalidate()```, que destrói a sessão junto com o cookie (id)
- Utiliza uma flag pra verificar se a página é protegida ou não, se for, redireciona pro começo (Login)
- Tempo de timeout é configurável no ```web.xml```:
```xml
<session-config>
    <!-- 10 min -->
    <session-timeout>10</session-timeout>
</session-config>
```

## Filtro
 - Semelhante a um servlet, filtra as requisições
 - Consegue parar a execução de uma requisição de usuário
 - Mapea a Servlet Controller e o Filtro pro mesmo endereço, assim o Filtro consegue filtrar todas as requisições pra ela (passa sempre pro ele)
  - Usa o parâmetro ```FilterChain``` para mandar a requisição para frente

## Deploy

- Executar a aplicação em outro servidor, e não precisa trocar a implementação: como segue os padrões Servlet, é possível executar em outro servidor Servlet (como o Jetty)
- O servidor faz a implementação do Http, objetos, etc
