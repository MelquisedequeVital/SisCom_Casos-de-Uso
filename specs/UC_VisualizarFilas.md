# Caso de Uso: UCX - Visualizar Filas de Chamados

**Objetivo:** Permitir que funcionários do setor visualizem a organização dos chamados pendentes, facilitando a gestão do fluxo de trabalho e a identificação de demandas urgentes.

**Requisitos:** [RF1003] - Visualização de Filas de Chamados; [RNF1007] - Departamento Responsável.

**Atores:** Usuário Requerido, Gestor.

**Condição de entrada:** O usuário deve estar autenticado e acessar a aba "Filas de Atendimento" no menu principal.

---

### Fluxo Principal

1. O usuário acessa a interface de "Filas de Chamados".
2. O sistema filtra automaticamente os chamados vinculados ao setor do usuário.
3. O sistema exibe os chamados organizados por status (ex: "Em Aberto", "Em Atendimento", "Aguardando Resposta").
4. O usuário pode aplicar filtros de visualização (ex: por nível de urgência, por data de abertura ou por responsável).
5. O sistema atualiza a lista em tempo real para exibir novas demandas ou mudanças de status, utilizando a comunicação via WebSocket ([RNF6001]).

---

### Fluxos Alternativos

#### FA01 - Visualização de Fila Geral (Gestor)
1. O Gestor possui permissão para visualizar as filas de todos os sub-setores do seu departamento, podendo trocar a visualização entre seu próprio setor e a visão global do departamento.

---

### Fluxos de Exceção

#### FE01 - Fila Vazia
1. Se não houver chamados no setor, o sistema exibe: "Nenhum chamado pendente no momento" e um indicador visual de "Fila Limpa".

#### FE02 - Erro de Carga de Dados
1. Caso ocorra uma falha na consulta ao banco de dados, o sistema exibe: "Erro ao carregar as filas de atendimento. Tente atualizar a página."

#### FE03 - Acesso Negado
1. Se o usuário tentar visualizar uma fila de um setor ao qual não pertence e não tiver permissão de Gestor, o sistema exibe: "Acesso restrito: você não possui permissão para visualizar as filas deste departamento."
