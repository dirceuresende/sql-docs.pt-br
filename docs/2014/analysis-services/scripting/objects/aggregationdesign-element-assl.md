---
title: Elemento AggregationDesign (ASSL) | Microsoft Docs
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
- AggregationDesign Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- AggregationDesign
helpviewer_keywords:
- AggregationDesign element
ms.assetid: 80ad98d8-73a8-4353-b5ad-d2a9ac3bc531
caps.latest.revision: 36
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: cfebce28ae08d0d76fa851b9d9df3ded8f6c28fc
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37200086"
---
# <a name="aggregationdesign-element-assl"></a>Elemento AggregationDesign (ASSL)
  Define um conjunto de definições de agregação que podem ser compartilhadas entre várias partições de um banco de dados.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<AggregationDesigns>  
   <AggregationDesign>  
      <ID>...</ID>  
      <Name>...</Name>  
            <Description>...</Description>  
      <EstimatedRows>...</EstimatedRows>  
      <Dimensions>...</Dimensions>  
            <Aggregations>...</Aggregation>  
      <EstimatedPerformanceGain>...</EstimatedPerformanceGain>  
      <Annotations>...</Annotations>  
   </AggregationDesign>  
</AggregationDesigns>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-n: Elemento opcional que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[AggregationDesigns](../collections/aggregationdesigns-element-assl.md)|  
|Elementos filho|[As agregações](../collections/aggregations-element-assl.md), [anotações](../collections/annotations-element-assl.md), [descrição](../properties/description-element-assl.md), [dimensões](../collections/dimensions-element-assl.md), [EstimatedPerformanceGain](../properties/estimatedperformancegain-element-assl.md), [EstimatedRows](../properties/estimatedrows-element-assl.md), [ID](../properties/id-element-assl.md), [nome](../properties/name-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 O elemento correspondente no modelo de objeto Analysis Management Objects (AMO) é <xref:Microsoft.AnalysisServices.AggregationDesign>.  
  
## <a name="see-also"></a>Consulte também  
 [Elemento de partição &#40;ASSL&#41;](partition-element-assl.md)   
 [Elemento Aggregation &#40;ASSL&#41;](aggregation-element-assl.md)   
 [Elemento Aggregations &#40;ASSL&#41;](../collections/aggregations-element-assl.md)   
 [Objetos &#40;ASSL&#41;](objects-assl.md)  
  
  
