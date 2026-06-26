# Caso de Uso: UC06 - Abrir Chamado

**Objetivo:** Permitir que o usuário requerente formalize uma demanda de atendimento.

**Requisitos:** [RF1001] - Abertura de Chamados;

**Atores:** Usuário Requerente.

**Condição de entrada:** O usuário seleciona a opção "Novo Chamado" no dashboard.

---

### Fluxo Principal

1. O ator clica na opção “Abrir Chamado” no menu de atalhos e é redirecionado. Ele verifica que o título da página é 'Novo Atendimento - Abertura de Chamado' e observa um formulário com os seguintes campos: "Motivo da Solicitação" (caixa de texto curta), "Urgência" (menu de seleção), "Setor Destino" (menu de seleção), "Mensagem Inicial" (caixa de texto longa) e o botão "Enviar Chamado".
2. O ator preenche todos os campos obrigatórios e seleciona o botão para enviar "Enviar Chamado".
3. O sistema registra o chamado na base de dados com o status inicial de "Aberto".
4. O sistema executa o algoritmo de Triagem e Direcionamento Automático ([RF1002]), identificando o atendente do setor selecionado que possua menor carga de trabalho no momento.
5. O sistema vincula a demanda ao atendente com menor carga, dispara uma notificação em tempo real na conta deste atendente e abre automaticamente a interface de conversação em chat para o início do atendimento.

---

### Fluxos Alternativos

#### FA01 - Seleção de Setor com Múltiplos Atendentes
1. Caso o sistema identifique dois atendentes empatados com a mesma carga de trabalho mínima no passo 4, ele executa o critério de rodízio (round-robin) para definir o responsável final.
---

### Fluxos de Exceção

#### FE01 - Setor Sem Atendentes Online
1. Se o algoritmo de triagem constatar que não há funcionários logados no setor escolhido, o sistema grava o chamado com o status de "Aguardando Atendente" e exibe uma caixa de texto amarela informando: "No momento, não há atendentes online neste setor. Sua solicitação foi encaminhada para a fila de espera."

#### FE02 - Erro de Validação de Campos
1. Se o usuário tentar enviar o formulário sem preencher campos obrigatórios (como "Motivo" ou "Setor"), o sistema impede o envio e destaca os campos necessários.

#### FE03 - Falha de Conexão durante o Envio
1. Caso a rede caia no momento do clique de envio, o sistema retém os dados localmente (através da arquitetura offline PWA) e exibe um ícone no rodapé indicando que a submissão será concluída ao restabelecer o sinal.
