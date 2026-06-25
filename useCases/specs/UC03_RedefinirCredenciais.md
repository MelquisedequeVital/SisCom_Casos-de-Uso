# Caso de Uso: UC03 - Redefinir Credenciais

**Objetivo:** Permitir que o Administrador resete as credenciais de acesso de um usuário, garantindo a recuperação de conta ou a aplicação de medidas de segurança.

**Requisitos:** [RF005] - Redefinição de Credenciais; [RNF1003] - Criptografia de Dados em Repouso.

**Atores:** Administrador.

**Condição de entrada:** O Administrador deve estar autenticado e acessar a interface de "Gestão de Usuários" para localizar o perfil do usuário alvo.


---

### Fluxo Principal

1. O Administrador localiza o usuário na listagem do sistema.
2. O Administrador seleciona a opção "Redefinir Credenciais" no painel do usuário.
3. O sistema solicita a confirmação da ação.
4. O Administrador confirma a redefinição.
5. O sistema gera um estado de "Senha Pendente" no registro do usuário.
6. O sistema comunica ao usuário (via e-mail institucional ou aviso na próxima tentativa de login) que suas credenciais foram redefinidas.
7. Na próxima autenticação, o sistema obriga o usuário a passar pelo caso de uso `Definir Senha`.

---

### Fluxos Alternativos

#### FA01 - Bloqueio após Redefinição
1. O Administrador pode optar por, além de redefinir a senha, bloquear temporariamente o acesso do usuário até que uma nova senha seja definida pessoalmente ou por outro canal de segurança.

---

### Fluxos de Exceção

#### FE01 - Permissão Negada
1. Se o Administrador tentar redefinir as credenciais de um usuário com privilégios superiores (ex: outro Administrador), o sistema bloqueia a ação e exibe: "Permissão negada para redefinir credenciais de superusuário".

#### FE02 - Erro de Persistência
1. Se a operação não for gravada no banco de dados, o sistema exibe: "Erro ao processar redefinição. Tente novamente."
