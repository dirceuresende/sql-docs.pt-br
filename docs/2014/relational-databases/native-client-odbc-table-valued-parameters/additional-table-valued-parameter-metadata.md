---
title: Metadados de parâmetro com valor de tabela adicionais | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), catalog functions to retrieve metadata
- table-valued parameters (ODBC), metadata
ms.assetid: 6c193188-5185-4373-9a0d-76cfc150c828
caps.latest.revision: 15
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4dbb77a586a08d0a8284a1c79f5ea8a2ef904c4c
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36013546"
---
# <a name="additional-table-valued-parameter-metadata"></a>Metadados adicionais de parâmetros com valor de tabela
  Para recuperar metadados para um parâmetro com valor de tabela, um aplicativo chama SQLProcedureColumns. Para um parâmetro com valor de tabela, SQLProcedureColumns retorna uma única linha. Dois adicionais [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-colunas específicas, SS_TYPE_CATALOG_NAME e SS_TYPE_SCHEMA_NAME, foram adicionadas para fornecer informações de esquema e catálogo para tipos de tabela associados com parâmetros com valor de tabela. Em conformidade com a especificação de ODBC, SS_TYPE_CATALOG_NAME e SS_TYPE_SCHEMA_NAME aparecem antes de todas as colunas específicas do driver adicionadas em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e depois de todas as colunas autorizadas pelo próprio ODBC.  
  
 A tabela a seguir lista as colunas significativas para parâmetros com valor de tabela.  
  
|Nome da coluna|Tipo de dados|Valor/comentários|  
|-----------------|---------------|---------------------|  
|DATA_TYPE|Smallint não NULL|SQL_SS_TABLE|  
|TYPE_NAME|WVarchar(128) não NULL|O nome do tipo do parâmetro com valor de tabela.|  
|COLUMN_SIZE|Integer|NULL|  
|BUFFER_LENGTH|Integer|0|  
|DECIMAL_DIGITS|Smallint|NULL|  
|NUM_PREC_RADIX|Smallint|NULL|  
|NULLABLE|Smallint não NULL|SQL_NULLABLE|  
|REMARKS|Varchar|NULL|  
|COLUMN_DEF|WVarchar(4000)|NULL|  
|SQL_DATA_TYPE|Smallint não NULL|SQL_SS_TABLE|  
|SQL_DATETIME_SUB|Smallint|NULL|  
|CHAR_OCTET_LENGTH|Integer|NULL|  
|ORDINAL_POSITION|Integer não NULL|A posição ordinal do parâmetro.|  
|IS_NULLABLE|Varchar|"YES"|  
|SS_TYPE_CATALOG_NAME|WVarchar(128) não NULL|O catálogo que contém a definição de tipo do tipo de tabela do parâmetro com valor de tabela.|  
|SS_TYPE_SCHEMA_NAME|WVarchar(128) não NULL|O esquema que contém a definição de tipo do tipo de tabela do parâmetro com valor de tabela.|  
  
 As colunas WVarchar são definidas como Varchar na especificação de ODBC, mas são retornadas de fato como WVarchar em todos os drivers ODBC recentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Esta alteração foi feita quando o suporte a Unicode foi adicionado à especificação de ODBC 3.5, mas não chamado explicitamente.  
  
 Para obter metadados adicionais para parâmetros com valor de tabela, um aplicativo usa as funções de catálogo SQLColumns e SQLPrimaryKeys. Antes de essas funções serem chamadas para parâmetros com valor de tabela, o aplicativo deve definir o atributo de instrução SQL_SOPT_SS_NAME_SCOPE como SQL_SS_NAME_SCOPE_TABLE_TYPE. Esse valor indica que o aplicativo exige metadados para um tipo de tabela em lugar de uma tabela real. O aplicativo passa então o TYPE_NAME do parâmetro com valor de tabela como o *TableName* parâmetro. SS_TYPE_CATALOG_NAME e SS_TYPE_SCHEMA_NAME são usados com o *CatalogName* e *SchemaName* parâmetros, respectivamente, para identificar o catálogo e o esquema para o parâmetro com valor de tabela. Quando um aplicativo concluir a recuperação de metadados para parâmetros com valor de tabela, ele deve definir SQL_SOPT_SS_NAME_SCOPE novamente com seu valor padrão SQL_SS_NAME_SCOPE_TABLE.  
  
 Quando SQL_SOPT_SS_NAME_SCOPE for definido como SQL_SS_NAME_SCOPE_TABLE, as consultas a servidores vinculados irão falhar. Chamadas para SQLColumns ou SQLPrimaryKeys com um catálogo que contém um componente de servidor falhará.  
  
## <a name="see-also"></a>Consulte também  
 [Parâmetros com valor de tabela &#40;ODBC&#41;](table-valued-parameters-odbc.md)  
  
  