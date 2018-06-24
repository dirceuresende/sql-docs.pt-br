---
title: Elemento QueryNotification (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- QueryNotification Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
helpviewer_keywords:
- QueryNotification element
ms.assetid: 0ee06730-81ff-4913-96e6-f39b6f181650
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 3c9bc13772d549d6ade640af4c3f57ac52efbbec
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36118735"
---
# <a name="querynotification-element-assl"></a>Elemento QueryNotification (ASSL)
  Contém informações para o elemento [ProactiveCaching](proactivecaching-element-assl.md) sobre a consulta a ser executada para determinar se uma fonte de dados foi modificada.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<QueryNotifications>  
   <QueryNotification>  
      <Query>...</Query>  
...</QueryNotification>  
</QueryNotifications>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|1-n: elemento obrigatório que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[QueryNotifications](../collections/querynotifications-element-assl.md)|  
|Elementos filho|[Consulta](../properties/query-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 O elemento correspondente no modelo de objeto Analysis Management Objects (AMO) é <xref:Microsoft.AnalysisServices.QueryNotification>.  
  
## <a name="see-also"></a>Consulte também  
 [Tipo de dados ProactiveCachingQueryBinding &#40;ASSL&#41;](../data-type/binding-data-type-assl.md)   
 [Objetos &#40;ASSL&#41;](objects-assl.md)  
  
  