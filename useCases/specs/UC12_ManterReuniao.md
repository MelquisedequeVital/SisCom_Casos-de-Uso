# Caso de Uso: UC12_ManterReuniao

**Objetivo:** Permitir que o ator realize o agendamento, consulta, alteração e cancelamento de reuniões integradas ao calendário do sistema.  

**Requisitos:** RF3001 e RF3002

**Atores:** Gestor, Administrador (Usuários com permissão de agendamento conforme [NR001])  

**Condição de entrada:** O ator seleciona a opção 'Calendário' ou 'Reuniões' no dashboard principal.

---

### Fluxo Principal (Agendar Reunião)

1. O ator acessa a página de reuniões. Ele verifica que o título da página na aba do navegador e na própria página é 'Calendário de Reuniões'.
2. O ator seleciona a opção de agendar uma nova reunião.
3. O sistema exibe a tela de formulário. O ator observa que a página possui os seguintes campos para:
   * Título da Reunião (campo de texto)
   * Data e Horário de Início (campos de data/hora)
   * Horário de Término (campo de hora)
   * Link da Plataforma Externa (caixa de texto para Google Meet, Zoom ou Teams, conforme [NR002])
   * Descrição/Pauta (caixa de texto longa)
   * Convidar Participantes (campo de seleção de usuários/setores)
   * opções:
     * Agendar
     * Cancelar
4. O ator preenche todos os campos com as informações da reunião, seleciona os participantes que deseja convidar e clica no botão 'Agendar'. **[A1]**, **[A2]**
5. O sistema verifica se todas as informações preenchidas são válidas e se não há conflito de horário para o organizador.
6. O sistema salva a reunião, insere o evento visualmente no calendário do ator e exibe uma mensagem informando que a reunião foi agendada com sucesso.
7. O sistema identifica os usuários adicionados e gera, de maneira automatizada, uma notificação visual (alerta em tela) e por e-mail informando sobre o convite para a reunião.

---

### Fluxos Alternativos

#### A1 - Visualizar e Editar Reunião
1. No passo 2 do Fluxo Principal, o ator em vez de criar uma nova reunião, seleciona uma reunião existente diretamente no painel do Calendário. O sistema abre a tela com os detalhes preenchidos. O sistema abre a tela com os detalhes preenchidos. O ator altera as caixas de horários ou pauta e seleciona o botão 'Salvar Alterações'.

#### A2 - Cancelar Reunião Existente
1. O ator abre o bloco de uma reunião agendada e clica no botão vermelho 'Excluir Reunião'. O sistema exibe um modal de confirmação , o ator confirma e o sistema remove o registro e dispara alertas de cancelamento.

#### A3 - Visão Global e Gerenciamento de Salas (Exclusivo Administrador)
1. O Administrador acessa a página e o sistema libera o painel adicional "Agendamentos Globais e Salas". O administrador visualiza e gerencia reuniões de qualquer usuário da plataforma.
---

### Fluxos de Exceção

#### E1 - Campos Obrigatórios Ausentes
1. O ator clica em agendar deixando caixas textuais ou temporais vazias.
3. O sistema bloqueia a criação e emite um pop-up de aviso: "Por favor, preencha os campos obrigatórios (Título, Data e Horários) para prosseguir."
