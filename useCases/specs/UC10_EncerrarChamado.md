# Caso de Uso: UC10_EncerrarChamado

**Objetivo:** Permitir que o Usuário Requerente encerre um chamado ativo de dentro da tela de chat após confirmar que seu pedido foi atendido, fornecendo feedback sobre a resolução. 

**Requisitos:** RF005 (Módulo de Finalização de Atendimentos)  

**Atores:** Usuário Requerente (UReq)  

**Condição de entrada:** O ator está com um chat de chamado ativo aberto na página de mensagens (`UC_TrocarMensagens`).

---

### Fluxo Principal

1. O ator visualiza a tela da conversa ativa à direita e seleciona o botão 'Encerrar Chamado' localizado no topo superior do chat.
2. O sistema abre uma janela sobreposta (modal) na tela. O ator observa que o título do modal é 'Encerrar Atendimento' e que ele possui os seguintes campos para:
   * O seu chamado foi atendido? (Opções de seleção: Sim / Não / Parcialmente)
   * Avaliação do Atendimento (Escala de 1 a 5 estrelas)
   * Descreva como o problema foi resolvido (Caixa de texto longa)
   * opções:
     * Confirmar Encerramento
     * Voltar para o Chat
3. O ator seleciona que o chamado foi atendido, escolhe a nota de avaliação, digita a explicação de como o problema foi resolvido na caixa de texto e clica no botão 'Confirmar Encerramento'. **[A1]**
4. O sistema verifica se os campos obrigatórios (confirmação e nota) foram preenchidos.
5. O sistema altera o status do chamado para 'Fechado' no banco de dados.
6. O sistema fecha o modal, atualiza a linha do tempo do chat inserindo um aviso de sistema de que o chamado foi encerrado, bloqueia novas mensagens e exibe um alerta de sucesso no topo: *"Chamado encerrado com sucesso. Obrigado pelo feedback!"*

---

### Fluxos Alternativos

#### A1 - Desistir do Encerramento
1. O ator decide não fechar o chamado naquele momento e seleciona o botão 'Voltar para o Chat' ou clica no ícone de fechar (X) do modal. O sistema fecha o modal sem salvar nenhuma alteração.

---

### Fluxos de Exceção

#### E1 - Feedback Obrigatório Ausente
1. O ator clica em 'Confirmar Encerramento' sem preencher os critérios mandatórios de nota ou atendimento.
2. O sistema bloqueia a finalização, destaca os campos em vermelho e emite o alerta: "Por favor, preencha os campos de avaliação obrigatórios para encerrar o chamado."
