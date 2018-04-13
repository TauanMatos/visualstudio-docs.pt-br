---
title: Usando a legenda de exibição de gráficos para analisar testes de carga no Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Load Test Analyzer, graphs view legend
- load tests, graphs view legend
ms.assetid: 0f6ba8e4-1343-419c-8a9f-240cf50efed7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 967cc1c854689ba034077d25f61cea74d1f082a2
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2018
---
# <a name="using-the-graphs-view-legend-to-analyze-load-tests"></a>Usando a legenda de exibição dos gráficos para analisar testes de carga

A exibição Gráficos do Analisador de Testes de Carga inclui um painel de legenda que exibe informações para cada contador de desempenho associado ao gráfico selecionado atualmente.

![Legenda de exibição de gráficos](../test/media/load_viewlegend.png "Load_ViewLegend")

As seguintes informações estão contidas na legenda:

-   **Mostrar no gráfico:** use as caixas de seleção para especificar se a linha de um determinado contador, como **Carga do usuário** ou **Erros/s**, é plotada no gráfico. Marque uma caixa de seleção se você quiser que a linha seja plotada no grafo. Desmarque uma caixa de seleção para remover a linha de plotagem do gráfico. Quando uma linha de plotagem é removida, as estatísticas do contador continuam sendo exibidas na legenda.

-   **Intervalo:** esta coluna exibe o intervalo do eixo y do contador de desempenho. Por padrão, esse valor se ajustará automaticamente à medida que o intervalo de dados de exemplo mudar. Um intervalo definido automaticamente sempre será a próxima potência de 10 maior que o valor máximo; isso inclui potências negativas de dez. Um gráfico pode conter vários contadores, cada um com um intervalo diferente. Por isso, o eixo y não é identificado com nenhum intervalo específico, e sim identificado com valores de 0-100 que representam uma porcentagem do intervalo total para cada contador. Por exemplo, para um contador com um intervalo de 1.000, um ponto de dados de 60 no eixo y corresponderia a um valor de 600 para o contador.

    > [!NOTE]
    > Você pode desativar o ajuste de valor do intervalo automático bloqueando o intervalo em um valor específico. Quando o intervalo é bloqueado, todos os valores excedendo o intervalo são exibidos como o valor máximo que você especificou na parte superior do gráfico. Use a caixa de diálogo **Opções de plotagem** para bloquear o intervalo em um valor específico. Para obter mais informações, consulte [Como especificar opções de plotagem para contadores de representação gráfica](../test/how-to-specify-plot-options-for-graphing-counters.md).

-   **Contador:** as quatro colunas chamadas **Contador**, **Instância**, **Categoria** e **Computador** identificam com exclusividade o contador de desempenho.

-   **Cor:** a coluna **Cor** mostra a cor e o estilo da linha plotada do contador de desempenho. Use a caixa de diálogo **Opções de plotagem** para alterar a cor ou o estilo da linha de um contador de desempenho no gráfico. A caixa de diálogo **Opções de plotagem** está disponível no menu de atalho da legenda. Para obter mais informações, consulte [Como especificar opções de plotagem para contadores de representação gráfica](../test/how-to-specify-plot-options-for-graphing-counters.md).

-   **Estatísticas:** as colunas **Mín.**, **Máx.**, **Média** e **Último** mostram as respectivas estatísticas do contador de desempenho. Esses valores correspondem aos dados exibidos na região visível do gráfico. Por exemplo, se você ampliar uma região de uma execução, as estatísticas da legenda refletirão valores somente da área ampliada. A coluna "Último" é o valor do contador de desempenho do intervalo de amostragem concluído mais recentemente.

    > [!NOTE]
    > A coluna Último só é exibida na legenda do Analisador de Testes de Carga quando o teste de carga está em execução.

     Para obter mais informações, consulte [Como ampliar uma região do gráfico](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

A seleção de um item na legenda faz o seguinte:

-   Permite que o item seja removido da legenda e do gráfico. Clique com o botão direito do mouse no item e selecione **Excluir** ou pressione a tecla **Delete**.

-   Realça a linha plotada no gráfico.

-   Faz a grade de dados exibir dados do item selecionado.

-   Permite acessar a caixa de diálogo **Opções de plotagem** do contador.

> [!TIP]
> Você pode usar o botão suspenso **Opções de gráfico** na barra de ferramentas do Analisador de Teste de Carga e selecione **Mostrar legenda** para mostrar ou ocultar o painel **Legenda** associado à exibição do gráfico.

## <a name="see-also"></a>Consulte também

- [Como especificar opções de plotagem para contadores de representação gráfica](../test/how-to-specify-plot-options-for-graphing-counters.md)
- [Como ampliar uma região do gráfico](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)
- [Analisar resultados de teste de carga na exibição de gráficos](../test/analyze-load-test-results-in-the-graphs-view.md)