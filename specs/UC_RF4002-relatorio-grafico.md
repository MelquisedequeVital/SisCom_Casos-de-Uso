## [RF4002] - Relatório Gráfico: Como gestor, eu gostaria de visualizar graficamente métricas do meu departamento, contendo quantidade de solicitações enviadas, resolvidas, principais motivos e média de mensagens por chamado, para que eu possa formular relatórios de produtividade.

**Caso de uso:** Visualização de Métricas e Geração de Relatórios do Setor  
**Objetivo:** Permitir que o gestor visualize graficamente as métricas do seu setor (solicitações, resoluções, motivos e interações) para acompanhar o desempenho e formular relatórios de produtividade.  
**Requisitos:** [RF4002]  
**Atores:** Gestor  
**Condição de entrada:** O ator faz login no sistema e acessa a área de dashboard/relatórios exclusiva da sua gestão.  

### Fluxo Principal
1. O ator acessa o menu de "Relatórios" no Dashboard do sistema.
2. O ator seleciona o período de tempo desejado para a análise **[A1]**.
3. O sistema carrega e o ator visualiza os gráficos contendo a quantidade total de solicitações enviadas e o volume de solicitações resolvidas.
4. O ator analisa o gráfico (ex: gráfico de pizza ou barras) que destaca os principais motivos para a abertura dos chamados.
5. O ator confere o indicador de média de mensagens por chamado para avaliar o nível de esforço e interação na resolução dos tickets.
6. O ator utiliza as informações dispostas na tela para extrair ou consolidar o seu relatório de produtividade **[A2]**.

### Fluxos Alternativos
* **[A1] Filtragem de Período Personalizada:** No passo 2, o ator pode aplicar filtros de data específicos (como "Últimos 7 dias", "Mês Atual" ou "Intervalo Customizado"). O sistema atualiza todos os gráficos instantaneamente para refletir apenas os dados do período selecionado.
* **[A2] Exportação de Dados:** No passo 6, o ator pode clicar em um botão de "Exportar Relatório" (ex: em PDF ou CSV), permitindo que ele salve uma cópia do painel gráfico no seu computador para apresentar em reuniões da instituição.

### Fluxos de Exceção
* **[E1] Ausência de Dados no Período:** Se, após o passo 2, não houver nenhum chamado aberto ou resolvido no setor durante o período selecionado, o sistema exibe os gráficos zerados (ou ocultos) junto com uma mensagem amigável: "Não há dados de chamados registrados para o período selecionado".
* **[E2] Falha no Carregamento das Métricas:** Caso ocorra um erro de comunicação com o banco de dados ao tentar gerar os gráficos, o sistema exibe um aviso de erro ("Falha ao carregar as métricas. Tente novamente mais tarde.") em vez de carregar gráficos quebrados ou incompletos.