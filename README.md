# Projeto Envio de E-mail com Java

## 1. Descrição do Projeto

Este projeto é uma aplicação Java projetada para simplificar o envio de e-mails, tanto em texto simples quanto em HTML, e com a capacidade de anexar arquivos PDF. É ideal para notificações automáticas, envio de documentos e outras comunicações corporativas ou pessoais que requerem envio programático de emails.

## 2. Explicação de cada arquivo encontrado no repositório

### `ObjetoEnviaEmail.java`
Este arquivo Java é a peça central do projeto. Ele define uma classe `ObjetoEnviaEmail` que encapsula todas as funcionalidades necessárias para enviar e-mails usando a biblioteca `javax.mail`. A classe suporta autenticação SMTP para enviar e-mails e pode ser configurada para trabalhar com diferentes servidores de e-mail (como configurado, está pré-definido para o Gmail).

#### Principais Métodos:
- **construtor `ObjetoEnviaEmail(String listaDestinatario, String nomeRemetente, String assuntoEmail, String textoEmail)`**: permite inicializar um objeto com os destinatários do email, o nome do remetente, o assunto e o corpo do email.
- **`enviarEmail(boolean envioHtml)`**: envia um email, que pode ser em formato de texto puro ou HTML, dependendo do valor do parâmetro `envioHtml`.
- **`enviarEmailAnexo(boolean envioHtml)`**: envia um email com anexos. Os anexos são gerados usando o método `simuladorDePDF()`. A função permite enviar múltiplos arquivos e suporta tanto texto quanto HTML para o corpo do email.
- **`simuladorDePDF()`**: gera um arquivo PDF de exemplo para ser usado como anexo nos e-mails.

### Arquivos adicionais necessários
- **Biblioteca JavaMail (`javax.mail`)**: necessária para manipulação e envio de mensagens de e-mail.
- **Biblioteca iText (`com.itextpdf.text`)**: utilizada para criar documentos PDF que podem ser anexados aos emails.

## 3. Lista de todos os métodos do projeto e suas funcionalidades

### Métodos em `ObjetoEnviaEmail`

- **`enviarEmail()`**: 
  - **URL**: `/enviarPlain` (assumindo uma interface de API REST)
  - **Método**: POST
  - **Funcionalidade**: Envio de email na forma de texto puro ou HTML sem anexos. Recebe parâmetros para detalhes do remetente, destinatários, assunto e conteúdo do e-mail.

- **`enviarEmailAnexo()`**:
  - **URL**: `/enviarComAnexo` (assumindo uma interface de API REST)
  - **Método**: POST
  - **Funcionalidade**: Permite o envio de emails com anexos PDF gerados dinamicamente. Suporta tanto emails em HTML quanto em texto puro e inclui detalhamento semelhante ao método `enviarEmail()`.

## Nota
Este README assume que a gestão de chamadas REST para os métodos da classe `ObjetoEnviaEmail` está implementada ou será implementada, uma vez que os detalhes específicos de implementação REST não foram fornecidos no código-fonte Java provido. A configuração do servidor SMTP, nomes de usuário e senhas devem ser configuradas de acordo com o ambiente de produção para garantir a segurança e a funcionalidade adequada.
