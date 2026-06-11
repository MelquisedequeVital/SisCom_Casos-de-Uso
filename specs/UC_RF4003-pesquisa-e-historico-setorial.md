## [RF4003] - Pesquisa e Histórico Setorial: Como gestor, eu gostaria de buscar e ler todos os chats abertos e encerrados no meu setor, com o uso de pesquisa avançada, para facilitar a auditoria interna do meu departamento, garantindo a privacidade conforme: [RNF1002] - Conformidade com a LGPD.

**Caso de uso:** Auditoria e Pesquisa de Histórico de Chats do Setor  
**Objetivo:** Permitir que o gestor busque, filtre e leia o histórico de chats abertos e encerrados do seu setor para fins de auditoria interna, garantindo a privacidade das informações.  
**Requisitos:** [RNF1002]  
**Atores:** Gestor  
**Condição de entrada:** O ator faz login no sistema, acessa o painel do seu setor e possui as permissões necessárias de gestão.  

### Fluxo Principal
1. O ator acessa o menu de "Histórico de Chats" ou "Auditoria".
2. O ator utiliza a barra de pesquisa avançada para buscar conversas específicas, preenchendo os critérios desejados (ex: palavras-chave, período de datas, status do chamado, ou atendente responsável) **[A1]**.
3. O sistema processa a busca e retorna uma lista de todos os chats abertos e encerrados vinculados ao setor do gestor que correspondam aos filtros.
4. O ator seleciona um chat específico da lista para leitura detalhada.
5. O sistema exibe a transcrição completa da conversa, aplicando automaticamente regras de ofuscação (máscaras de dados) sobre informações pessoais sensíveis para garantir o cumprimento do **[RNF1002]** (Conformidade com a LGPD) **[A2]**.
6. O ator conclui a leitura e análise para a sua auditoria interna, podendo retornar à lista de pesquisa para consultar novos chats.

### Fluxos Alternativos
* **[A1] Combinação de Múltiplos Filtros:** No passo 2, o ator pode combinar vários parâmetros simultaneamente (ex: buscar chats "Encerrados", atendidos por "João", no mês de "Maio", contendo a palavra "reembolso") para refinar a auditoria e encontrar ocorrências muito específicas.
* **[A2] Registro de Acesso (Log de Auditoria):** No passo 5, assim que o gestor abre a transcrição de um chat, o sistema pode registrar um log interno silencioso (data, hora e usuário que acessou) para garantir a rastreabilidade de quem visualizou aquelas informações, reforçando as políticas de segurança e privacidade.

### Fluxos de Exceção
* **[E1] Nenhum Resultado Encontrado:** No passo 3, caso nenhum chat corresponda aos critérios preenchidos na pesquisa avançada, o sistema exibe a mensagem "Nenhum chat encontrado com os filtros informados" e sugere que o ator limpe ou altere os parâmetros de busca.
* **[E2] Tentativa de Acesso a Chat de Outro Setor:** Se o ator tentar acessar o link direto de um histórico de chat que pertence a um setor diferente do qual ele gerencia, o sistema bloqueia a visualização e exibe uma tela de "Acesso Negado: Você não tem permissão para visualizar auditorias de outros setores".