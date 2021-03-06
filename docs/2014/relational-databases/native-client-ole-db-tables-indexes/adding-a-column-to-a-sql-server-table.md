---
title: Adicionar uma coluna a uma tabela do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- AddColumn function
- SQL Server Native Client OLE DB provider, columns
- adding columns
ms.assetid: 22bae18a-bc9d-4617-8660-ed8b17a468d4
caps.latest.revision: 29
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e79886f09783737a392fa67899feb59cd7deb2a1
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37425265"
---
# <a name="adding-a-column-to-a-sql-server-table"></a>Adicionando uma coluna a uma tabela do SQL Server
  O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor do OLE DB do Native Client expõe a **itabledefinition:: addColumn** função. Isso permite aos consumidores adicionar uma coluna para um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela.  
  
 Quando você adiciona uma coluna para uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor OLE DB do Native Client é restringido da seguinte forma:  
  
-   Caso DBPROP_COL_AUTOINCREMENT seja VARIANT_TRUE, DBPROP_COL_NULLABLE deve ser VARIANT_FALSE.  
  
-   Se a coluna é definida usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp** tipo de dados, DBPROP_COL_NULLABLE deve ser VARIANT_FALSE.  
  
-   Para qualquer outra definição de coluna, DBPROP_COL_NULLABLE deve ser VARIANT_TRUE.  
  
 Os consumidores especificam o nome da tabela como uma cadeia de caracteres Unicode na *pwszName* membro do *uName* união no *pTableID* parâmetro. O *eKind* membro *pTableID* deve ser DBKIND_NAME.  
  
 O nome da nova coluna é especificado como uma cadeia de caracteres Unicode na *pwszName* membro do *uName* união no *dbcid* membro do parâmetro DBCOLUMNDESC *pColumnDesc*. O *eKind* membro deve ser DBKIND_NAME.  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas e índices](tables-and-indexes.md)   
 [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
