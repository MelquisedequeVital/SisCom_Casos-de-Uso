# Caso de Uso: UC07 - Visualizar Filas de Chamados

**Objetivo:** Permitir que funcionários do setor visualizem a organização dos chamados pendentes, facilitando a gestão do fluxo de trabalho e a identificação de demandas urgentes.

**Requisitos:** [RF1003] - Visualização de Filas de Chamados; [RNF1007] - Departamento Responsável.

**Atores:** Usuário Requerido, Gestor.

**Condição de entrada:** O usuário deve estar autenticado e acessar a aba "Filas de Atendimento" no menu principal.

---

### Fluxo Principal

1. O usuário clica na opção "Filas de Atendimento" no menu de navegação. Ele verifica que a página se chama 'Painel de Gerenciamento de Filas' e observa três colunas organizadoras (Kanban ou listagem) baseadas em status: "Em Aberto", "Em Atendimento" e "Aguardando Resposta". Na área superior, ele nota opções de filtros por "Urgência" e "Responsável".
2. O sistema aplica o filtro automático de contexto exibindo apenas os chamados atrelados ao setor de lotação daquele usuário autenticado.
3. O usuário pode clicar nos menus de seleção superior para aplicar filtros específicos de refinamento visual (ex: exibir apenas chamados de Alta Urgência).
4. O sistema mantém a listagem atualizada e síncrona através de conexões WebSocket ([RNF6001]), adicionando novos blocos ou movendo os chamados em tempo real na tela sem necessidade de recarregar a página.

---

### Fluxos Alternativos

#### FA01 - Visualização de Fila Geral (Gestor)
1. Caso o sistema identifique que o usuário possui o perfil de 'Gestor', ele exibe no topo um campo de seleção adicional chamado "Escolher Subsetor". O gestor pode alternar esse campo para visualizar a fila de qualquer área do seu departamento ou selecionar a opção "Visão Global".
---

### Fluxos de Exceção

#### FE01 - Fila Vazia
1. Se não houver nenhum ticket ativo no setor, o sistema limpa as tabelas e renderiza de forma centralizada uma ilustração acompanhada do texto: "Nenhum chamado pendente no momento - Fila Limpa".

#### FE02 - Erro de Carga de Dados
1. Havendo indisponibilidade na busca dos registros, as tabelas não são carregadas e o sistema exibe um banner vermelho fixo: "Erro ao carregar as filas de atendimento. Tente atualizar a página."

#### FE03 - Acesso Negado
1. Se um usuário tentar acessar diretamente via URL uma fila fora de seu escopo e sem as credenciais adequadas, o sistema interrompe o carregamento e mostra a página de aviso: "Acesso restrito: você não possui permissão para visualizar as filas deste departamento."
