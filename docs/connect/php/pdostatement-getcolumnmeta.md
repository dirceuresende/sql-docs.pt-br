---
title: 'Pdostatement:: Getcolumnmeta | Microsoft Docs'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: c92a21cc-8e53-43d0-a4bf-542c77c100c9
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8211a6a4cda4a5efa29b7379c24ba3fbbfa5458e
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37983004"
---
# <a name="pdostatementgetcolumnmeta"></a>PDOStatement::getColumnMeta
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Recupera metadados para uma coluna.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
array PDOStatement::getColumnMeta ( $column );  
```  
  
#### <a name="parameters"></a>Parâmetros  
*$conn*: (Inteiro) o número da coluna, com base em zero, cujos metadados que você deseja recuperar.  
  
## <a name="return-value"></a>Valor retornado  
Uma matriz associativa (chave e valor) que contém os metadados da coluna. Consulte a seção de comentários para obter uma descrição dos campos na matriz.  
  
## <a name="remarks"></a>Remarks  
A tabela a seguir descreve os campos na matriz retornada por getColumnMeta.  
  
|NAME|VALUES|  
|--------|----------|  
|native_type|Especifica o tipo do PHP para a coluna. Sempre cadeia de caracteres.|  
|driver:decl_type|Especifica o tipo do SQL usado para representar o valor da coluna no banco de dados. Se a coluna no conjunto de resultados é o resultado de uma função, esse valor não é retornado por PDOStatement::getColumnMeta.|  
|sinalizadores|Especifica os sinalizadores definidos para essa coluna. Sempre 0.|  
|NAME|Especifica o nome da coluna no banco de dados.|  
|table|Especifica o nome da tabela que contém a coluna no banco de dados. Sempre em branco.|  
|len|Especifica o comprimento da coluna.|  
|precisão|Especifica a precisão numérica dessa coluna.|  
|pdo_type|Especifica o tipo desta coluna, conforme representado pelas constantes PDO::PARAM_ *. Sempre PDO::PARAM_STR (2).|  
  
O suporte para PDO foi adicionado na versão 2.0 dos [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="example"></a>Exemplo  
  
```  
<?php  
$database = "AdventureWorks";  
$server = "(local)";  
$conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
$stmt = $conn->query("select * from Person.ContactType");  
$metadata = $stmt->getColumnMeta(2);  
var_dump($metadata);  
  
print $metadata['sqlsrv:decl_type'] . "\n";  
print $metadata['native_type'] . "\n";  
print $metadata['name'];  
?>  
```  
  
## <a name="see-also"></a>Consulte Também  
[PDOStatement Class](../../connect/php/pdostatement-class.md)

[PDO](http://php.net/manual/book.pdo.php)  
  
