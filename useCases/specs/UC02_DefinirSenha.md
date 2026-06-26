# Caso de Uso: UC02 - Definir Senha

**Objetivo:** Permitir que o utilizador realize o cadastro inicial da sua senha de acesso ao sistema de forma segura, após ter a sua identidade validada pela instituição através da API CEHAP.

**Requisitos:** [RF002] - Definição de Senha; [RNF1003] - Criptografia de Dados em Repouso.

**Atores:** Usuário do Sistema.

**Condição de entrada:** O utilizador deve ter passado pela validação de identidade via API CEHAP (no login) e o sistema ter identificado a ausência de uma senha cadastrada na base local.

---

### Fluxo Principal

1. O sistema redireciona o utilizador para a página de "Definição de Senha". O utilizador verifica que o título da página na aba do navegador e no topo da tela é 'Definição de Senha' e observa os seguintes campos: "Nova Senha" (caixa de texto protegida), "Confirmar Senha" (caixa de texto protegida) e a opção/botão "Salvar Senha".  
2. O sistema solicita que o utilizador insira uma nova senha e confirme a digitação exata num segundo campo.
3. O ator preenche os campos e clica no botão "Salvar Senha".
4. O sistema verifica se a senha cumpre os requisitos de complexidade institucional (tamanho mínimo, caracteres especiais, etc.).
5. O sistema verifica se os campos de "Senha" e "Confirmar Senha" são idênticos.
6. O sistema aplica o algoritmo de hash (SHA-512) e processa a Criptografia de Dados em Repouso ([RNF1003]).
7. O sistema armazena a nova senha na base de dados.
8. O sistema exibe uma mensagem de sucesso e redireciona o utilizador para a página inicial, já autenticado.

---

### Fluxos Alternativos

#### FA01 - Alteração de Senha
1. Caso o utilizador precise alterar a senha posteriormente, ele acessa a página de perfil através do menu superior, observa o campo "Senha Atual" e os campos de nova senha, preenche-os seguindo os mesmos critérios de criptografia do fluxo principal e seleciona o botão "Atualizar Senha".

---

### Fluxos de Exceção

#### FE01 - Senhas Divergentes
1. Se o campo de confirmação for diferente do campo de senha, o sistema exibe o erro em vermelho: "As senhas informadas não coincidem" e limpa o campo de confirmação para nova tentativa.

#### FE02 - Senha Fraca
1. Se a senha escolhida não cumprir os requisitos de segurança definidos, o sistema impede o salvamento e exibe um alerta pop-up detalhando os critérios mínimos necessários.

#### FE03 - Erro de Persistência
1. Caso ocorra uma falha na conexão com a base de dados durante o salvamento, o sistema exibe a mensagem de erro: "Erro ao salvar senha. Tente novamente mais tarde."
