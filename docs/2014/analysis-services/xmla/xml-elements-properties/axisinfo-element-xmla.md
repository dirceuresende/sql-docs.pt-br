---
title: Elemento AxisInfo (XMLA) | Microsoft Docs
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
- AxisInfo Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#AxisInfo
- microsoft.xml.analysis.axisinfo
- http://schemas.microsoft.com/analysisservices/2003/engine#AxisInfo
helpviewer_keywords:
- AxisInfo element
ms.assetid: 060741db-b2ec-4174-9277-58d996440a88
caps.latest.revision: 12
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 36eb4542923f9be42c0a114fb198c1efb1285a26
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37243456"
---
# <a name="axisinfo-element-xmla"></a>Elemento AxisInfo (XMLA)
  Representa os metadados de um único eixo contido pelo pai [AxesInfo](axesinfo-element-xmla.md) elemento.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<AxesInfo>  
   ...  
   <AxisInfo name="string">  
      <HierarchyInfo>...</HierarchyInfo>  
   </AxisInfo>  
   ...  
</AxesInfo>  
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
|Elementos pai|[AxesInfo](axesinfo-element-xmla.md)|  
|Elementos filho|[HierarchyInfo](hierarchyinfo-element-xmla.md)|  
  
## <a name="attributes"></a>Atributos  
  
|attribute|Description|  
|---------------|-----------------|  
|Nome|Necessário `String` atributo. O nome do eixo.|  
  
## <a name="remarks"></a>Remarks  
 Em um elemento `root` que usa o objeto `MDDataSet`, um elemento `AxisInfo` contém uma coleção de elementos `HierarchyInfo` que, combinados com o valor do atributo `name`, representa a definição de um único eixo retornado no conjunto de dados multidimensional.  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40;XMLA&#41;](xml-elements-properties.md)  
  
  
