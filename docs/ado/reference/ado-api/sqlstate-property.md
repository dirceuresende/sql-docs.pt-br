---
title: Propriedade SQLState | Microsoft Docs
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
- Error::GetSQLState
- Error::SQLState
- Error::get_SQLState
helpviewer_keywords:
- SQLState property
ms.assetid: f9e25967-54b0-444d-af2a-0d2c75365d3e
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 97aa3d77696162e99f94876a19083ce96d5773e5
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35281925"
---
# <a name="sqlstate-property"></a>Propriedade SQLState
Indica o estado do SQL para um determinado [erro](../../../ado/reference/ado-api/error-object.md) objeto.  
  
## <a name="return-value"></a>Valor retornado  
 Retorna os cinco caracteres **cadeia de caracteres** valor que segue o padrão SQL ANSI e indica o código de erro.  
  
## <a name="remarks"></a>Remarks  
 Use o **SQLState** propriedade para ler o código de erro de cinco caracteres que o provedor retorna quando ocorre um erro durante o processamento de uma instrução SQL. Por exemplo, ao usar o Microsoft OLE DB Provider para ODBC com um banco de dados do Microsoft SQL Server, os códigos de erro de estado SQL se originar de ODBC, com base em erros de ODBC específicos ou sobre os erros que se originam do Microsoft SQL Server e, em seguida, são mapeados para ODBC erros. Esses códigos de erro estão documentados no padrão ANSI SQL, mas podem ser implementados de maneira distinta por fontes de dados diferentes.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Error](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>Consulte também  
 [Descrição, HelpContext, HelpFile, NativeError, número, fonte e exemplo de propriedades de SQLState (VB)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Descrição, HelpContext, HelpFile, NativeError, número, fonte e exemplo de propriedades de SQLState (VC + +)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
