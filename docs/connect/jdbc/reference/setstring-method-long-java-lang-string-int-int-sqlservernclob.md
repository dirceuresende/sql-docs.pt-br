---
title: Método setString (long, Java, int, int) - NClob | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 2d5e9f50-15b2-4c76-8bfc-3b5be49c2781
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d38e6265e5516f92155b4e69d7e7b2c61b8f2bd0
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32844041"
---
# <a name="setstring-method-long-javalangstring-int-int-sqlservernclob"></a>Método setString (long, java.lang.String, int, int) (SQLServerNClob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Grava a cadeia de caracteres especificada para o NCLOB começando na posição especificada, com base no comprimento e deslocamento especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
int setString(long pos,  
              java.lang.String str,  
              int offset,  
              int len)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *POS*  
  
 A posição na qual iniciar a gravação de **NCLOB**; a primeira posição é 1.  
  
 *STR*  
  
 A cadeia de caracteres a serem gravados para o **NCLOB**.  
  
 *offset*  
  
 O deslocamento em *str* para iniciar a leitura dos caracteres a serem gravados.  
  
 *len*  
  
 O número de caracteres a serem gravados.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Esse método setString é especificado pelo método setString na interface Java.SQL. NCLOB.  
  
## <a name="see-also"></a>Consulte também  
 [Métodos SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-methods.md)   
 [Membros SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-members.md)   
 [Classe SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-class.md)  
  
  
