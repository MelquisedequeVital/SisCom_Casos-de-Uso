# UC05 - Monitoramento e Auditoria Global de Logs de Acesso

  
**Objetivo:** Permitir que o administrador registre, visualize e monitore os logs de login e ações dos usuários no sistema para garantir a segurança da 
informação e investigar atividades indevidas, respeitando as normas de privacidade.  

**Requisitos:** [RNF1002] , [RF4004] - Auditoria Global de Acessos 

**Atores:** Administrador  

**Condição de entrada:** O ator faz login no sistema com credenciais administrativas e acessa o painel de segurança/auditoria global.  

### Fluxo Principal
1. O ator clica na opção "Auditoria Global" ou "Logs do Sistema" no menu lateral administrativo. Ele verifica que o título da página é 'Painel de Auditoria Global'.
2. O sistema exibe uma tabela contendo os registros mais recentes de login, logout e acessos a módulos. O ator observa que acima da tabela existem campos para filtros: "Usuário", "Período (Data Inicial e Final)", "Tipo de Ação" (menu de seleção) e "Status" (Sucesso/Falha).
3. O ator preenche os campos de filtros desejados e seleciona o botão "Filtrar" para realizar a busca por eventos específicos **[A1]**.
4. O sistema retorna os resultados da busca, exibindo dados como data, hora e o tipo de evento, porém aplicando técnicas de anonimização ou mascaramento em dados pessoais e IPs diretos para garantir a conformidade com o **[RNF1002]** (Conformidade com a LGPD) **[A2]**.
5. O ator analisa os registros listados para identificar possíveis anomalias, como múltiplas tentativas de login com falha ou acessos em horários não convencionais.

### Fluxos Alternativos
* **[A1] Exportação de Relatório de Segurança:**
1. No passo 3, o administrador observa e clica no botão "Exportar Relatório" localizado ao lado dos filtros.
2. O sistema abre uma lista de opções contendo os formatos de arquivo "PDF Criptografado" e "CSV Criptografado". O ator seleciona o formato desejado e o sistema realiza o download seguro.
* **[A2] Detalhamento de Evento de Segurança:**
1. No passo 4, na listagem de logs, o ator clica na linha de um evento crítico identificado (ex: tentativa de invasão).
2. O sistema abre uma gaveta de informações à direita da tela detalhando os parâmetros técnicos sem expor informações confidenciais desnecessárias.

### Fluxos de Exceção
* **[E1] Indisponibilidade do Serviço de Logs:** No passo 2, se a base de logs estiver offline, o sistema exibe de forma centralizada uma caixa de texto amigável: "O serviço de logs está indisponível no momento. Tente novamente mais tarde."
* **[E2] Tentativa de Alteração de Logs:** Se o administrador tentar executar comandos de escrita ou manipulação na tela ou URLs de logs, o sistema intercepta, cancela o evento e emite um alerta popup crítico de "Tentativa de violação de integridade de logs", notificando a segurança interna.
