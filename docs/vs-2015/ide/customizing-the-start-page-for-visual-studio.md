---
title: Personalizando a página inicial | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start page
ms.assetid: 925d42eb-ec34-426e-ad81-19db8630e536
caps.latest.revision: 48
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c426ca146380ce01ec2c1f257c6da5538b941c19
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53059766"
---
# <a name="customizing-the-start-page-for-visual-studio"></a>Personalizando a página inicial do Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

É possível personalizar a página inicial do Visual Studio de várias maneiras padrão, mostrando, por exemplo, a caixa de diálogo **Abrir Projeto** ou abrindo a solução que foi carregada mais recentemente. Também é possível mostrar uma página inicial personalizada, que é uma página XAML do Windows Presentation Foundation (WPF) executada em uma janela de ferramenta e pode executar comandos que são internos do Visual Studio.

## <a name="customizing-the-default-start-page"></a>Personalizando a página inicial padrão

1.  Na barra de menus, escolha **Ferramentas**, **Opções**.

2.  Expanda **Ambiente** e escolha **Inicialização**.

3.  Na lista **Na inicialização**, escolha o item da personalização desejado.

## <a name="show-a-custom-start-page"></a>Mostrar uma página inicial personalizado

1.  Instale uma página inicial personalizada de uma das seguintes maneiras:

    -   Instale-a por meio da [Galeria do Visual Studio](http://visualstudiogallery.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=start%20page), de outro site ou de uma página da intranet local.

        > [!NOTE]
        >  Se desejar uma página que é direcionada para uma versão anterior do Visual Studio, você pode atualizá-la usando o SDK do Visual Studio. Consulte como fazê-lo: [. Atualizar uma página de início personalizados do Visual Studio](../misc/how-to-upgrade-a-visual-studio-custom-start-page.md).

         Abra um arquivo .vsix que contenha uma página inicial personalizada ou copie e cole os arquivos de página inicial na pasta **%USERPROFILE% \My Documents\Visual Studio 2015\StartPages** do computador.

    -   Criar sua própria página inicial se você instalou o SDK do Visual Studio.

         Ver [criar a sua própria página inicial](../misc/creating-your-own-start-page.md).

2.  Na barra de menus, escolha **Ferramentas**, **Opções**.

3.  Expanda **Ambiente** e escolha **Inicialização**.

4.  Na lista **Personalizar Página Inicial**, escolha a página desejada.

> [!NOTE]
>  Se um erro em uma página inicial personalizada causar pane no Visual Studio, você poderá iniciar o Visual Studio no modo de segurança e defini-lo para usar a página inicial padrão. Consulte [/SafeMode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).

## <a name="see-also"></a>Consulte também
 [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3) [criando sua própria página inicial](../misc/creating-your-own-start-page.md)
