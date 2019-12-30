# Servlet 02

- No projeto (pacote) é possível dar New > Servlet
- Criar nova Servlet sobrescrevendo o ```service()```
- Para passar parâmetros para o Servlet, pode passar pela URL (requisição):
 - Começa com ```?``` logo depois do nome
 - Caracter ```&``` separa parâmetros
 - ```localhost:8080/gerenciador/novaEmpresa?nome=valor&cnpj=valor```
- Para receber a requisição, utiliza-se ```getParameter()```
- Sempre que tem requisição, tem o método da requisição:
 - GET: envia os parâmetros na URL, pensado para acessar recurso
 - POST: esconde os parâmetros no corpo da mesma, não deixando visível, pensado para alterar ou criar algum recurso
- Essas requisições podem ser feitas via formulário html
- Pode sobrescerver o ```service()``` com ```doPost()``` para atender somente requisições POST (o mesmo para GET)
- Se criar uma classe de persistência, os dados dela ficarão no Tomcat somente enquanto ele executa (se o mesmo for reiniciado perde-se os dados)


## JSP

- Transforma a página HTML numa página dinâmica pra poder tratar com o HTML e código junto (Scriptlet)
 - Código: ```<% codigo %>```
 - Esse código é interpretado no servidor e executado no servidor antes de enviar a página (resposta)
- Requisição chega no servidor, e o Servlet responsável chama o JSP e repassa esse requisição pra ele
- No JSP é possível pegar atributos da requisição e trabalhar com os mesmos
