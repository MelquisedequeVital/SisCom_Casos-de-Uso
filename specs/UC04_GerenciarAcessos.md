# Caso de Uso: UC04 - Gerenciar Acessos

**Objetivo:** Permitir ao Administrador controlar as permissões e perfis de acesso dos usuários, garantindo que apenas usuários autorizados realizem operações específicas, de acordo com o modelo de privilégios da instituição.

**Requisitos:** [RF004] - Gerenciamento de Acessos; [RNF1001] - Controle de Acesso Baseado em Papéis.

**Atores:** Administrador.

**Condição de entrada:** O Administrador deve estar autenticado e acessar o painel de "Configurações de Usuários" na interface administrativa.

---

### Fluxo Principal

1. O ator acessa a listagem de todos os usuários registrados no sistema.
2. O ator utiliza a busca para localizar o usuário desejado (por nome ou matrícula).
3. O sistema exibe o perfil atual do usuário e as permissões de acesso vinculadas (ex: funcionário, gestor, administrador).
4. O ator altera o perfil de acesso ou adiciona/remove permissões específicas.
5. O ator clica em "Salvar Alterações".
6. O sistema valida a consistência da alteração (garantindo que não fiquemos sem administradores, por exemplo).
7. O sistema atualiza o registro no banco de dados e aplica as novas políticas de controle de acesso (RBAC) para a próxima sessão do usuário.

---

### Fluxos Alternativos

#### FA01 - Suspensão de Acesso
1. O Administrador seleciona a opção "Bloquear Acesso" para um usuário que não faz mais parte da instituição ou que necessita de interdição temporária, impedindo seu login imediato.

---

### Fluxos de Exceção

#### FE01 - Usuário não localizado
1. Se o Administrador buscar um usuário inexistente, o sistema exibe: "Usuário não encontrado na base de dados".

#### FE02 - Conflito de Permissão
1. Caso o Administrador tente atribuir uma permissão inválida ou incompatível, o sistema impede a ação e emite um alerta de "Violação de regra de segurança: Permissão inválida para este perfil".

#### FE03 - Erro de Persistência
1. Se o banco de dados falhar ao salvar as alterações, o sistema exibe: "Erro interno ao atualizar privilégios. As alterações não foram aplicadas."
