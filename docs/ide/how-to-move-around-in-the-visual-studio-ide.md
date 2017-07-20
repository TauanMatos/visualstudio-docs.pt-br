---
title: Como mover-se no IDE do Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- environments [Visual Studio], navigation
- documents [Visual Studio], navigating
- IDE, navigation
- navigation [Visual Studio]
- files [Visual Studio], navigating between
- windows [Visual Studio], navigating
- Window.NextDocumentWindowNav
- IDE navigator
ms.assetid: 6c36b6eb-c93f-496b-af08-4199f7afd8bd
caps.latest.revision: 25
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: 9ca6b957f3ebc2770bed91e5ca27ec3f95715aa9
ms.contentlocale: pt-br
ms.lasthandoff: 05/24/2017

---
# Como mover-se no Visual Studio IDE
<a id="how-to-move-around-in-the-visual-studio-ide" class="xliff"></a>
O IDE (ambiente de desenvolvimento integrado) foi projetado para que você possa mover de uma janela para outra e de um arquivo para outro de várias maneiras diferentes, dependendo dos requisitos do projeto ou de preferência. Você pode optar por percorrer os arquivos abertos no editor ou percorrer todas as janelas de ferramentas ativas no IDE. Você também pode mudar diretamente para qualquer arquivo aberto no editor, independentemente da ordem em que ele foi acessado pela última vez. Esses recursos podem ajudar a aumentar sua produtividade ao trabalhar no IDE.  
  
> [!NOTE]
>  As opções disponíveis nas caixas de diálogo e os nomes os locais dos comandos de menu que você vê podem diferir do que é descrito na Ajuda, dependendo de suas configurações ativas ou da edição. Esta página de Ajuda foi escrita pensando nas **Configurações Gerais de Desenvolvimento**. Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**. Para obter mais informações, confira [Personalizar o IDE do Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
## Atalhos de teclado
<a id="keyboard-shortcuts" class="xliff"></a>  
 Quase todos os comandos de menu no Visual Studio têm um atalho de teclado. Também é possível criar seus próprios atalhos personalizados. Para obter mais informações, consulte [Identificando e personalizando atalhos de teclado](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
## Navegando entre arquivos no editor
<a id="navigating-among-files-in-the-editor" class="xliff"></a>  
 Você pode usar vários métodos para percorrer os arquivos abertos no editor. Você pode percorrer os arquivos com base na ordem em que os acessa, usar o Navegador de IDE para localizar rapidamente qualquer arquivo aberto no momento ou fixar arquivos favoritos à guia também para que fiquem sempre visíveis.  
  
 Navegue para Trás e Navegar para Frente percorre os arquivos abertos no editor baseado na ordem em que foram acessados, de modo muito semelhante a Voltar e Avançar no histórico de exibição no Microsoft Internet Explorer.  
  
#### Para percorrer os arquivos abertos por ordem de uso
<a id="to-move-through-open-files-in-order-of-use" class="xliff"></a>  
  
-   Para ativar os documentos abertos na ordem em que foram utilizados mais recentemente, pressione CTRL + SINAL DE SUBTRAÇÃO.  
  
-   Para ativar os documentos abertos na ordem inversa, pressione CTRL + SHIFT + SINAL DE SUBTRAÇÃO.  
  
    > [!NOTE]
    >  As opções **Navegar para Trás** e **Navegar para Frente** também podem ser encontradas no menu **Exibir**.  
  
 Você também pode mudar para um arquivo específico aberto no editor, independentemente de quando o arquivo foi acessado pela última vez, usando o **Navegador de IDE**, a lista **Arquivos Ativos** no editor ou a caixa de diálogo **Windows**.  
  
 O **Navegador de IDE** funciona de modo muito semelhante ao gerenciador de aplicativos do Windows. Ele não está disponível nos menus e pode ser acessado somente usando teclas de atalho. Você pode usar qualquer um dos dois comandos para acessar o **Navegador de IDE** (mostrado abaixo) para percorrer os arquivos, dependendo da ordem na qual deseja percorrê-los.  
  
 ![Navegador de IDE do Visual Studio](../ide/media/vs2015_ide_navigator.png "VS2015_IDE_Navigator")  
  
 O `Window.PreviousDocumentWindowNav` permite ir para o arquivo acessado mais recentemente e `Window.NextDocumentWindowNav` permite mover-se na ordem inversa. Configurações Gerais de Desenvolvimento atribuem CTRL + SHIFT + TAB a `Window.PreviousDocumentWindowNav` e CTRL + TAB a `Window.NextDocumentWindowNav`.  
  
> [!NOTE]
>  Se a combinação de configurações que você está usando ainda não tiver uma combinação de teclas de atalho atribuída a esse comando, você poderá atribuir seu próprio comando personalizado usando a página **Teclado** da caixa de diálogo **Opções**. Para obter mais informações, consulte [Identificando e personalizando atalhos de teclado](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
#### Para mudar para arquivos específicos no editor
<a id="to-switch-to-specific-files-in-the-editor" class="xliff"></a>  
  
-   Pressione CTRL + TAB para exibir o **Navegador de IDE**. Mantenha pressionada a tecla CTRL e pressione TAB repetidamente até selecionar o arquivo para o qual você deseja mudar.  
  
    > [!TIP]
    >  Para inverter a ordem em que você percorre a lista **Arquivos Ativos**, mantenha pressionadas as teclas CTRL + SHIFT e pressione a tecla TAB.  
  
     \- ou -  
  
-   No canto superior direito do editor, escolha o botão **Arquivos Ativos** e, em seguida, selecione um arquivo na lista para mudar para ele.  
  
     \- ou -  
  
-   Na barra de menus, escolha **Janela**, **Janelas**.  
  
-   Na lista, selecione o arquivo que você deseja exibir e, em seguida, escolha **Ativar**.  
  
## Navegando entre janelas de ferramentas no IDE
<a id="navigating-among-tool-windows-in-the-ide" class="xliff"></a>  
 O **Navegador de IDE** também permite percorrer as janelas de ferramenta abertas no IDE. Você pode usar qualquer um dos dois comandos para acessar o **Navegador de IDE** para percorrer janelas de ferramentas, dependendo da ordem na qual deseja percorrê-las. O `Window.PreviousToolWindowNav` permite ir para o arquivo acessado mais recentemente e `Window.NextToolWindowNav` permite mover-se na ordem inversa. Configurações gerais de desenvolvimento atribuem SHIFT + ALT + F7 a `Window.PreviousDocumentWindowNav` e ALT + F7 a `Window.NextDocumentWindowNav`.  
  
> [!NOTE]
>  Se a combinação de configurações que você está usando ainda não tiver uma combinação de teclas de atalho atribuída a esse comando, você poderá atribuir seu próprio comando personalizado usando a página **Teclado** da caixa de diálogo **Opções**. Para obter mais informações, consulte [Identificando e personalizando atalhos de teclado](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
#### Para mudar para uma janela de ferramentas específica no IDE
<a id="to-switch-to-a-specific-tool-window-in-the-ide" class="xliff"></a>  
  
-   Pressione ALT + F7 para exibir o **Navegador de IDE**. Mantenha pressionada a tecla ALT e pressionar F7 repetidamente até que selecionar a janela para a qual você pretende mudar.  
  
    > [!TIP]
    >  Para inverter a ordem em que você percorre a lista **Janelas de Ferramentas Ativas**, mantenha pressionada as teclas ALT + SHIFT e pressione F7.  
  
## Consulte também
<a id="see-also" class="xliff"></a>  
 [Personalizando layouts de janela](../ide/customizing-window-layouts-in-visual-studio.md)   
 [Atalhos de teclado padrão](../ide/default-keyboard-shortcuts-in-visual-studio.md)