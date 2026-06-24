# Caso de Uso: UC11_ConsultarHistorico

**Objetivo:** Permitir que o ator consulte o histórico completo de chats anteriores e mensagens trocadas, inclusive em modo offline.  

**Requisitos:** RF003 (Módulo de Mensagem e Colaboração) e RF2004 (Modo Offline)  

**Atores:** Usuário do Sistema (US)  

**Condição de entrada:** O ator está com uma conversa ativa aberta na página de mensagens (`UC_TrocarMensagens`).

---

### Fluxo Principal

1. O ator visualiza a tela da conversa ativa à direita e seleciona o ícone de três pontinhos (menu de opções) localizado no topo superior da conversa.
2. O sistema exibe um menu flutuante com opções adicionais. O ator observa que existe a opção:
   * Consultar Histórico
3. O ator seleciona a opção 'Consultar Histórico'. **[A1]**
4. O sistema processa a requisição, busca os registros no banco de dados e atualiza a tela exibindo uma linha do tempo estática com todas as mensagens, carimbos de data/hora e anexos passados daquele chat/chamado.
5. O ator verifica as informações desejadas no histórico da conversação.

---

### Fluxos Alternativos

#### A1 - Visualizar Histórico Offline
1. No passo 3 do Fluxo Principal, o ator seleciona 'Consultar Histórico', porém o sistema detecta que o dispositivo está sem conexão com a internet.
2. O sistema ativa o modo offline por meio da arquitetura PWA `[RNF005]`.
3. O sistema busca os dados armazenados localmente no cache do dispositivo `[RNF002]`.
4. O sistema renderiza o histórico disponível localmente e exibe um informativo visual na tela com o texto: *"Modo Offline - Exibindo histórico local"*.
