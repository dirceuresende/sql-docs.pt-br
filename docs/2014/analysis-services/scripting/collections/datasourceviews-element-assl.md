---
title: Elemento DataSourceViews (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- DataSourceViews Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- DataSourceViews
helpviewer_keywords:
- DataSourceViews element
ms.assetid: f708ceac-8eeb-45ee-a2bb-919126898c80
caps.latest.revision: 35
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 869e404c4d9a46f4d3b4fc14b8f5dac46fd72304
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37187113"
---
# <a name="datasourceviews-element-assl"></a>Elemento DataSourceViews (ASSL)
  Contém a coleção de [DataSourceView](../objects/datasourceview-element-assl.md) elementos associados a um [banco de dados](../objects/database-element-assl.md) elemento.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Database>  
   ...  
   <DataSourceViews>  
      <DataSourceView>...</DataSourceView>  
   </DataSourceViews>  
   ...  
</Database>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-1: elemento opcional que pode ocorrer apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Banco de dados](../objects/database-element-assl.md)|  
|Elementos filho|[DataSourceView](../objects/datasourceview-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 O elemento correspondente no modelo de objeto Analysis Management Objects (AMO) é <xref:Microsoft.AnalysisServices.DataSourceViewCollection>.  
  
## <a name="see-also"></a>Consulte também  
 [Coleções &#40;ASSL&#41;](collections-assl.md)  
  
  
