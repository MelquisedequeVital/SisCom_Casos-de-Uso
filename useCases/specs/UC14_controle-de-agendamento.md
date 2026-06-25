## UC14 - Gerenciar Salas e Agendamentos Globais 

**Objetivo:** Permitir que o administrador realize um controle global de agendamentos, gerencie salas de reunião, ajude usuários a recuperar credenciais e evite conflitos de horários.  

**Requisitos:** [RF3003]  

**Atores:** Administrador  

**Condição de entrada:** O ator faz login no sistema e é redirecionado para o seu painel de controle.  

### Fluxo Principal
1. O ator acessa a página do painel de administrador.
2. O ator visualiza as opções disponíveis: usuários e departamentos.
3. O ator seleciona o campo "dashboard" e tem acesso aos chats, as reuniões agendadas e aos departamentos monitorados.
4. O ator seleciona os chats e redireciona os profissionais para os colaboradores com menor carga de trabalho no setor requisitado **[A1]**.
5. O ator acessa a área de usuários e redefine as credenciais daqueles que necessitam de auxílio **[A2]**.
6. O ator visualiza o calendário geral e faz a gestão dos links e horários das salas de reunião, garantindo que não haja conflitos **[A3]**.

### Fluxos Alternativos
* **[A1] Controle global de agendamentos:** O ator consegue visualizar as solicitações dos usuários e redirecioná-las para profissionais com menor carga de trabalho.
* **[A2] Redefinir credenciais:** O ator entra na lista geral de usuários, busca um usuário específico e aciona a opção para redefinir sua senha/credencial de acesso.
* **[A3] Gerenciar salas de reuniões:** O ator acessa a visualização de calendário contendo todas as reuniões agendadas, podendo criar uma nova reunião ou alterar dados (horário, sala, link) de reuniões já existentes.

### Fluxos de Exceção
* **[E1] Conflito de Horário:** No passo 5 do fluxo principal ou no [A3], se o ator tentar agendar uma reunião em uma sala/horário já ocupado, o sistema exibe um alerta de conflito e sugere o próximo horário disponível.
