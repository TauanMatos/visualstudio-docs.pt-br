---
title: Renomeação de refatoração
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 02b08f3218ab6f1380884d2385899d6dd486bb81
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53063147"
---
# <a name="rename-a-code-symbol-refactoring"></a>Refatoração Renomear um símbolo de código

Esta refatoração aplica-se a:

- C#

- Visual Basic

**O quê:** Permite renomear identificadores para símbolos de código, como campos, variáveis locais, métodos, namespaces, propriedades e tipos.

**Quando:** Você deseja renomear algo com segurança sem precisar localizar todas as instâncias e copiar/colar o novo nome.

**Por que:** Copiar e colar o novo nome em um projeto inteiro provavelmente resultará em erros. Essa ferramenta de refatoração realizará com precisão a ação de renomeação.

## <a name="how-to"></a>Como fazer

1. realce ou coloque o cursor do texto dentro do item a ser renomeado:

   - C#:

       ![Código realçado – C#](media/rename-highlight-cs.png)

   - Visual Basic:

       ![Código realçado – Visual Basic](media/rename-highlight-vb.png)

2. Depois, siga um destes procedimentos:

   - **Teclado**
      - Pressione **Ctrl+R**, em seguida, **Ctrl+R**. (Observe que o atalho de teclado pode ser diferente com base no perfil selecionado.)
   - **Mouse**
      - Selecione **Editar > Refatorar > Renomear**.
      - Clique com o botão direito do mouse no código e selecione **Renomear**.

3. Renomeie o item digitando o novo nome.

   - C#:

      ![Renomear animação – C#](media/rename-animated-cs.gif)

   - Visual Basic:

      ![Renomear – VB](media/rename-rename-vb.png)

   > [!TIP]
   > Também é possível atualizar os comentários e outras cadeias de caracteres para usar esse novo nome, bem como [visualizar as alterações](../../ide/preview-changes.md) antes de salvar usando as caixas de seleção na caixa **Renomear** que aparece na parte superior direita do editor.

4. Quando estiver satisfeito com a alteração, escolha **Aplicar** ou pressione **Enter** e as alterações serão confirmadas.

> [!NOTE]
> Se você escolher um nome que já exista, o que causaria um conflito, a caixa **Renomear** o avisará.
>
> ![Conflito de renomeação](media/rename-conflict-cs.png)

## <a name="see-also"></a>Consulte também

- [Refatoração](../refactoring-in-visual-studio.md)
- [Visualizar alterações](../../ide/preview-changes.md)
