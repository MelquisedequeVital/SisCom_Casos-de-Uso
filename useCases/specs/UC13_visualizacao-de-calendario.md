## UC13 - Visualização de Calendário Pessoal

  
**Objetivo:** Permitir que o usuário comum consiga visualizar as reuniões marcadas que necessitam da sua presença para organizar sua agenda.  

**Requisitos:** [RF3001] , [RF3004] 

**Atores:** Usuário comum  

**Condição de entrada:** O ator faz login no sistema e é redirecionado para a página de dashboard.  

### Fluxo Principal
1. O ator acessa a tela principal (dashboard) do sistema.
2. O ator seleciona o menu de “Reuniões Agendadas”.
3. O ator visualiza um calendário contendo todas as reuniões marcadas em que sua presença é exigida **[A1]**.

### Fluxos Alternativos
* **[A1] Detalhamento da Reunião:** O ator clica em uma reunião específica no calendário e o sistema expande os detalhes do evento, exibindo: pauta, horário de início, horário de término, organizador e formato (online/presencial).

### Fluxos de Exceção
* **[E1] Calendário Vazio:** No passo 3 do fluxo principal, caso o usuário não tenha nenhuma reunião agendada no período, o sistema exibe o calendário em branco.
