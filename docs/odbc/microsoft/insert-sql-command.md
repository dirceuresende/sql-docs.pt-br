---
title: Insira - o comando SQL | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- INSERT [ODBC]
ms.assetid: 9b648198-349f-46f6-b869-13d129945971
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 881ee4d74eab6b1e26b1f3ec243a39c08125ea00
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32900681"
---
# <a name="insert---sql-command"></a>Insira - o comando SQL
Acrescenta um registro para o final de uma tabela que contém os valores do campo especificado.  
  
 O Driver de ODBC do Visual FoxPro oferece suporte a sintaxe de linguagem do Visual FoxPro nativo para este comando. Para obter informações específicas do driver, consulte os comentários.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
INSERT INTO dbf_name [(fname1 [, fname2, ...])]  
   VALUES (eExpression1 [, eExpression2, ...])  
```  
  
## <a name="arguments"></a>Argumentos  
 INSERT INTO *dbf_name*  
 Especifica o nome da tabela para o qual o novo registro é adicionado. *dbf_name* pode incluir um caminho e pode ser uma expressão de nome.  
  
 Se a tabela que você especificar não estiver aberta, ele está sendo usado exclusivamente em uma nova área de trabalho e o novo registro é acrescentado à tabela. A nova área de trabalho não estiver selecionada. a área de trabalho atual permanece selecionada.  
  
 Se a tabela que você especificar for aberta, INSERT acrescenta o novo registro à tabela. Se a tabela é aberta em uma área de trabalho diferente de área de trabalho atual, ele não é selecionado depois que o registro é anexado; a área de trabalho atual permanece selecionada.  
  
 [( *fname1*[, *fname2*[,...]])]  
 Especifica o novo registro, os nomes dos campos no qual os valores são inseridos.  
  
 VALORES ( *eExpression1*[, *eExpression2*[,...]])  
 Especifica os valores de campo inseridos no novo registro. Se você omitir os nomes de campo, você deve especificar os valores de campo na ordem definida pela estrutura de tabela.  
  
## <a name="remarks"></a>Remarks  
 O novo registro contém os dados listados na cláusula VALUES.  
  
## <a name="driver-remarks"></a>Comentários de driver  
 Quando o aplicativo envia a instrução INSERT do ODBC SQL para a fonte de dados, o Driver de ODBC do Visual FoxPro converte o comando para o comando FoxProINSERT Visual sem conversão.  
  
## <a name="see-also"></a>Consulte também  
 [Criar tabela - comando SQL](../../odbc/microsoft/create-table-sql-command.md)   
 [SELECT – comando SQL](../../odbc/microsoft/select-sql-command.md)
