# Caso de Uso: UCX - Login

**Objetivo:** Permitir que o usuário acesse o sistema de forma segura utilizando e-mail institucional e senha.

**Requisitos:** [RF001] - Autenticação de Usuário; [RNF4001] - Integração com API CEHAP; [RNF1003] - Criptografia de Dados em Repouso.

**Atores:** Usuário do Sistema.

**Condição de entrada:** O usuário acessa a página inicial do sistema.

---

### Fluxo Principal

1. O ator acessa a página de login do SisCom. Ele verifica que o título da página no aplicativo e na própria página é ‘Realizar Login’. Ele observa os seguintes campos: “E-mail institucional” e “Senha”, opção: “Entrar”.
2. O ator preenche todos os campos e seleciona o botão para entrar na conta.
3. O sistema valida as credenciais através da integração com a API CEHAP e verifica a integridade dos dados.
4. O sistema concede acesso à plataforma.

---

### Fluxos Alternativos

#### FA01 - Primeiro Acesso
1. Se a API da CEHAP validar o usuário, mas o sistema identificar que ele não possui senha cadastrada, o fluxo é desviado para o caso de uso `Definir Senha`.

---

### Fluxos de Exceção

#### E1 - Campos Obrigatórios ou Credenciais Inválidas
1. O ator tenta entrar sem preencher algum campo obrigatório, ou insere uma senha incorreta/e-mail não reconhecido pela API.
2. O sistema impede o acesso.
3. O sistema exibe uma mensagem de erro informando o problema e solicita uma nova tentativa.
