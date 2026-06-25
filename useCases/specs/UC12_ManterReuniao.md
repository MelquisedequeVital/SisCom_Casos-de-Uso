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
1. No passo 2 do Fluxo Principal, o ator em vez de criar uma nova reunião, seleciona uma reunião existente diretamente no painel do Calendário.
2. O sistema abre a tela com os detalhes da reunião e os campos preenchidos.
3. O ator altera as informações necessárias (como horário ou participantes) e clica em 'Salvar Alterações'.
4. O sistema atualiza o evento e dispara uma notificação de atualização para os convidados.

#### A2 - Cancelar Reunião Existente
1. O ator executa o passo 1 do fluxo **[A1]**.
2. O ator seleciona a opção 'Excluir Reunião' ou 'Cancelar Reunião'.
3. O sistema solicita uma confirmação da exclusão.
4. O ator confirma. O sistema remove o evento do calendário e notifica os participantes sobre o cancelamento.

#### A3 - Visão Global e Gerenciamento de Salas (Exclusivo Administrador)
1. O ator Administrador acessa a página de reuniões.
2. O sistema identifica o perfil de Administrador e libera o painel de "Agendamentos Globais e Salas".
3. O Administrador consegue visualizar, alterar ou cancelar reuniões de qualquer setor ou usuário do sistema, além de alocar salas globais.
4. O fluxo de edição ou cancelamento segue as mesmas etapas dos fluxos **[A1]** e **[A2]**.
---

### Fluxos de Exceção

#### E1 - Campos Obrigatórios Ausentes
1. No passo 4 do Fluxo Principal, o ator tenta agendar a reunião deixando o Título, Data ou Horário em branco.
2. O sistema identifica a ausência dos dados obrigatórios.
3. O sistema impede o salvamento, destaca os campos inválidos e exibe o alerta: *"Por favor, preencha os campos obrigatórios (Título, Data e Horários) para prosseguir."*
