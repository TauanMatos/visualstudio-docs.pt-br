---
title: "Implementar uma classe abstrata - geração de código (c#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cfed7f-f090-4369-8a85-2dcd4c7cf12b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 301c4f7a8955f22952787c78eaeabff826495c29
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="implement-an-abstract-class-in-c"></a>Implementar uma classe abstrata em c# #
**O que:** permite gerar imediatamente o código necessário para implementar uma classe abstrata. 

**Quando:** você deseja herdar de uma classe abstrata.  

**Motivo:** pode implementar manualmente todos os membros abstratos um por um, no entanto, esse recurso gerará automaticamente todas as assinaturas de método. 

**Como:**

1. Coloque o cursor na linha em que há um rabisco vermelho, indicando que você tenha herdado de uma classe abstrata, mas não implementou todos os membros necessários.

   ![Código realçado](media/abstract_highlight.png)

1. Em seguida, siga um destes procedimentos:
   * **Teclado**
     * Pressione **Ctrl +.** para disparar o **ações rápidas e refatorações** menu e selecione **implementação de classe abstrata** do popup da janela de visualização.
   * **Mouse**
     * Clique com botão direito e selecione o **ações rápidas e refatorações** menu e selecione **implementação de classe abstrata** do popup da janela de visualização.
     * Passe o mouse sobre o Rabisco vermelho e clique no ![Lâmpada](media/bulb.png) ícone que aparece.
     * Clique no ![Lâmpada](media/bulb.png) ícone que aparece na margem esquerda, se o cursor de texto já está na linha com o Rabisco vermelho.

   ![Visualização da classe de implementação](media/abstract_preview.png)

   >[!TIP]
   >Use o [ **visualizar alterações** ](../../ide/preview-changes.md) link na parte inferior da janela de visualização para ver todas as alterações que serão feitas antes de fazer sua seleção.
   >
   >Além disso, você pode usar o **documento**, **projeto**, e **solução** links na parte inferior da janela de visualização para criar as assinaturas de método correto em várias classes que herdam da classe abstrata.

1. As assinaturas de método abstract será criado automaticamente, pronto para ser implementada.

   ![Implementar o resultado de classe](media/abstract_result.png)

## <a name="see-also"></a>Consulte também  
[Geração de código (C#)](../code-generation-csharp.md)  
[Visualizar alterações](../../ide/preview-changes.md)