---
title: Comando Localizar nos Arquivos
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- edit.findinfiles
helpviewer_keywords:
- Edit.FindInFiles command
- find in files command
ms.assetid: 2fc78bfe-b339-4599-97f9-4cafd8a194d9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4cf5078bb16d90744b83dfd99cf0c1da663149a
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33705015"
---
# <a name="find-in-files-command"></a>Comando Localizar nos Arquivos
Pesquise arquivos usando um subconjunto das opções disponíveis na guia **Localizar nos Arquivos** da janela **Localizar e Substituir**.

## <a name="syntax"></a>Sintaxe

```cmd
Edit.FindinFiles findwhat [/case] [/ext:extensions]
[/lookin:searchpath] [/names] [/options] [/reset] [/stop] [/sub]
[/text2] [/wild|/regex] [/word]
```

## <a name="arguments"></a>Arguments
 `findwhat` Necessário. O texto a ser correspondido.

## <a name="switches"></a>Opções
 /case ou /c Opcional. As correspondências ocorrerão somente se os caracteres maiúsculos e minúsculos corresponderem exatamente aos especificados no argumento `findwhat`.

 /ext: `extensions` Opcional. Especifica as extensões de arquivo para os arquivos a serem pesquisados. Se não forem especificadas, a extensão anterior será usada, caso uma tenha sido inserida.

 /lookin: `searchpath` Opcional. Diretório a pesquisar. Se o caminho contiver espaços, coloque todo o caminho entre aspas.

 /names ou /n Opcional. Exibe uma lista de nomes de arquivos que contêm correspondências.

 /options ou /t Opcional. Exibe uma lista das configurações atuais da opção de localização e não realiza uma pesquisa.

 /regex ou /r Opcional. Usa caracteres especiais predefinidos no argumento `findwhat` como notações que representam padrões de texto, em vez de caracteres literais. Para obter uma lista completa de caracteres de expressão regular, consulte [Expressões Regulares](../../ide/using-regular-expressions-in-visual-studio.md).

 /reset ou /e Opcional. Retorna as opções de localização para suas configurações padrão e não realiza uma pesquisa.

 /stop Opcional. Interromperá a operação de pesquisa atual se houver uma em andamento. Pesquisar ignorará todos os outros argumentos quando `/stop` tiver sido especificado. Por exemplo, para interromper a pesquisa atual, você digitaria o seguinte:

```cmd
>Edit.FindinFiles /stop
```

 /sub ou /s Opcional. Procura as subpastas dentro do diretório especificado no argumento /lookin:`searchpath`.

 /text2 ou /2 Opcional. Exibe os resultados da pesquisa na janela Localizar Resultados 2.

 /wild ou /l Opcional. Usa caracteres especiais predefinidos no argumento `findwhat` como notações para representar um caractere ou uma sequência de caracteres.

 /word ou /w Opcional. Pesquisa somente palavras inteiras.

## <a name="example"></a>Exemplo
 Este exemplo procura btnCancel em todos os arquivos .cls localizados na pasta "Meus Projetos do Visual Studio" e exibe as informações de correspondência na Janela Localizar Resultados 2.

```cmd
>Edit.FindinFiles btnCancel /lookin:"c:/My Visual Studio Projects" /ext:*.cls /text2
```

## <a name="see-also"></a>Consulte também

- [Localizar em Arquivos](../../ide/find-in-files.md)
- [Janela Comando](../../ide/reference/command-window.md)
- [Caixa Localizar/Comando](../../ide/find-command-box.md)
- [Comandos do Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Aliases de comando do Visual Studio](../../ide/reference/visual-studio-command-aliases.md)