---
title: Tipos de dados com suporte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7380ef0-c9d7-49e4-b6de-fad34752b9f3
caps.latest.revision: 20
author: stevestein
ms.author: sstein
manager: jhubbard
ms.openlocfilehash: 93c6555c1a8400306d40b2d3a719f280104ef582
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36118662"
---
# <a name="supported-data-types"></a>Tipos de dados com suporte
  Os tipos de dados a seguir têm **suporte** nas tabelas com otimização de memória e nos procedimentos armazenados compilados de modo nativo:  
  
 **Tipos de dados numéricos**  
  
|Tipo de dados|Para obter mais informações|  
|---------------|--------------------------|  
|INT|[int, bigint, smallint e tinyint &#40;Transact-SQL&#41;](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|BIGINT|[int, bigint, smallint e tinyint &#40;Transact-SQL&#41;](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|SMALLINT|[int, bigint, smallint e tinyint &#40;Transact-SQL&#41;](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|TINYINT|[int, bigint, smallint e tinyint &#40;Transact-SQL&#41;](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|Decimal|[decimal e numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|NUMERIC|[decimal e numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|FLOAT|[float e real &#40;Transact-SQL&#41;](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|REAL|[float e real &#40;Transact-SQL&#41;](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|money|[money e smallmoney &#40;Transact-SQL&#41;](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
|SMALLMONEY|[money e smallmoney &#40;Transact-SQL&#41;](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
  
 **Tipos de dados de cadeia de caracteres**  
  
|Tipo de dados|Para obter mais informações|  
|---------------|--------------------------|  
|char(n)|[char e varchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|varchar <sup>1</sup>|[char e varchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|nchar(n)|[nchar and nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|nvarchar <sup>1</sup>|[nchar and nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|sysname|[nchar and nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
  
 <sup>1</sup> limitação é 8060 bytes por total de linhas, contando (n) em tipos de comprimento variável.  
  
 Para obter informações sobre agrupamentos suportados, consulte [agrupamentos e páginas de código](../../database-engine/collations-and-code-pages.md).  
  
 **Tipos de dados de data e hora**  
  
|Tipo de dados|Para obter mais informações|  
|---------------|--------------------------|  
|Data|[data &#40;Transact-SQL&#41;](/sql/t-sql/data-types/date-transact-sql)|  
|time|[time &#40;Transact-SQL&#41;](/sql/t-sql/data-types/time-transact-sql)|  
|DATETIME|[datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql)|  
|datetime2|[datetime2 &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime2-transact-sql)|  
|smalldatetime|[smalldatetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/smalldatetime-transact-sql)|  
  
 **Tipos de dados binários**  
  
|Tipo de dados|Para obter mais informações|  
|---------------|--------------------------|  
|bit|[bit &#40;Transact-SQL&#41;](/sql/t-sql/data-types/bit-transact-sql)|  
|binary(n)|[binary e varbinary &#40;Transact-SQL&#41;](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
|varbinary <sup>1</sup>|[binary e varbinary &#40;Transact-SQL&#41;](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
  
 <sup>1</sup> limitação é 8060 bytes por total de linhas, contando (n) em tipos de comprimento variável.  
  
 **Outros tipos de dados**  
  
|Tipo de dados|Para obter mais informações|  
|---------------|--------------------------|  
|UNIQUEIDENTIFIER|[uniqueidentifier &#40;Transact-SQL&#41;](/sql/t-sql/data-types/uniqueidentifier-transact-sql)|  
  
 **Tipos de dados sem suporte**  
  
 Não há suporte para os seguintes tipos de dados:  
  
||||  
|-|-|-|  
|DATETIMEOFFSET|GEOGRAPHY|GEOMETRY|  
|HIERARCHYID|Objetos Grandes (LOBs). Por exemplo, varchar(max), nvarchar(max), varbinary(max), image, xml, text e ntext.|ROWVERSION|  
|sql_variant|Funções CLR|Tipos definidos pelo usuário (UDTs)|  
  
## <a name="see-also"></a>Consulte também  
 [Suporte ao Transact-SQL para OLTP na memória](transact-sql-support-for-in-memory-oltp.md)   
 [Implementando Colunas LOB em uma tabela com otimização de memória](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md)   
 [Implementando SQL_VARIANT em uma tabela com otimização de memória](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
  