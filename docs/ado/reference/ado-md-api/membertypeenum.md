---
title: MemberTypeEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- MemberTypeEnum
helpviewer_keywords:
- MemberTypeEnum enumeration [ADO MD]
ms.assetid: 5d8132c0-7ca2-4f86-8336-1b34213869ad
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2d98b66ad2941d34f15d49d146cea622e4d39457
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35284687"
---
# <a name="membertypeenum"></a>MemberTypeEnum
Especifica a configuração para o [tipo](../../../ado/reference/ado-md-api/type-property-ado-md.md) propriedade de um [membro](../../../ado/reference/ado-md-api/member-object-ado-md.md) objeto.  
  
|Constante|Valor|Description|  
|--------------|-----------|-----------------|  
|**adMemberAll**|4|Indica que o **membro** objeto representa todos os membros do nível.|  
|**adMemberFormula**|3|Indica que o **membro** objeto é calculado usando uma expressão de fórmula.|  
|**adMemberMeasure**|2|Indica que o **membro** objeto pertence a dimensão de medidas e representa um atributo quantitativo.|  
|**adMemberRegular**|1|Padrão. Indica que o **membro** objeto representa uma instância de uma entidade de negócios.|  
|**adMemberUnknown**|0|Não é possível determinar o tipo do membro.|
