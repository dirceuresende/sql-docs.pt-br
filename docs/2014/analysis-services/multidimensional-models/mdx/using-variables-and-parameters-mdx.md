---
title: Usando variáveis e parâmetros (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [MDX]
- queries [MDX], variables
- queries [MDX], parameters
- variables [MDX]
ms.assetid: a4754d16-d9c4-49f6-9be0-392180b912e4
caps.latest.revision: 29
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 22adb713c5a75d4cf038e5683a6ddec8adbe836d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37266102"
---
# <a name="using-variables-and-parameters-mdx"></a>Usando variáveis e parâmetros (MDX)
  No [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], é possível parametrizar uma instrução MDX (Multidimensional Expressions). Uma instrução parametrizada permite a criação de instruções genéricas que podem ser personalizadas no tempo de execução.  
  
 Ao criar uma instrução parametrizada, você identifica o nome do parâmetro incluindo um prefixo ao nome com o sinal arroba (@). Por exemplo, @Year seria um nome de parâmetro válido  
  
 A linguagem MDX oferece suporte apenas a valores literais ou escalares. Para criar um parâmetro que faça referência a um membro, conjunto ou tupla, use uma função como [StrToMember](/sql/mdx/strtomember-mdx) ou [StrToSet](/sql/mdx/strtoset-mdx).  
  
 No XML a seguir, por exemplo Analysis (XMLA), o @CountryName parâmetro conterá o país em que o cliente para os dados são recuperados:  
  
```  
<Envelope xmlns="http://schemas.xmlsoap.org/soap/envelope/">  
  <Body>  
    <Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <Command>  
        <Statement>  
select [Measures].members on 0,   
       Filter(Customer.[Customer Geography].Country.members,   
              Customer.[Customer Geography].CurrentMember.Name =  
              @CountryName) on 1  
from [Adventure Works]  
</Statement>  
      </Command>  
      <Properties />  
      <Parameters>  
        <Parameter>  
          <Name>CountryName</Name>  
          <Value>'United Kingdom'</Value>  
        </Parameter>  
      </Parameters>  
    </Execute>  
  </Body>  
</Envelope>  
```  
  
 Para usar essa funcionalidade com OLE DB, você usaria o `ICommandWithParameters` interface. Para usar essa funcionalidade com ADOMD.Net, use a interface **AdomdCommand.Parameters** .  
  
## <a name="see-also"></a>Consulte também  
 [Conceitos básicos de script MDX &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md)  
  
  
