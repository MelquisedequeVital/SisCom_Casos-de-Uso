# Caso de Uso: UC08_TrocarMensagens

**Objetivo:** Permitir que o ator realize a troca de mensagens em tempo real ou de forma assíncrona, enviando textos e anexos após a abertura ou solicitação de um chamado.  

**Requisitos:** RF2001 

**Atores:** Usuário do Sistema (US)  

**Condição de entrada:** O ator é solicitado para atendimento ou solicita interação após a abertura de um chamado, selecionando a opção 'Acessar chats' no dashboard.

---

### Fluxo Principal

1. O ator acessa a página de mensagens através da opção 'Acessar chats' no dashboard principal. Ele verifica que o título da página na aba do navegador e na própria página é 'Chat do Sistema' (ou 'Mensagens'). Ele observa que existe uma lista de chats ativos à esquerda e, na tela da conversa ativa à direita, existe um campo para:
   * Escreva uma mensagem... (caixa de texto)
   * ícone de clipe (anexo)
   * ícone de avião de papel (enviar)
2. O ator seleciona a conversa ativa que está vinculada ao chamado (onde ele foi solicitado ou cuja interação ele mesmo requisitou).
3. O ator digita o texto da mensagem detalhando o problema ou respondendo à solicitação na caixa de texto e seleciona o botão com o ícone de avião de papel para enviar a mensagem. **[A1]**, **[A2]**
4. O sistema verifica se as informações para envio são válidas (campo de texto preenchido).
5. O sistema atualiza a tela exibindo a mensagem em um balão de texto na linha do tempo do chat em tempo real.
6. O outro ator (requerente ou requerido) visualiza a notificação, acessa a tela de chats e responde à mensagem enviada.
7. O sistema exibe as respostas sequencialmente na tela de mensagens.
8. Após o problema ser completamente resolvido por meio da conversação, o chamado associado é encerrado e a sessão de mensagens é concluída.

---

### Fluxos Alternativos

#### A1 - Enviar e Receber anexos
1. O ator necessita enviar um arquivo ou imagem para ilustrar o andamento do chamado. Ele seleciona o ícone de clipe ao lado da caixa de texto.
2. O sistema abre a janela de busca de arquivos do sistema operacional.
3. O ator seleciona o arquivo desejado e confirma o envio.
4. O sistema valida o arquivo e o renderiza dentro do balão de mensagens da conversa.

#### A2 - Redigir Mensagem Offline
1. O ator digita uma mensagem e clica no ícone de avião de papel para enviar, porém o sistema detecta que a conexão de rede caiu.
2. O sistema retém a mensagem localmente e apresenta um indicativo visual de falha de conexão.
3. Assim que a rede é restabelecida, o sistema processa o envio da mensagem automaticamente e a exibe na linha do tempo.
4. 
### Fluxos de Exceção

#### E1 - Mensagem Vazia
1. No passo 3 do Fluxo Principal, o ator seleciona o botão com o ícone de avião de papel sem ter digitado nenhum texto na caixa de mensagem (ou apenas espaços em branco).
2. O sistema identifica que o campo está vazio.
3. O sistema não realiza nenhuma ação de envio e mantém o botão de envio desabilitado ou impede a inserção na linha do tempo.

#### E2 - Falha no Upload do Anexo
1. No passo 3 do Fluxo Alternativo A1, o ator seleciona um arquivo que excede o limite de **10 MB** ou possui uma extensão proibida (** .exe, .bat, .sh **).
2. O sistema valida o arquivo e detecta a incompatibilidade.
3. O sistema exibe a mensagem de erro: *"Arquivo inválido. Limite máximo de 5 MB e extensões executáveis não permitidas."*
