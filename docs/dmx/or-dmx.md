---
title: OU (DMX) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- OR
dev_langs:
- DMX
helpviewer_keywords:
- OR operator
ms.assetid: 727a38a9-7f75-4963-8e8a-aa703c129d30
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 41cdd1638dc31eefa9cb034db33ef9d30162d617
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="or-dmx"></a>OR (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Operador lógico que executa uma disjunção lógica em duas expressões numéricas.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Expression1 OR Expression2  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *Expression1*  
 Expressão DMX (Data Mining Extensions) válida que retorna um valor numérico.  
  
 *Expression2*  
 Expressão DMX válida que retorna um valor numérico.  
  
## <a name="return-value"></a>Valor de retorno  
 Valor booliano que retorna TRUE quando um argumento ou todos os argumentos avaliarem TRUE; do contrário, FALSE.  
  
## <a name="remarks"></a>Comentários  
 Os argumentos são todos tratados como valores boolianos (0 como FALSE; do contrário, TRUE) antes que o operador realize a disjunção lógica. Se um ou ambos os argumentos forem avaliados como TRUE, o operador retornará TRUE. Se *Expression1* for avaliada como TRUE e *Expression2* for avaliada como FALSE, o operador retornará TRUE.  
  
 A tabela a seguir ilustra como a disjunção lógica é executada.  
  
|Se a Expression1 for|Se a Expression2 for|O valor de retorno será|  
|-----------------------|-----------------------|---------------------|  
|TRUE|TRUE|TRUE|  
|TRUE|FALSE|TRUE|  
|FALSE|TRUE|TRUE|  
|FALSE|FALSE|FALSE|  
  
## <a name="see-also"></a>Consulte também  
 [Extensões de mineração de dados &#40; DMX &#41; Referência de operador](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Lógica operadores &#40; DMX &#41;](../dmx/operators-logical.md)   
 [Operadores &#40; DMX &#41;](../dmx/operators-dmx.md)  
  
  
