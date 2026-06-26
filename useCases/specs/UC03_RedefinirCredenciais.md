# Caso de Uso: UC03 - Redefinir Credenciais

**Objetivo:** Permitir que o Administrador resete as credenciais de acesso de um usuário, garantindo a recuperação de conta ou a aplicação de medidas de segurança.

**Requisitos:** [RF005] - Redefinição de Credenciais; [RNF1003] - Criptografia de Dados em Repouso.

**Atores:** Administrador.

**Condição de entrada:** O Administrador deve estar autenticado e acessar a interface de "Gestão de Usuários" para localizar o perfil do usuário alvo.


---

### Fluxo Principal

1. O Administrador acessa o menu administrativo e seleciona a opção 'Gestão de Usuários'. Ele verifica que a página exibe uma listagem de todos os usuários registrados e localiza o usuário alvo na tabela.
2. Na coluna de ações do painel do usuário correspondente, o Administrador seleciona o botão/link "Redefinir Credenciais".
3. O sistema abre uma janela sobreposta (modal) na tela. O Administrador observa o título 'Confirmar Ação' e os botões: "Confirmar Redefinição" e "Cancelar".
4. O Administrador seleciona o botão "Confirmar Redefinição".
5. O sistema gera um estado de "Senha Pendente" no registro do usuário no banco de dados.
6. O sistema comunica ao usuário (via e-mail institucional ou aviso na próxima tentativa de login) que suas credenciais foram redefinidas.
7. Na próxima autenticação, o sistema obriga o usuário a passar pelo caso de uso `Definir Senha`.

---

### Fluxos Alternativos

#### FA01 - Bloqueio após Redefinição
1. No passo 3, o Administrador observa também uma caixa de seleção (checkbox) com o rótulo "Bloquear Acesso Temporariamente". Ele marca essa opção antes de confirmar, fazendo com que o sistema bloqueie o acesso até liberação manual.

---

### Fluxos de Exceção

#### FE01 - Permissão Negada
1. Se o Administrador tentar redefinir as credenciais de um usuário com privilégios superiores (ex: outro Administrador), o sistema bloqueia a ação e exibe um alerta flutuante: "Permissão negada para redefinir credenciais de superusuário".

#### FE02 - Erro de Persistência
1. Se a operação não for gravada no banco de dados, o sistema exibe a mensagem no rodapé: "Erro ao processar redefinição. Tente novamente."
