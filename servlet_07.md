# Servlet 07

## Web Services

- Estrutura do projeto web no mercado troca o controlador
 - **Controlador**: Mais sofisticados, ajudam a ler, converter e validar os parâmetros, além de popular o modelo (Spring MVC)
 - **Modelo**: JDBC puro + SQL, JPA + Hibernate
 - **View**: JSP, jQuery (para fazer método AJAX), tags
 - Controlador não devolver somente um HTML, mas sim os dados separados (JSON, XML)
 - Existem bibliotecas (frameworks) JavaScript que fazer o MVC dentro do próprio navegador, como *Angular*, *React* e *Vue.js*
  - Elas precisam dos dados em formato JSON ou XML pois não consomem HTML

## JSON
- Notação para definir um objeto java
- Recebe a lista e gera um JSON
- Usa uma biblioteca pronta pra fazer isso
 - GSON: biblioteca do Google
- Precisa definir o tipo da ```response``` com ```setContentType```

## XML
- Biblioteca específica pra devolver xml, do mesmo modo que o JSON

## Cliente Web Service
- Faz uma classe HttpCliente da Apache para simular um cliente
- Essa classe faz uma requisição pro servidor e recebe a resposta
 - Pode definir um ```header``` para o cabeçalho para o tipo de arquivo que quer receber
 - O servidor deve tratar isso
