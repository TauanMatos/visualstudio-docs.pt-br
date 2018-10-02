---
title: 'Diagramas de componente UML: Referência | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.componentdiagram.diagram
- vs.teamarch.componentdiagram.toolbox
- vs.teamarch.UMLModelExplorer.componentdiagram
helpviewer_keywords:
- UML diagrams, component
- diagrams - modeling, component
- diagrams - modeling, UML component
- UML, component diagrams
- component diagrams
ms.assetid: 5eddff6a-892a-4c3c-9278-687ac1eccc50
caps.latest.revision: 38
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: f628ebfa84246c6d991543352f4de36a51cc7fbf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47474309"
---
# <a name="uml-component-diagrams-reference"></a>Diagramas de componente UML: referência
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [diagramas de componente UML: referência](https://docs.microsoft.com/visualstudio/modeling/uml-component-diagrams-reference).  
  
No Visual Studio, uma *diagrama de componente* mostra as partes de um design para um sistema de software. Ajuda do diagrama de componente você visualizar a estrutura de alto nível do sistema e o comportamento de serviço que essas partes fornecerem e consumir por meio de interfaces. Para criar um diagrama de componente UML, nos **arquitetura** menu, clique em **UML novo ou diagrama de camada**.  
  
 Para ver quais versões do Visual Studio dão suporte a esse recurso, consulte [suporte de versão para a arquitetura e ferramentas de modelagem](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Você pode usar um diagrama de componente para descrever um design que é implementado em qualquer linguagem ou estilo. Só é necessário identificar partes de design que interagem com as outras partes do projeto por meio de um conjunto restrito de entradas e saídas. Os componentes podem ser de qualquer escala e podem ser interconectados de qualquer maneira.  
  
 Para obter mais informações sobre como usar diagramas de componente no processo de design, consulte [modelar a arquitetura do seu aplicativo](../modeling/model-your-app-s-architecture.md).  
  
> [!NOTE]
>  Este tópico descreve os elementos que você pode usar em diagramas de componente. Para obter mais informações sobre como desenhar diagramas de componente detalhados, consulte [diagramas de componente UML: diretrizes](../modeling/uml-component-diagrams-guidelines.md). Para obter mais informações sobre como desenhar diagramas de modelagem em geral, consulte [modelos e diagramas UML editar](../modeling/edit-uml-models-and-diagrams.md).  
  
## <a name="reading-component-diagrams"></a>Leitura de diagramas de componente  
 A tabela a seguir descreve os elementos que você pode usar em um diagrama de componente, junto com suas propriedades principais. Para obter uma lista completa das propriedades dos elementos, consulte [propriedades de elementos em diagramas de componente UML](../modeling/properties-of-elements-on-uml-component-diagrams.md).  
  
 ![Elementos usados em diagramas de componente](../modeling/media/uml-compovreading.png "UML_CompOvReading")  
  
|**Forma**|**Elemento**|**Descrição e propriedades principais**|  
|---------------|-----------------|-----------------------------------------|  
|1|**Componente**|Um pedaço reutilizável de funcionalidade do sistema. Um componente fornece e consome comportamento por meio de interfaces e pode usar outros componentes.<br /><br /> Você pode ocultar ou mostrar as partes internas de um componente usando o controle expandir/recolher (9).<br /><br /> Um componente é um tipo de classe.<br /><br /> -   **Is Indirectly Instantiated**. Se for true (padrão), o componente existe apenas como um artefato de design. Em tempo de execução, apenas suas partes existem.|  
|2|**Fornecida a porta do adaptador**|Representa um grupo de mensagens ou chamadas que um componente implementa e que outros componentes ou sistemas externos podem usar. Uma porta é uma propriedade de um componente que tem uma interface como seu tipo.|  
|3|**Porta de Interface necessária**|Representa um grupo de mensagens ou chamadas que o componente envia para outros componentes ou sistemas externos. O componente é projetado para ser acoplado a componentes que fornecem pelo menos essas operações. A porta tem uma interface como seu tipo.|  
|4|**dependência**|Pode ser usado para indicar que uma Interface obrigatória em um componente pode ser atendida por uma Interface fornecida em outro.<br /><br /> As dependências também podem ser usadas de modo geral entre os elementos de modelo, para mostrar que o design de um dependerá do design do outro.|  
|5|**Parte**|Um atributo de um componente, cujo tipo é um componente geralmente outro. Uma parte é usada no design interno do componente pai. Partes são exibidas graficamente, aninhadas dentro do componente pai.<br /><br /> Para criar uma parte de um tipo de componente existente, arraste o componente do Gerenciador de modelos UML para o componente proprietário.<br /><br /> Para criar uma parte de um novo tipo, clique o **componente** ferramenta e, em seguida, clique no componente de proprietário.<br /><br /> Por exemplo, um componente `Car` tem partes `engine:CarEngine`, `backLeft:Wheel`, `frontRight:Wheel`e assim por diante.<br /><br /> Mais de uma parte pode ter o mesmo tipo e componentes diferentes podem ter partes do mesmo tipo.<br /><br /> -   **Tipo**. O tipo da parte, que é definido em outro lugar no modelo. Normalmente, o tipo é outro componente.<br />-   **Multiplicidade**. O padrão é 1. Você pode defini-lo **entre 0 e 1** para indicar que a parte pode ter o valor **nulo**, **\*** para indicar que a parte é uma coleção de instâncias de determinado tipo, ou a qualquer expressão que pode ser avaliada como um intervalo de números.|  
|6|**Assembly de parte**|Uma conexão entre as portas de interface obrigatória de uma parte e as portas de interface fornecida de outro. A implementação de um assembly de parte pode variar de um componente para outro. As partes conectadas devem ter o mesmo componente pai.|  
|7|**Delegação**|Vincula uma porta para uma interface de uma das partes do componente. Indica que as mensagens enviadas para o componente são tratadas pela parte ou que as mensagens enviadas da parte são enviadas do componente pai.|  
|(não mostrado)|**Generalização**|Indica que um componente herda de outro componente. Interfaces e partes são herdadas.|  
|9|Recolher/expandir controle|Use isto para ocultar ou mostrar as partes internas de um componente.|  
|(não mostrado)|**Comentário**|Para obter notas adicionais. Você pode vincular um comentário para qualquer número de elementos no diagrama usando o **conector** ferramenta.|  
  
## <a name="see-also"></a>Consulte também  
 [Editar modelos e diagramas UML](../modeling/edit-uml-models-and-diagrams.md)   
 [Diagramas de componente UML: diretrizes](../modeling/uml-component-diagrams-guidelines.md)   
 [Validar o sistema durante o desenvolvimento](../modeling/validate-your-system-during-development.md)   
 [Diagramas de caso de uso UML: referência](../modeling/uml-use-case-diagrams-reference.md)   
 [Diagramas de classe UML: referência](../modeling/uml-class-diagrams-reference.md)   
 [Diagramas de atividade UML: referência](../modeling/uml-activity-diagrams-reference.md)   
 [Diagramas de sequência UML: referência](../modeling/uml-sequence-diagrams-reference.md)


