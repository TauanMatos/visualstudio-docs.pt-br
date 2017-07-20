---
title: "Solução de problemas com erros de direcionamento do .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.FrameworkTargetingErrors
- MSBuild.ResolveAssemblyReference.FailedToResolveReferenceBecausePrimaryAssemblyInExclusionList
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], .NET Framework Client Profile
- multi-targeting
- multitargeting
- .NET Framework Client Profile
ms.assetid: 830e3e45-9a93-4279-a249-75b84599aefb
caps.latest.revision: 29
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
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 23510bfb61028db6d62912066bc6f4756e8ec37e
ms.contentlocale: pt-br
ms.lasthandoff: 05/13/2017

---
# <a name="troubleshooting-net-framework-targeting-errors"></a>Solução de problemas com erros de direcionamento do .NET Framework
Este tópico descreve os erros do MSBuild que podem ocorrer devido a referência problemas e como você pode resolver esses erros.  
  
## <a name="you-have-referenced-a-project-or-assembly-that-targets-a-different-version-of-the-net-framework"></a>Você fez referência a um projeto ou assembly direcionado a uma versão diferente do .NET Framework  
 É possível criar aplicativos que fazem referência a projetos ou a assemblies direcionados a versões diferentes do [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Por exemplo, você pode criar um aplicativo que tem como alvo o perfil de cliente para o [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] faz referência a um assembly que tem como alvo o .NET Framework 2.0. Entretanto, se você criar um projeto direcionado a uma versão anterior do [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], não será possível definir uma referência nesse projeto a um projeto ou assembly direcionado ao perfil de cliente para do [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] ou do próprio [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)]. Para resolver o erro, certifique-se de que seu aplicativo seja direcionado a um perfil ou a perfis compatíveis com o perfil que é o destino dos projetos ou assemblies referenciados pelo seu aplicativo.  
  
## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework"></a>Você novamente direcionou um projeto para uma versão diferente do .NET Framework  
 Se você alterar a versão de destino do [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] para seu aplicativo, o Visual Studio altera algumas das referências, mas talvez você precise atualizar algumas referências manualmente. Por exemplo, um dos erros mencionados anteriormente pode ocorrer se você alterar um aplicativo de destino de [!INCLUDE[net_v35SP1_long](../msbuild/includes/net_v35sp1_long_md.md)] e que o aplicativo tem recursos ou configurações que se baseiam no perfil de cliente para o [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)].  
  
 Para contornar as configurações do aplicativo, abra o **Solution Explorer**, escolha **Mostrar Todos os Arquivos** e edite o arquivo app.config no editor de XML do Visual Studio. Altere a versão nas configurações para coincidir com a versão apropriada do .NET Framework. Por exemplo, você pode alterar a configuração de versão de 4.0.0.0 para 2.0.0.0. Da mesma forma, para um aplicativo que tenha adicionado recursos, abra o **Solution Explorer**, escolha o botão **Mostrar Todos os Arquivos**, expanda **Meu Projeto** (Visual Basic) ou **Propriedades** (C#) e, em seguida, edite o arquivo Resources.resx no editor XML do Visual Studio. Altere a configuração de versão de 4.0.0.0 para 2.0.0.0.  
  
 Se seu aplicativo tiver recursos como ícones ou bitmaps ou configurações, como cadeias de conexão de dados, você também pode resolver o erro, removendo todos os itens na página **Configurações** do **Project Designer** e, em seguida, adicionando novamente as configurações necessárias.  
  
## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework-and-references-do-not-resolve"></a>Você novamente direcionou um projeto para uma versão diferente do .NET Framework e as referências não resolvidas  
 Se você redirecionar um projeto para uma versão diferente de [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], as referências podem não ser resolvidas corretamente em alguns casos. Explícitas referências totalmente qualificadas para assemblies geralmente causam esse problema, mas você pode resolvê-lo removendo as referências que não são resolvidas e, em seguida, adicioná-los ao projeto. Como alternativa, você pode editar o arquivo de projeto para substituir as referências. Primeiro, você pode remover referências da seguinte forma:  
  
```xml  
<Reference Include="System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089, processorArchitecture=MSIL" />  
```  
  
 Em seguida, substitua-os pelo seguinte formato:  
  
```xml  
<Reference Include="System.ServiceModel" />  
```  
  
> [!NOTE]
>  Depois de fechar e reabrir o projeto, você também deve recompilá-lo para garantir que todas as referências resolver corretamente.  
  
## <a name="see-also"></a>Consulte também  
 [Como direcionar para uma versão do .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md)   
 [.NET Framework Client Profile](http://msdn.microsoft.com/Library/f0219919-1f02-4588-8704-327a62fd91f1)   
 [Direcionamento para uma versão específica do .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md)   
 [Multiplataforma](../msbuild/msbuild-multitargeting-overview.md)