# Caso de Uso: UC_IniciarChatDireto

**Objetivo:** Permitir que um ator com perfil de Gestor tenha a opção de iniciar uma comunicação direta com outro gestor da organização a partir da tela de abertura de chamados, pulando a triagem por setor, ou optar por seguir com a abertura de um chamado normal.  
**Requisitos:** RF2002
**Atores:** Gestor  
**Condição de entrada:** O ator seleciona a opção de abrir um chamado no dashboard principal.

---

### Fluxo Principal

1. O ator acessa a página de abertura de chamados. Ele verifica que o título da página na aba do navegador e na própria página é 'Abrir Chamado'.
2. O sistema identifica que o ator possui o perfil de 'Gestor' e exibe, além dos campos padrão de chamado, uma opção de alternância (aba ou botão) para "Iniciar Chat Direto com Gestor".
3. O ator decide por utilizar o canal direto e seleciona a opção "Iniciar Chat Direto com Gestor". **[A1]**
4. O sistema atualiza a tela e altera os campos visíveis, ocultando a seleção de setores. O ator observa que a página agora possui os seguintes campos para:
   * Lista de Gestores (campo de seleção do destinatário)
   * Motivo do Contato (campo de texto curto)
   * Mensagem Inicial (caixa de texto longa)
   * opções:
     * Iniciar Chat
     * Cancelar
5. O ator seleciona o gestor desejado na lista, preenche o motivo do contato e digita a primeira mensagem.
6. O ator seleciona o botão 'Iniciar Chat'. **[A2]**
7. O sistema verifica se todos os campos obrigatórios estão preenchidos de forma válida.
8. O sistema cria o canal de comunicação direta, envia a mensagem inicial e redireciona o ator automaticamente para a tela do chat ativo (`UC_TrocarMensagens`), exibindo uma mensagem de sucesso no topo.

---

### Fluxos Alternativos

#### A1 - Optar por Abrir Chamado Normal
1. No passo 3 do Fluxo Principal, o Gestor opta por não usar o chat direto e decide abrir um chamado comum para um setor específico.
2. O fluxo segue as regras e etapas descritas no caso de uso de abertura de chamados padrão (`UC_AbrirChamado`).

#### A2 - Cancelar a Operação
1. No passo 6 do Fluxo Principal, o ator desiste de iniciar o chat direto e seleciona o botão 'Cancelar'.
2. O sistema limpa os campos preenchidos e retorna o ator para o dashboard principal, sem criar nenhuma nova conversa ou registro.

---

### Fluxos de Exceção

#### E1 - Campos Obrigatórios Não Preenchidos
1. No passo 6 do Fluxo Principal, o ator clica em 'Iniciar Chat' sem selecionar um gestor da lista ou sem digitar a mensagem inicial.
2. O sistema identifica a ausência dos dados obrigatórios.
3. O sistema impede o envio, destaca os campos não preenchidos em vermelho e exibe o alerta: *"Por favor, preencha todos os campos obrigatórios para iniciar o chat."*