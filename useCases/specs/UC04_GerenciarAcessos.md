# Caso de Uso: UC04 - Gerenciar Acessos

**Objetivo:** Permitir ao Administrador controlar as permissões e perfis de acesso dos usuários, garantindo que apenas usuários autorizados realizem operações específicas, de acordo com o modelo de privilégios da instituição.

**Requisitos:** [RF004] - Gerenciamento de Acessos; [RNF1001] - Controle de Acesso Baseado em Papéis.

**Atores:** Administrador.

**Condição de entrada:** O Administrador deve estar autenticado e acessar o painel de "Configurações de Usuários" na interface administrativa.

---

### Fluxo Principal

1. O ator acessa a página de 'Configurações de Usuários'. Ele verifica que o título da página é 'Gerenciamento de Perfis e Acessos' e observa um campo de busca textual seguido pela listagem de usuários.
2. O ator preenche a caixa de busca com o nome ou matrícula do usuário desejado  e clica no ícone de lupa.
3. O sistema atualiza a tabela e exibe o perfil encontrado com as permissões vinculadas. O ator clica no botão "Editar Permissões".
4. O sistema abre uma tela lateral de edição onde o ator observa campos de seleção múltipla (checkboxes ou tags) com as opções de perfil (ex: funcionário, gestor, administrador) e altera as permissões adicionando ou removendo marcações.
5. O ator clica em "Salvar Alterações".
6. O sistema valida a consistência da alteração (garantindo que não fiquemos sem administradores, por exemplo).
7. O sistema atualiza o registro no banco de dados e aplica as novas políticas de controle de acesso (RBAC) para a próxima sessão do usuário.

---

### Fluxos Alternativos

#### FA01 - Suspensão de Acesso
1. No passo 4, na tela lateral de edição, o Administrador localiza o botão vermelho com o rótulo "Bloquear Acesso" e o seleciona para impedir o login imediato de um usuário inativo.

---

### Fluxos de Exceção

#### FE01 - Usuário não localizado
1. Se a busca por nome ou matrícula retornar vazia, o sistema exibe na área da tabela o texto informativo: "Usuário não encontrado na base de dados".

#### FE02 - Conflito de Permissão
1. Caso o Administrador tente salvar uma combinação incompatível de perfis, o sistema bloqueia o envio e emite um banner de alerta: "Violação de regra de segurança: Permissão inválida para este perfil".

#### FE03 - Erro de Persistência
1. Se o banco de dados falhar ao salvar, o sistema exibe uma caixa de diálogo contendo: "Erro interno ao atualizar privilégios. As alterações não foram aplicadas."
