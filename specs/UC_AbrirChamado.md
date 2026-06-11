# Caso de Uso: UCX - Abrir Chamado

**Objetivo:** Permitir que o usuário requerente formalize uma demanda de atendimento.
**Requisitos:** [RF1001] - Abertura de Chamados;
**Atores:** Usuário Requerente.
**Condição de entrada:** O usuário seleciona a opção "Novo Chamado" no dashboard.

---

### Fluxo Principal

1. O ator clica na opção “Abrir Chamado” e observa os seguintes campos: motivo da solicitação, urgência, setor destino e mensagem inicial.
2. O ator preenche todos os campos e seleciona o botão para enviar.
3. O sistema registra o chamado na base de dados com o status "Aberto".
4. O sistema executa o algoritmo de Triagem e Direcionamento Automático ([RF1002]), identificando o atendente do setor selecionado que possua menor carga de trabalho no momento.
5. O sistema vincula o chamado ao atendente identificado e notifica-o em tempo real e abre a interface de chat vinculada ao chamado para que o diálogo inicie.

---

### Fluxos Alternativos

#### FA01 - Seleção de Setor com Múltiplos Atendentes
1. Caso existam dois atendentes com a mesma carga horária mínima, o sistema aplica o critério de round-robin (rodízio) para distribuir a demanda de forma equilibrada.

---

### Fluxos de Exceção

#### FE01 - Setor Sem Atendentes Online
1. Se o algoritmo de triagem não localizar nenhum atendente disponível no setor escolhido, o sistema mantém o chamado em uma fila de espera ("Aguardando Atendente") e emite um alerta para o usuário: "No momento, não há atendentes online neste setor. Sua solicitação foi encaminhada para a fila de espera."

#### FE02 - Erro de Validação de Campos
1. Se o usuário tentar enviar o formulário sem preencher campos obrigatórios (como "Motivo" ou "Setor"), o sistema impede o envio e destaca os campos necessários.

#### FE03 - Falha de Conexão durante o Envio
1. Caso a conexão caia no momento da submissão, o sistema salva os dados temporariamente (conforme a lógica de PWA/Offline) e tenta realizar o envio assim que a conexão for restabelecida.