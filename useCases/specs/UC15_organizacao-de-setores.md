# UC15 - Cadastro e Organização de Setores

**Objetivo:** Permitir o cadastro, a organização dos setores internos da instituição e o correto roteamento de chamados.  

**Requisitos:** [RNF1007] ,[RF4001] 

**Atores:** Administrador  

**Condição de entrada:** O ator faz login no sistema.  

### Fluxo Principal
1. O ator acessa o menu de "Departamentos" no sistema.
2. O ator clica no botão "Adicionar Departamento".
3. O ator preenche as informações do novo departamento e designa um gestor responsável **[A1]**.
4. O ator configura as regras de roteamento de chamados para que os tickets sejam direcionados automaticamente para aquele setor.
5. O ator salva as informações e o sistema confirma a criação.

### Fluxos Alternativos
* **[A1] Definição de Responsabilidade:** No passo 3 do fluxo principal, ao vincular um gestor, o administrador garante que o cadastro deste usuário fique guardado e atrelado ao seu devido setor de responsabilidade, respeitando as regras estabelecidas no [RNF1007].

### Fluxos de Exceção
* **[E1] Setor Duplicado:** No passo 5 do fluxo principal, se o ator tentar salvar um setor com um nome que já existe no sistema, uma mensagem de erro é exibida informando a duplicidade e solicitando a alteração do nome.
