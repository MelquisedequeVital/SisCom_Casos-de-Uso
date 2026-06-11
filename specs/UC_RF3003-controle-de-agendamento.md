[RF3003] - Controle de Agendamentos: Como administrador, eu gostaria de realizar o controle global de agendamentos, redefinir credenciais e gerenciar salas de reunião, para evitar conflitos de horários na instituição.
Caso de uso: Gerenciar Salas e Agendamentos Globais 
Objetivo: Permitir que o administrador realize um controle global de agendamentos, gerencie salas de reunião, ajude usuários a recuperar credenciais e evite conflitos de horários.
Requisitos: [RF3003] 
Atores: Administrador 
Condição de entrada: O ator faz login no sistema e é redirecionado para o seu painel de controle.

Fluxo Principal
O ator acessa a página do painel de administrador.
O ator visualiza as opções disponíveis: controle global de agendamentos, redefinição de credenciais e gerenciamento de salas.
O ator seleciona o controle de agendamentos e redireciona os horários profissionais para os colaboradores com menor carga de trabalho no setor requisitado [A1].
O ator acessa a área de usuários e redefine as credenciais daqueles que necessitam de auxílio [A2].
O ator visualiza o calendário geral e faz a gestão dos links e horários das salas de reunião, garantindo que não haja conflitos [A3].

Fluxos Alternativos
[A1] Controle global de agendamentos: O ator seleciona um usuário específico através da lista de usuários e gerencia os agendamentos diretamente no perfil desse colaborador.
[A2] Redefinir credenciais: O ator entra na lista geral de usuários, busca um usuário específico e aciona a opção para redefinir sua senha/credencial de acesso.
[A3] Gerenciar salas de reuniões: O ator acessa a visualização de calendário contendo todas as reuniões agendadas, podendo criar uma nova reunião ou alterar dados (horário, sala, link) de reuniões já existentes.

Fluxos de Exceção
[E1] Conflito de Horário: No passo 5 do fluxo principal ou no [A3], se o ator tentar agendar uma reunião em uma sala/horário já ocupado, o sistema exibe um alerta de conflito e sugere o próximo horário disponível.
