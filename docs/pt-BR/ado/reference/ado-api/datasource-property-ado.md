---
title: Propriedade de fonte de dados (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset20::DataSource
helpviewer_keywords:
- DataSource property [ADO]
ms.assetid: 300a702a-3544-48c5-b759-83b511fe97e0
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6bd018a74b39e644710ede5e5f002d543dac3f2c
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="datasource-property-ado"></a>Propriedade de fonte de dados (ADO)
Indica um objeto que contém dados a ser representado como um [registros](../../../ado/reference/ado-api/recordset-object-ado.md) objeto.  
  
## <a name="remarks"></a>Remarks  
 Essa propriedade é usada para criar controles associados a dados com o ambiente de dados. O ambiente de dados mantém a chamada de conjuntos de dados (fontes de dados) que contém objetos (membros de dados) que serão representados como um **registros** objeto *.*  
  
 O [DataMember](../../../ado/reference/ado-api/datamember-property.md) e **DataSource** propriedades devem ser usadas em conjunto.  
  
 O objeto referenciado deve implementar o **IDataSource** de interface e deve conter um **IRowset** interface.  
  
## <a name="usage"></a>Uso  
  
```  
Dim rs as New ADODB.Recordset  
rs.DataMember = "Command"     'Name of the rowset to bind to.  
Set rs.DataSource = myDE      'Name of the object containing an IRowset.  
```  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [Propriedade DataMember](../../../ado/reference/ado-api/datamember-property.md)