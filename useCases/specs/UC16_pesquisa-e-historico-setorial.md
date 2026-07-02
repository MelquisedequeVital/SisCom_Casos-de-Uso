# UC16 - Auditoria e Pesquisa de Histórico de Chats do Setor  


**Objetivo:** Permitir que o gestor busque, filtre e leia o histórico de chats abertos e encerrados do seu setor para fins de auditoria interna, garantindo a privacidade das informações.  

**Requisitos:** [RNF1002] , [RF4003]

**Atores:** Gestor  

**Condição de entrada:** O ator faz login no sistema, acessa o painel do seu setor e possui as permissões necessárias de gestão.  

### Fluxo Principal
1. O ator clica na opção "Histórico de Chats" no painel gerencial. Ele verifica que o título da página é 'Auditoria de Conversações Setoriais'. Ele observa uma barra de pesquisa avançada contendo campos para preenchimento de palavras-chave, filtros de data (inicial/final), status do chamado (Aberto/Encerrado) e atendente responsável.
2. O ator preenche os filtros desejados na barra avançada e clica no botão "Pesquisar" [A1].
3. O sistema processa a busca e atualiza a listagem exibindo em colunas estruturadas todos os chats que pertencem àquele setor e batem com os filtros.
4. O ator localiza a conversa procurada na tabela e clica no botão/ícone de olho "Visualizar Transcrição".
5. O sistema carrega na tela o documento de transcrição completa, aplicando máscaras pretas ou caracteres de ofuscação (ex: ..*-) sobre dados como CPF, telefone e e-mails pessoais, garantindo conformidade com o [RNF1002] (LGPD) [A2].
6. O ator conclui a leitura analítica e clica no botão "Voltar para Pesquisa" para continuar a rotina.
   
### Fluxos Alternativos
* **[A1] Combinação de Múltiplos Filtros:** No passo 2, o ator pode combinar vários parâmetros simultaneamente (ex: buscar chats "Encerrados", atendidos por "João", no mês de "Maio", contendo a palavra "reembolso") para refinar a auditoria e encontrar ocorrências muito específicas.
* **[A2] Registro de Acesso (Log de Auditoria):** No passo 5, concomitante à renderização do texto, o sistema grava internamente uma linha imutável no banco de segurança contendo: ID do Gestor, Data, Hora e ID da conversa lida para rastreabilidade de acessos.

### Fluxos de Exceção
* **[E1] Nenhum Resultado Encontrado:** No passo 3, caso nenhum chat corresponda aos critérios preenchidos na pesquisa avançada, o sistema exibe a mensagem "Nenhum chat encontrado com os filtros informados. Limpe os parâmetros e tente novamente."
* **[E2] Tentativa de Acesso a Chat de Outro Setor:** Se o gestor tentar forçar o id de uma URL de um chat de outro departamento, o sistema barra o carregamento e exibe em tela inteira a mensagem: "Acesso Negado: Você não tem permissão para visualizar auditorias de outros setores."
