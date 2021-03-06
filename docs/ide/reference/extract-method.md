---
title: Extrair um método
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.extractmethod
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: b80b5053022b9e42bb6cfd30e3c76a72bef70746
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53064608"
---
# <a name="extract-a-method-refactoring"></a>Refatoração Extrair um método

Esta refatoração aplica-se a:

- C#

- Visual Basic

**O quê:** Permite transformar um fragmento de código em seu próprio método.

**Quando:** Você tem um fragmento de código existente em algum método que precisa ser chamado de outro método.

**Por que:** Você pode copiar/colar esse código, mas isso pode levar à duplicação. A melhor solução é refatorar esse fragmento em seu próprio método, o que pode ser chamado livremente por qualquer outro método.

## <a name="how-to"></a>Como fazer

1. realce o código a ser extraído:

   - C#:

       ![Código realçado – C#](media/extractmethod-highlight-cs.png)

   - Visual Basic:

       ![Código realçado – Visual Basic](media/extractmethod-highlight-vb.png)

2. Depois, siga um destes procedimentos:

   - **Teclado**
      - Pressione **Ctrl+R**, em seguida, **Ctrl+M**. (Observe que o atalho de teclado pode ser diferente com base no perfil selecionado.)
      - Pressione **Ctrl**+**.** para disparar o menu **Ações Rápidas e Refatorações** e selecionar **Extrair Método** no pop-up da janela Visualização.
   - **Mouse**
      - Selecione **Editar > Refatorar > Extrair Método**.
      - Clique com o botão direito do mouse no código e selecione **Refatorar > Extrair > Extrair Método**.
      - Clique com o botão direito do mouse no código, selecione o menu **Ações Rápidas e Refatorações** e selecione **Extrair Método** no pop-up da janela Visualização.

   O método será criado imediatamente. A partir daqui, agora você pode renomear o método digitando o novo nome.

   > [!TIP]
   > Também é possível atualizar os comentários e outras cadeias de caracteres para usar esse novo nome, bem como [visualizar as alterações](../../ide/preview-changes.md) antes de salvar usando as caixas de seleção na caixa **Renomear**, que aparece na parte superior direita do seu IDE.

   - C#:

      ![Renomear método – C#](media/extractmethod-rename-cs.png)

   - Visual Basic:

      ![Renomear método – Visual Basic](media/extractmethod-rename-vb.png)

3. Quando estiver satisfeito com a alteração, escolha **Aplicar** ou pressione **Enter** e as alterações serão confirmadas.

## <a name="see-also"></a>Consulte também

- [Refatoração](../refactoring-in-visual-studio.md)
- [Visualizar alterações](../../ide/preview-changes.md)