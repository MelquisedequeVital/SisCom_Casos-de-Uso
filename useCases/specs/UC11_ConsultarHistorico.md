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
    e então, clica nela.
3. O sistema processa a requisição, busca os registros de forma cronológica no banco de dados.
4. O sistema atualiza a tela e o ator observa que a linha do tempo ativa foi substituída por uma 'Visualização de Histórico Estático', contendo todas as mensagens antigas, balões cinzas, carimbos de data/hora e links de anexos passados daquele chat.
5. O ator desliza a página e verifica as informações desejadas no histórico da conversação.

---

### Fluxos Alternativos

#### A1 - Visualizar Histórico Offline
1. No passo 3 do Fluxo Principal, o ator seleciona 'Consultar Histórico', porém o sistema detecta que o dispositivo está sem conexão com a internet.
2. O sistema ativa o modo offline por meio da arquitetura PWA `[RNF005]` e busca os dados armazenados localmente no cache do dispositivo `[RNF002]`.
3. O sistema renderiza a listagem local e exibe um banner informativo fixado na cor amarela com o texto: "Modo Offline - Exibindo histórico local".

### Fluxos de Exceção

####FE01 - Histórico Inexistente
1. No passo 3, caso o chat seja novo e não possua interações prévias arquivadas, o sistema mantém a tela limpa e insere uma mensagem centralizada: "Não há mensagens anteriores registradas para este chat."
