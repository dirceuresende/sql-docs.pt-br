---
title: Propriedade NumericScale (ADOX) | Microsoft Docs
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
- _Column::PutNumericScale
- _Column::GetNumericScale
- _Column::NumericScale
- _Column::put_NumericScale
- _Column::get_NumericScale
helpviewer_keywords:
- NumericScale property [ADOX]
ms.assetid: 573ee5d1-57c7-4a27-be79-a0e12944ad9b
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 7bbe61177e9af6db7d3c663e18afd01b4f2b951e
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35286715"
---
# <a name="numericscale-property-adox"></a>Propriedade NumericScale (ADOX)
Indica a escala de um valor numérico na coluna.  
  
## <a name="settings-and-return-values"></a>Configurações e valores de retorno  
 Define e retorna um **bytes** valor que é a escala de valores de dados na coluna quando o [tipo](../../../ado/reference/adox-api/type-property-column-adox.md) é de propriedade **adNumeric** ou **adDecimal**. **NumericScale** é ignorado para todos os outros tipos de dados.  
  
## <a name="remarks"></a>Remarks  
 O valor padrão é zero (0).  
  
 **NumericScale** é somente leitura para [coluna](../../../ado/reference/adox-api/column-object-adox.md) já está anexados a uma coleção de objetos.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Column (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de código ADOX: NumericScale e exemplo de propriedades de precisão (VB)](../../../ado/reference/adox-api/adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Propriedade Type (Column) (ADOX)](../../../ado/reference/adox-api/type-property-column-adox.md)
