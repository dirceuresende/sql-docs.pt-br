---
title: Método setFailoverPartner (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerDataSource.setFailoverPartner
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 5310b7c2-9d10-474f-ad3a-218fe5da694b
caps.latest.revision: 17
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c6e08b2189e2eca12a44802ded59775b63a0fcb6
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32842281"
---
# <a name="setfailoverpartner-method-sqlserverdatasource"></a>Método setFailoverPartner (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define o nome do servidor de failover usado em uma configuração de espelhamento de banco de dados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void setFailoverPartner(java.lang.String serverName)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *nome do servidor*  
  
 Um **cadeia de caracteres** que contém o nome do servidor de failover.  
  
## <a name="remarks"></a>Remarks  
 O valor definido por este método é usado no caso de uma falha de conexão inicial com o servidor principal; depois que a conexão inicial é feita, este valor é ignorado. O [setDatabaseName](../../../connect/jdbc/reference/setdatabasename-method-sqlserverdatasource.md) método também deve ser usado em conjunto com este método ou uma exceção será lançada.  
  
 O driver não dá suporte à especificação do número de porta do servidor de failover quando o nome do servidor de failover é definido. No entanto, ao chamar o [setServerName](../../../connect/jdbc/reference/setservername-method-sqlserverdatasource.md) método e o [setInstanceName](../../../connect/jdbc/reference/setinstancename-method-sqlserverdatasource.md) método com o [setFailoverPartner](../../../connect/jdbc/reference/setfailoverpartner-method-sqlserverdatasource.md) método tem suporte.  
  
## <a name="see-also"></a>Consulte também  
 [Membros de SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Classe SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
