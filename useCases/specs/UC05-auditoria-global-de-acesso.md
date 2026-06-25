# UC05 - Monitoramento e Auditoria Global de Logs de Acesso

  
**Objetivo:** Permitir que o administrador registre, visualize e monitore os logs de login e ações dos usuários no sistema para garantir a segurança da 
informação e investigar atividades indevidas, respeitando as normas de privacidade.  

**Requisitos:** [RNF1002] , [RF4004] - Auditoria Global de Acessos 

**Atores:** Administrador  

**Condição de entrada:** O ator faz login no sistema com credenciais administrativas e acessa o painel de segurança/auditoria global.  

### Fluxo Principal
1. O ator acessa o menu de "Auditoria Global" ou "Logs do Sistema".
2. O sistema exibe uma listagem contendo os registros mais recentes de login, logout e acessos a módulos por parte de todos os usuários.
3. O ator utiliza os filtros de pesquisa (por usuário específico, período de data/hora, tipo de ação ou status de sucesso/falha) para localizar eventos suspeitos ou realizar uma auditoria de rotina **[A1]**.
4. O sistema retorna os resultados da busca, exibindo dados como data, hora e o tipo de evento, porém aplicando técnicas de anonimização ou mascaramento em dados pessoais e IPs diretos para garantir a conformidade com o **[RNF1002]** (Conformidade com a LGPD) **[A2]**.
5. O ator analisa os registros listados para identificar possíveis anomalias, como múltiplas tentativas de login com falha ou acessos em horários não convencionais.

### Fluxos Alternativos
* **[A1] Exportação de Relatório de Segurança:** No passo 3, caso o administrador esteja investigando um incidente formal, ele pode exportar a listagem de logs filtrados para um arquivo seguro (ex: PDF ou CSV criptografado) para anexar como evidência da auditoria.
* **[A2] Detalhamento de Evento de Segurança:** No passo 4, o ator pode clicar em um log de "tentativa de invasão" ou "acesso bloqueado" para ver detalhes técnicos extras, mas sem que o sistema exponha informações sensíveis desnecessárias do titular da conta.

### Fluxos de Exceção
* **[E1] Indisponibilidade do Serviço de Logs:** No passo 2, se o servidor ou banco de dados responsável por armazenar os registros de auditoria estiver temporariamente offline, o sistema exibe uma mensagem: "O serviço de logs está indisponível no momento. Tente novamente mais tarde", evitando travar a interface do administrador.
* **[E2] Tentativa de Alteração de Logs:** Como os logs são imutáveis por questões de segurança, se o administrador tentar (por qualquer interface ou manipulação de URL) editar ou apagar um registro de acesso, o sistema bloqueia imediatamente a ação e gera um alerta interno crítico de "Tentativa de violação de integridade de logs".
