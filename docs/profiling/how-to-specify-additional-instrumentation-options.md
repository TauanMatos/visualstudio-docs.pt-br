---
title: "Como especificar opções de instrumentação adicionais | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.advanced
helpviewer_keywords:
- instrumentation, options
- profiling tools, session options
- performance sessions, options
ms.assetid: 639afe26-8335-4bd4-8aa5-f2c607b81f07
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 84e77bbb0901a677b9974ceacb4363155a26d8cc

---
# <a name="how-to-specify-additional-instrumentation-options"></a>Como especificar opções de instrumentação adicionais
Você pode instrumentar binários do IDE (ambiente de desenvolvimento integrado) do [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ou usando as ferramentas de linha de comando. Se você instrumentar um binário do IDE, será possível controlar o volume de dados coletados durante a instrumentação, especificando opções de instrumentação adicionais para a ferramenta [VSInstr](../profiling/vsinstr.md). Essas opções estão disponíveis no nível de sessão ou de destino. Por exemplo, para incluir ou excluir funções específicas durante o processo de instrumentação, use a opção adicional de instrumentação no nível de destino.  
  
 **Requisitos**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!IMPORTANT]
>  Cada investigação que é inserida modifica ligeiramente o comportamento do programa original. Essa modificação gera sobrecarga no tempo de análise. Mesmo que uma aproximação dessa sobrecarga seja subtraída, ela ainda tem efeitos de temporização sutis em aplicativos com multithread. As opções de ferramenta [VSInstr](../profiling/vsinstr.md) ajudam a controlar a coleta de dados durante a criação de perfil.  
  
### <a name="to-specify-additional-instrumentation-option"></a>Como especificar opções de instrumentação adicionais  
  
1.  No **Gerenciador de Desempenho**, selecione a **Sessão de Desempenho** e, em seguida, clique com o botão direito do mouse em **Propriedades**.  
  
2.  Nas **Páginas de Propriedades**, clique nas propriedades **Avançadas**.  
  
3.  Digite opções na caixa **Opções de instrumentação adicionais**.  
  
     Por exemplo, use /CONTROL:THREAD para especificar o nível de criação de perfil. Para obter uma lista completa das opções, consulte [VSInstr](../profiling/vsinstr.md).  
  
4.  Clique em **OK**.  
  
## <a name="see-also"></a>Consulte também  
 [Configurando sessões de desempenho](../profiling/configuring-performance-sessions.md)   
 [Criando perfil na linha de comando](../profiling/using-the-profiling-tools-from-the-command-line.md)


<!--HONumber=Feb17_HO4-->

