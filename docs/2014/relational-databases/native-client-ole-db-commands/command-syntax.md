---
title: Sintaxe de comando | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, commands
- commands [OLE DB]
- SQL Server Native Client OLE DB provider, stored procedures
- stored procedures [OLE DB], command syntax
ms.assetid: d463d3d7-e5cb-426d-8e92-aa29980356b6
caps.latest.revision: 32
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4c8b0f5c1798d0547bf7a1acc6ef97c93660cd89
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37423485"
---
# <a name="command-syntax"></a>Sintaxe de comando
  O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client reconhece a sintaxe de comando especificada pela macro DBGUID_SQL. Para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client, o especificador indica que um amálgama de ODBC SQL, ISO, e [!INCLUDE[tsql](../../includes/tsql-md.md)] é uma sintaxe válida. Por exemplo, a seguinte instrução SQL usa uma sequência de escape do ODBC SQL para especificar a função de cadeia de caracteres LCASE:  
  
```  
SELECT customerid={fn LCASE(CustomerID)} FROM Customers  
```  
  
 LCASE retorna uma cadeia de caracteres, convertendo todos os caracteres em maiúscula aos seus equivalentes em minúsculas. A função LOWER de cadeia de caracteres ISO executa a mesma operação, assim a seguinte instrução SQL é uma equivalente ISO para a instrução ODBC apresentada acima:  
  
```  
SELECT customerid=LOWER(CustomerID) FROM Customers  
```  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client processa qualquer formulário da instrução com êxito quando especificado como o texto para um comando.  
  
## <a name="stored-procedures"></a>Procedimentos armazenados  
 Ao executar uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o procedimento de armazenado um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor OLE DB do Native Client de comando, use a sequência de escape CALL do ODBC no texto do comando. O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client, em seguida, usa o mecanismo de chamada de procedimento remoto de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para otimizar o processamento do comando. Por exemplo, a seguinte instrução SQL do ODBC é o texto de comando preferido à forma do [!INCLUDE[tsql](../../includes/tsql-md.md)]:  
  
-   ODBC SQL  
  
    ```  
    {call SalesByCategory('Produce', '1995')}  
    ```  
  
-   Transact-SQL  
  
    ```  
    EXECUTE SalesByCategory 'Produce', '1995'  
    ```  
  
## <a name="see-also"></a>Consulte também  
 [Comandos](commands.md)  
  
  
