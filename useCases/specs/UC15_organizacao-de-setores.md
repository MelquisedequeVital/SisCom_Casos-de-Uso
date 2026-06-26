# UC15 - Cadastro e Organização de Setores

**Objetivo:** Permitir o cadastro, a organização dos setores internos da instituição e o correto roteamento de chamados.  

**Requisitos:** [RNF1007] ,[RF4001] 

**Atores:** Administrador  

**Condição de entrada:** O ator faz login no sistema.  

### Fluxo Principal
1. O ator acessa o menu lateral e clica no item "Departamentos". Ele verifica que a página exibe o título 'Estrutura Organizacional e Setores' e observa uma listagem dos departamentos atuais e um botão destacado "Adicionar Departamento".
2. O ator clica no botão "Adicionar Departamento". O sistema exibe um formulário em tela contendo os seguintes campos vazios: "Nome do Setor" (caixa de texto), "Gestor Vinculado" (menu de seleção listando usuários habilitados) e "Regras de Entrada".
3. O ator digita o nome do novo setor e seleciona o profissional responsável no menu suspenso [A1].
4. O ator configura o campo "Regras de Entrada" marcando caixas de seleção que estabelecem quais palavras-chave ou tags farão com que um ticket seja direcionado automaticamente para aquele setor.
5. O ator clica no botão "Salvar Setor" e o sistema grava os dados exibindo uma notificação flutuante de sucesso.

### Fluxos Alternativos
* **[A1] Definição de Responsabilidade:** No passo 3, ao escolher o gestor na lista, o sistema efetua uma busca interna e assegura em conformidade com o [RNF1007] que aquele profissional não possua duplicidade de cargo em setores concorrentes, travando o registro associado em seu perfil.

### Fluxos de Exceção
* **[E1] Setor Duplicado:** No momento do salvamento (passo 5), se o nome digitado na caixa de texto coincidir exatamente com um departamento existente, o sistema cancela a inserção e emite um texto explicativo em vermelho abaixo do campo: "Setor Duplicado. Já existe um departamento com este nome no sistema."
