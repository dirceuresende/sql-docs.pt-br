---
title: Usar variáveis no componente de Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], using variables
ms.assetid: 92d1881a-1ef1-43ae-b1ca-48d0536bdbc2
caps.latest.revision: 12
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 8556b2ceb0da2c533bead385380956351413aba2
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37291052"
---
# <a name="using-variables-in-the-script-component"></a>Usando variáveis no componente Script
  As variáveis armazenam valores que um pacote e seus contêineres, tarefas e manipuladores de eventos podem usar em tempo de execução. Para obter mais informações, consulte [Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md).  
  
 Você pode tornar as variáveis existentes disponíveis para somente leitura ou leitura/gravação acesso pelo seu script personalizado inserindo listas delimitada por vírgulas de variáveis na `ReadOnlyVariables` e `ReadWriteVariables` campos da **Script** página do **Editor de transformação scripts**. Lembre-se de que os nomes de variáveis diferenciam maiúsculas de minúsculas. Use a propriedade `Value` para ler e gravar em variáveis individuais. O componente Script trata qualquer bloqueio necessário em segundo plano, à medida que seu script manipula as variáveis em tempo de execução.  
  
> [!IMPORTANT]  
>  A coleção de `ReadWriteVariables` está disponível somente no método `PostExecute` para maximizar o desempenho e minimizar o risco de conflitos de bloqueio. Portanto, não será possível incrementar diretamente o valor de uma variável de pacote ao processar cada linha de dados. Em vez disso, incremente o valor de uma variável local e defina o valor da variável do pacote como o valor da variável local no método `PostExecute` depois de todos os dados terem sido processados. Você também pode usar a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A> para funcionar nesta limitação, conforme descrito posteriormente neste tópico. Entretanto, gravar diretamente em uma variável de pacote, à medida que cada linha for processada, afetará negativamente o desempenho e aumentará o risco de conflitos de bloqueio.  
  
 Para obter mais informações sobre o **Script** página do **Editor de transformação scripts**, consulte [Configurando o componente Script no Editor de componente Script] (( Configuring-the-script-Component-in-the-script-Component-Editor.MD) e [Editor de transformação scripts &#40;página de Script&#41;](../../script-transformation-editor-script-page.md).  
  
 O componente Script cria uma classe de coleção `Variables` no item de projeto `ComponentWrapper` com uma propriedade de acessador com rigidez de tipos para o valor de cada variável pré-configurada  onde a propriedade tem o mesmo nome que a variável em si. Esta coleção é exposta pela propriedade `Variables` da classe `ScriptMain`. A propriedade de acessador fornece permissão somente leitura ou de leitura/gravação ao valor da variável conforme apropriado. Por exemplo, se você tiver adicionado uma variável de inteiro nomeada `MyIntegerVariable` à lista `ReadOnlyVariables`, poderá recuperar seu valor em seu script utilizando o seguinte código:  
  
 `Dim myIntegerVariableValue As Integer = Me.Variables.MyIntegerVariable`  
  
 Você também pode usar a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A>, acessada chamando `Me.VariableDispenser`, para trabalhar com variáveis no componente Script. Neste caso você não está utilizando as propriedades de acessador digitadas e nomeadas para variáveis, mas acessando as variáveis diretamente. Ao usar o <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A>, você deve tratar as semânticas de bloqueio e a conversão de tipos de dados para obter valores variáveis em seu próprio código. Você deve usar a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A> em vez das propriedades de acessador nomeadas e tipadas, se desejar trabalhar com uma variável que não esteja disponível no tempo de design, mas é criada programaticamente no tempo de execução.  
  
![Ícone do Integration Services (pequeno)](../../media/dts-16.gif "ícone do Integration Services (pequeno)")**mantenha-se para cima até o momento com o Integration Services  **<br /> Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:<br /><br /> [Visite a página do Integration Services no MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.  
  
## <a name="see-also"></a>Consulte também  
 [Serviços de integração &#40;SSIS&#41; variáveis](../../integration-services-ssis-variables.md)   
 [Usar variáveis em pacotes](../../use-variables-in-packages.md)  
  
  
