---
title: Valores para declarações &lt;xsd:simpleType&gt; | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- xsd:simpleType declarations
ms.assetid: 557b972d-3af9-40bf-8382-72b05c9de1c1
caps.latest.revision: 13
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 14423da54a9890c7c286f5f997580f49931d1934
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37290312"
---
# <a name="values-for-ltxsdsimpletypegt-declarations"></a>Valores para declarações &lt;xsd:simpleType&gt;
  A tabela a seguir descreve as restrições aplicadas com base em todas as enumerações de tipo simples XSD reconhecidas.  
  
 Além disso, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não dá suporte para o valor NaN nas declarações **\<<xsd:simpleType>**. Esquemas que incluem valores NaN são rejeitados pelo servidor.  
  
|Tipo simples|Limitação|  
|-----------------|----------------|  
|`duration`|A parte do ano precisa estar dentro do intervalo de -2<sup>^</sup>31 a 2<sup>^</sup>31-1. O mês, o dia, a hora, o minuto e o segundo devem estar dentro do intervalo de 0 a 9999. A parte dos segundos tem três dígitos adicionais de precisão à direita da casa decimal.|  
|`dateTime`|A parte da hora no subcampo de fuso horário deve estar dentro do intervalo aceito de -14 a +14. A parte do ano deve estar dentro do intervalo de 1 a 9999. A parte do mês deve estar dentro do intervalo de 1 a 12. A parte do dia deve estar dentro do intervalo de 1 a 31 e deve ser uma data válida do calendário. Por exemplo, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detecta e retorna um erro para uma data inválida, como 1974-02-31, porque o mês de fevereiro não tem 31 dias.<br /><br /> O componente de segundos oferece suporte a precisão de 100 nonossegundos. A indicação de fuso horário é opcional.<br /><br /> O SQL Server 2005 oferecia suporte a anos no intervalo de -9999 a 9999. Atualmente, o SQL Server oferece suporte a um intervalo de anos mais restrito. Para obter mais informações, consulte [Comparar XML digitado com XML não digitado](compare-typed-xml-to-untyped-xml.md).|  
|`date`|A parte do ano deve estar dentro do intervalo de 1 a 9999. A parte do mês deve estar dentro do intervalo de 1 a 12. A parte do dia deve estar dentro do intervalo de 1 a 31 e deve ser uma data válida do calendário. Por exemplo, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detecta e retorna um erro para uma data inválida, como 1974-02-31, porque o mês de fevereiro não tem 31 dias.<br /><br /> O SQL Server 2005 oferecia suporte a anos no intervalo de -9999 a 9999. Atualmente, o SQL Server oferece suporte a um intervalo de anos mais restrito. Para obter mais informações, consulte [Comparar XML digitado com XML não digitado](compare-typed-xml-to-untyped-xml.md).|  
|`gYearMonth`|A parte do ano deve estar dentro do intervalo de -9999 a 9999.|  
|`gYear`|A parte do ano deve estar dentro do intervalo de -9999 a 9999.|  
|`gMonthDay`|A parte do mês deve estar dentro do intervalo de 1 a 12. A parte do dia deve estar dentro do intervalo de 1 a 31.|  
|`gDay`|A parte do dia deve estar dentro do intervalo de 1 a 31|  
|`gMonth`|A parte do mês deve estar dentro do intervalo de 1 a 12.|  
|`decimal`|Valores deste tipo devem estar de acordo com o formato do tipo numérico do SQL. Esse tipo representa internamente o suporte de números até um total de 38 dígitos, com 10 das posições desses dígitos reservadas para precisão fracional.|  
|`float`|Valores desse tipo devem estar de acordo com o formato do tipo `real` do SQL.|  
|**double**|Valores desse tipo devem estar de acordo com o formato do tipo `float` do SQL.|  
|`string`|Valores desse tipo devem estar de acordo com o formato do tipo `nvarchar(max)` do SQL.|  
|`anyURI`|Valores deste tipo não podem ter mais que 4000 caracteres Unicode de comprimento.|  
  
## <a name="see-also"></a>Consulte também  
 [Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
