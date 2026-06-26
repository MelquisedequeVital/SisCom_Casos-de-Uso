# UC17 - Visualização de Métricas e Geração de Relatórios do Setor  
 
**Objetivo:** Permitir que o gestor visualize graficamente as métricas do seu setor (solicitações, resoluções, motivos e interações) para acompanhar o desempenho e formular relatórios de produtividade.  

**Requisitos:** [RF4002]  

**Atores:** Gestor  

**Condição de entrada:** O ator faz login no sistema e acessa a área de dashboard/relatórios exclusiva da sua gestão.  

### Fluxo Principal
1. O ator clica na opção "Relatórios e Indicadores" no Dashboard gerencial. Ele verifica que a página se chama 'Painel de Desempenho Setorial' e observa no topo um campo de seleção de datas chamado "Período de Análise".
2. O ator seleciona o intervalo temporal desejado no campo correspondente e clica em "Atualizar Indicadores" [A1].
3. O sistema renderiza e exibe na tela os seguintes componentes visuais:
   Gráfico de Barras com o volume de solicitações enviadas versus resolvidas.
   Gráfico de Pizza detalhando os percentuais dos principais motivos de abertura de chamados.
   Cartão Indicador numérico exibindo a média de troca de mensagens por chamado.  
5. O ator analisa os gráficos exibidos e posiciona o ponteiro sobre as fatias do gráfico de pizza para inspecionar os valores exatos.
6. O ator utiliza a consolidação visual do painel e clica no botão "Extrair Relatório de Produtividade" [A2].

### Fluxos Alternativos
* **[A1] Filtragem de Período Personalizada:** No passo 2, o ator pode aplicar filtros de data específicos (como "Últimos 7 dias", "Mês Atual" ou "Intervalo Customizado"). O sistema atualiza todos os gráficos instantaneamente para refletir apenas os dados do período selecionado.
* **[A2] Exportação de Dados:** No passo 6, o ator pode clicar em um botão de "Exportar Relatório" (ex: em PDF ou CSV), permitindo que ele salve uma cópia do painel gráfico no seu computador para apresentar em reuniões da instituição.

### Fluxos de Exceção
* **[E1] Ausência de Dados no Período:** Se no período selecionado o setor não tiver computado nenhuma movimentação, o sistema oculta as áreas de gráficos e posiciona uma caixa de texto amigável: "Não há dados de chamados registrados para o período selecionado."
* **[E2] Falha no Carregamento das Métricas:** Se houver falha de requisição ou banco corrompido ao tentar montar as imagens, o sistema exibe retângulos vazios com uma exclamação e a mensagem interna: "Falha ao carregar as métricas. Tente novamente mais tarde."
