## UC14 - Gerenciar Salas e Agendamentos Globais 

**Objetivo:** Permitir que o administrador realize um controle global de agendamentos, gerencie salas de reunião, ajude usuários a recuperar credenciais e evite conflitos de horários.  

**Requisitos:** [RF3003]  

**Atores:** Administrador  

**Condição de entrada:** O ator faz login no sistema e é redirecionado para o seu painel de controle.  

### Fluxo Principal
1. O ator clica no link "Painel Administrativo". Ele verifica que o título da página é 'Módulo de Gestão Centralizada' e observa duas seções bem definidas: "Usuários" e "Departamentos".
2. O administrador clica na opção/aba "Dashboard de Controle" e ganha visualização imediata de três painéis dinâmicos: listagem de chats ativos, calendário global de reuniões e monitoramento de departamentos.
3. O ator clica no painel de chats ativos, observa a distribuição de atendimentos e seleciona um chat para redirecioná-lo manualmente a um profissional livre do setor [A1].
4. O ator acessa a seção de "Usuários", digita o nome de um colaborador em uma caixa de pesquisa e seleciona a opção "Resetar Senha" para auxiliá-lo a recuperar seu acesso [A2].
5. O administrador clica no calendário global, observa a ocupação visual das salas físicas e manipula os campos de links e horários para ajustar agendamentos sem gerar conflito [A3].

### Fluxos Alternativos
* **[A1] Controle global de agendamentos:** Na listagem de chamados, o administrador clica no botão "Ajustar Carga de Trabalho". O sistema abre um assistente onde ele arrasta um ticket em aberto e solta sobre o nome de um atendente específico com menor índice de chamados ativos.
* **[A2] Redefinir credenciais:** O administrador localiza o botão "Forçar Nova Credencial" ao lado do perfil do usuário na listagem geral. Ao clicar, o sistema envia o comando direto ao banco de dados e dispara e-mail de redefinição obrigatória.
* **[A3] Gerenciar salas de reuniões:** Na visualização de salas, o administrador clica no botão "Nova Sala" ou "Mudar Link". O sistema atualiza o formulário da reunião modificando a URL externa em tempo real.

### Fluxos de Exceção
* **[E1] Conflito de Horário:** No passo 5 ou no fluxo alternativo [A3], se o administrador tentar arrastar ou salvar uma reunião em uma sala/horário já reservado por outro setor, o sistema bloqueia o salvamento e exibe um pop-up de alerta vermelho: "Conflito de Horário detectado para esta sala. Sugestão de próximo horário livre: [Data/Hora]."
