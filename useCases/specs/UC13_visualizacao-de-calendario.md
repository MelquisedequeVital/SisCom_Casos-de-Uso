## UC13 - Visualização de Calendário Pessoal

  
**Objetivo:** Permitir que o usuário comum consiga visualizar as reuniões marcadas que necessitam da sua presença para organizar sua agenda.  

**Requisitos:** [RF3001] , [RF3004] 

**Atores:** Usuário comum  

**Condição de entrada:** O ator faz login no sistema e é redirecionado para a página de dashboard.  

### Fluxo Principal
1. O ator acessa a tela principal (dashboard) do sistema.
2. O ator clica na opção “Reuniões Agendadas” no menu superior de navegação. Ele verifica que a página se chama 'Meu Calendário Pessoal' e observa uma grade mensal contendo blocos coloridos nas datas com compromissos marcados.
3. O ator visualiza um calendário contendo todas as reuniões marcadas em que sua presença é exigida **[A1]**.

### Fluxos Alternativos
* **[A1] Detalhamento da Reunião:**
1. O ator clica em um bloco de reunião específico contido na grade do calendário.
2. O sistema expande um modal flutuante na tela, onde o ator observa os seguintes campos preenchidos e informativos: "Pauta", "Horário de Início", "Horário de Término", "Organizador" e "Formato (Online/Presencial)". Se for online, exibe o link clicável da sala.

### Fluxos de Exceção
* **[E1] Calendário Vazio:** No passo 3, caso o usuário não possua nenhuma reunião salva para aquele mês visualizado, o sistema exibe a grade limpa de blocos contendo no cabeçalho um aviso em texto: "Você não possui reuniões agendadas para este período."
