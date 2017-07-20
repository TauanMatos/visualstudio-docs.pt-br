---
title: "Instruções passo a passo: suporte Test-First com o Recurso Gerar do uso | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Generate From Usage
- Test-First Development
ms.assetid: 764c17a4-cd95-4c23-bf63-d92d9c5adfb2
caps.latest.revision: 63
author: kempb
ms.author: kempb
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: b5c18e7d208879498c1923403ec1bd213adffb5a
ms.contentlocale: pt-br
ms.lasthandoff: 05/24/2017

---
# <a name="walkthrough-test-first-support-with-the-generate-from-usage-feature"></a>Instruções passo a passo: suporte Test-First com a Funcionalidade Gerar a partir do Uso
Este tópico demonstra como usar o recurso [Gerar do Uso](../ide/visual-csharp-intellisense.md#generate-from-usage), que oferece suporte ao desenvolvimento de test-first.  
  
 O *desenvolvimento test-first* é uma abordagem para design de software em que você primeiro escreve testes de unidade baseados nas especificações do produto e, em seguida, escreve o código-fonte que é necessário para tornar os testes bem-sucedidos. O [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oferece suporte ao desenvolvimento de test-first gerando novos tipos e membros no código-fonte ao referenciá-los pela primeira vez em seus casos de teste antes de serem definidos.  
  
 O [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gera os novos tipos e membros com uma interrupção mínima no seu fluxo de trabalho. Você pode criar stubs para tipos, métodos, propriedades, campos ou construtores sem sair do seu local atual no código. Quando você abre uma caixa de diálogo para especificar as opções para a geração de tipo, o foco retorna imediatamente para o arquivo aberto no momento quando a caixa de diálogo é fechada.  
  
 O recurso Gerar do Uso pode ser usado com estruturas de teste que se integram com o [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. A Estrutura de Teste de unidade da Microsoft é demonstrada neste tópico.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-windows-class-library-project-and-a-test-project"></a>Para criar um projeto de Biblioteca de classes do Windows e um projeto de Teste  
  
1.  Em [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] ou em [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], crie um novo projeto de Biblioteca de Classes do Windows. Nomeie-o `GFUDemo_VB` ou `GFUDemo_CS`, dependendo de qual linguagem você está usando.  
  
2.  No **Gerenciador de Soluções**, clique com o botão direito do mouse no ícone da solução na parte superior, aponte para **Adicionar**e, em seguida, clique em **Novo Projeto**. Na caixa de diálogo **Novo Projeto**, no painel **Tipos de projeto** à esquerda, clique em **Testar**.  
  
3.  No painel **Modelos**, clique em **Projeto de teste de unidade** e aceite o nome padrão UnitTestProject1. A ilustração a seguir mostra a caixa de diálogo quando ele for exibido em [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]. Em [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], a caixa de diálogo tem aparência semelhante.  
  
     ![Caixa de diálogo Novo Projeto de Teste](../ide/media/newproject_test.png "NewProject_Test")  
Caixa de diálogo Novo Projeto  
  
4.  Clique em **OK** para fechar a caixa de diálogo **Novo Projeto**. Agora você está pronto para começar a escrever testes  
  
### <a name="to-generate-a-new-class-from-a-unit-test"></a>Para gerar uma nova classe de um teste de unidade  
  
1.  O projeto de teste contém um arquivo chamado UnitTest1. Clique duas vezes neste arquivo no **Gerenciador de Soluções** para abri-lo no Editor de Código. Uma classe de teste e um método de teste foram gerados.  
  
2.  Localize a declaração da classe `UnitTest1` e renomeie para `AutomobileTest`. No C#, se um construtor `UnitTest1()` estiver presente, renomeie-o para `AutomobileTest()`.  
  
    > [!NOTE]
    >  O IntelliSense agora fornece duas alternativas para o preenchimento de declaração do IntelliSense: *modo de preenchimento* e *modo de sugestão*. Use o modo de sugestão para situações nas quais classes e membros são usados antes de serem definidos. Quando uma janela do IntelliSense estiver aberta, você pode pressionar CTRL + ALT + BARRA DE ESPAÇOS para alternar entre o modo de preenchimento e o modo de sugestão. Consulte [Usando o IntelliSense](../ide/using-intellisense.md) para obter mais informações. O modo de sugestão ajudará quando você estiver digitando `Automobile` na próxima etapa.  
  
3.  Localize o método `TestMethod1()` e renomeie-o para `DefaultAutomobileIsInitializedCorrectly()`. Dentro desse método, crie uma nova instância de uma classe chamada `Automobile`, conforme mostrado nas ilustrações a seguir. Um sublinhado ondulado aparece, indicando um erro em tempo de compilação e uma marcação inteligente aparece sob o nome do tipo. O local exato da marcação inteligente varia, dependendo se você estiver usando [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ou [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].  
  
     ![Sublinhado de Marcação Inteligente no Visual Basic](../ide/media/genclass_underlinevb.png "GenClass_UnderlineVB")  
Visual Basic  
  
     ![Sublinhado de Marcação Inteligente no C&#35;](../ide/media/genclass_underline.png "GenClass_Underline")  
Visual C#  
  
4.  Pare o ponteiro do mouse sobre a marcação inteligente para ver uma mensagem de erro afirmando que nenhum tipo com nome `Automobile` foi definido. Clique na marcação inteligente ou pressione CTRL +. (CTRL + ponto) para abrir o menu de atalho Gerar do Uso, conforme mostrado nas ilustrações a seguir.  
  
     ![Menu de contexto de Marcação Inteligente no Visual Basic](../ide/media/genclass_smartvb.png "GenClass_SmartVB")  
Visual Basic  
  
     ![Menu de contexto de Marcação Inteligente no C&#35;](../ide/media/genclass_smartcs.png "GenClass_SmartCS")  
Visual C#  
  
5.  Agora você tem duas opções. Você pode clicar em **Gerar 'Classe Automobile'** para criar um novo arquivo no seu projeto de teste e preenchê-lo com uma classe vazia chamada `Automobile`. Essa é uma maneira rápida para criar uma nova classe em um novo arquivo que tenha os modificadores de acesso padrão no projeto atual. Você também pode clicar em **Gerar novo tipo** para abrir a caixa de diálogo **Gerar Novo Tipo**. Isso fornece opções que incluem colocar a classe em um arquivo existente e adicionar o arquivo em outro projeto.  
  
     Clique em **Gerar novo tipo** para abrir a caixa de diálogo **Gerar Novo Tipo** mostrada na ilustração a seguir. No lista **Projetos**, clique em **GFUDemo_VB** ou **GFUDemo_CS** para instruir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a adicionar o arquivo ao projeto de código-fonte em vez do projeto de teste.  
  
     ![Caixa de diálogo Gerar Novo Tipo](../ide/media/genotherdialog.png "GenOtherDialog")  
Caixa de diálogo Gerar Novo Tipo  
  
6.  Clique em **OK** para fechar a caixa de diálogo e criar o novo arquivo.  
  
7.  Em **Gerenciador de Soluções**, procure no nó de projeto GFUDemo_VB ou GFUDemo_CS para verificar se o novo arquivo Automobile.vb ou Automobile.cs está lá. No Editor de Código, o foco ainda está em `AutomobileTest.DefaultAutomobileIsInitializedCorrectly`. Você pode continuar a escrever seu teste com um mínimo de interrupção.  
  
### <a name="to-generate-a-property-stub"></a>Para gerar um stub de propriedade  
  
1.  Suponha que a especificação de produto afirma que a classe `Automobile` tem duas propriedades públicas chamadas `Model` e `TopSpeed`. Essas propriedades devem ser inicializadas com valores padrão de `"Not specified"` e `-1` pelo construtor padrão. O seguinte teste de unidade verificará para que o construtor padrão defina as propriedades para seus valores padrão corretos.  
  
     Adicione a seguinte linha de código em `DefaultAutomobileIsInitializedCorrectly`.  
  
     [!code-cs[VbTDDWalkthrough#1](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.cs)]  [!code-vb[VbTDDWalkthrough#1](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.vb)]  
  
     Com o código faz referência a duas propriedades indefinidas em `Automobile`, uma marcação inteligente é exibida. Clique na marcação inteligente para `Model` e, em seguida, clique em **Gerar stub de propriedade**. Gere um stub de propriedade para a propriedade `TopSpeed` também.  
  
     Na classe `Automobile`, os tipos das novas propriedades são inferidos corretamente do contexto.  
  
     A ilustração a seguir mostra o menu de atalho da marcação inteligente.  
  
     ![Gerar o menu de contexto Propriedades no Visual Basic](../ide/media/genpropertysmarttagvb.png "GenPropertySmartTagVB")  
Visual Basic  
  
     ![Gerar o menu de contexto Propriedades no C&#35;](../ide/media/genpropertysmarttagcs.png "GenPropertySmartTagCS")  
Visual C#  
  
### <a name="to-locate-the-source-code"></a>Para localizar o código-fonte  
  
1.  Use o recurso **Navegar Para** para navegar até o arquivo de código-fonte Automobile.cs ou Automobile.vb e verificar se as novas propriedades foram geradas.  
  
     O recurso **Navegar Para** permite inserir rapidamente uma cadeia de texto, como um nome de tipo ou parte de um nome, e ir até o local desejado clicando no elemento na lista de resultados.  
  
     Abra a caixa de diálogo **Navegar Para** clicando no Editor de Código e pressionando CTRL +, (CTRL + vírgula). Na caixa de texto, digite `automobile`. Clique na classe **Automobile** na lista e, em seguida, clique em **OK**.  
  
     A janela **Navegar Para** é mostrada na ilustração a seguir.  
  
     ![Caixa de diálogo Navegar Para](../ide/media/navigate_2.png "Navigate_2")  
Janela Navegar Para  
  
### <a name="to-generate-a-stub-for-a-new-constructor"></a>Para gerar um stub para um novo construtor  
  
1.  Nesse método de teste, você vai gerar um stub de construtor que inicializará as propriedades `Model` e `TopSpeed` para ter os valores que você especificar. Depois, você adicionará mais código para concluir o teste. Adicione também o seguinte método de teste à sua classe `AutomobileTest`.  
  
     [!code-cs[VbTDDWalkthrough#2](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.cs)]  [!code-vb[VbTDDWalkthrough#2](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.vb)]  
  
2.  Clique na marcação inteligente no novo construtor de classe e, em seguida, clique em **Gerar stub de construtor**. No arquivo de classe `Automobile`, observe que o novo construtor examinou os nomes das variáveis locais que são usadas na chamada do construtor, encontrou propriedades que têm os mesmos nomes na classe `Automobile` e forneceu código no corpo do construtor para armazenar os valores de argumento nas propriedades `Model` e `TopSpeed`. (Em [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], os campos `_model` e `_topSpeed` do novo construtor são campos de suporte implicitamente definidos para as propriedades `Model` e `TopSpeed`.)  
  
3.  Depois de gerar o novo construtor, um sublinhado ondulado aparece sob a chamada para o construtor padrão em `DefaultAutomobileIsInitializedCorrectly`. A mensagem de erro informa que a classe `Automobile` não tem nenhum construtor que assuma zero argumentos. Para gerar um construtor padrão explícito que não tem parâmetros, clique na marcação inteligente e, em seguida, clique em **Gerar stub de construtor**.  
  
### <a name="to-generate-a-stub-for-a-method"></a>Para gerar um stub para um método  
  
1.  Suponha que a especificação afirma que uma nova `Automobile` pode ser colocada em um estado de Execução se suas propriedades `Model` e `TopSpeed` forem definidas como algo diferente dos valores padrão. Adicione as seguintes linhas ao método `AutomobileWithModelNameCanStart`.  
  
     [!code-cs[VbTDDWalkthrough#3](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.cs)]  [!code-vb[VbTDDWalkthrough#3](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.vb)]  
  
2.  Clique na marcação inteligente da chamada de método `myAuto.Start` e, em seguida, clique em **Gerar stub de método**.  
  
3.  Clique na marcação inteligente da propriedade `IsRunning` e depois clique em **Gerar stub de propriedade**. A classe `Automobile` agora contém o código a seguir.  
  
     [!code-cs[VbTDDWalkthrough#4](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_4.cs)]  [!code-vb[VbTDDWalkthrough#4](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_4.vb)]  
  
### <a name="to-run-the-tests"></a>Para executar os testes  
  
1.  No menu **Teste de Unidade**, aponte para **Executar Testes de Unidade** e, em seguida, clique em **Todos os Testes**. Este comando executa todos os testes em todas as estruturas de teste que foram escritas para a solução atual.  
  
     Nesse caso, há dois testes e ambos falham conforme o esperado. O teste `DefaultAutomobileIsInitializedCorrectly` falha porque a condição `Assert.IsTrue` retorna `False`. O teste `AutomobileWithModelNameCanStart` falha porque o método `Start` na classe `Automobile` lança uma exceção.  
  
     A janela **Resultados do Teste** é mostrada na ilustração a seguir.  
  
     ![Resultados do teste que falharam](../ide/media/testsfailed.png "TestsFailed")  
Janela Resultados de Teste  
  
2.  Na janela **Resultados do Teste**, clique duas vezes em cada linha de resultado do teste para ir até o local de cada falha de teste.  
  
### <a name="to-implement-the-source-code"></a>Para implementar o código-fonte  
  
1.  Adicione o seguinte código ao construtor padrão de maneira que as propriedades `Model`, `TopSpeed` e `IsRunning` são inicializadas com seus valores padrão `"Not specified"`, `-1` e `True` (`true`).  
  
     [!code-cs[VbTDDWalkthrough#5](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.cs)]  [!code-vb[VbTDDWalkthrough#5](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.vb)]  
  
2.  Quando o método `Start` é chamado, ele deve definir o sinalizador `IsRunning` como true apenas se as propriedades `Model` ou `TopSpeed` estiverem definidas com valor diferente de seu valor padrão. Remova o `NotImplementedException` do corpo do método e adicione o código a seguir.  
  
     [!code-cs[VbTDDWalkthrough#6](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.cs)]  [!code-vb[VbTDDWalkthrough#6](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.vb)]  
  
### <a name="to-run-the-tests-again"></a>Para executar os testes novamente  
  
1.  No menu **Testar**, aponte para **Executar** e, em seguida, clique em **Todos os Testes na Solução**. Dessa vez os testes são aprovados. A janela **Resultados do Teste** é mostrada na ilustração a seguir.  
  
     ![Resultados de teste que foram aprovados](../ide/media/testspassed.png "TestsPassed")  
Janela Resultados de Teste  
  
## <a name="see-also"></a>Consulte também  
 [Gerar com base no uso](../ide/visual-csharp-intellisense.md#generate-from-usage)   
 [Escrevendo código](../ide/writing-code-in-the-code-and-text-editor.md)   
 [Usando o IntelliSense](../ide/using-intellisense.md)   
 [Efetuar teste de unidade em seu código](../test/unit-test-your-code.md)