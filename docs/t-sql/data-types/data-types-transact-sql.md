---
title: Tipos de dados (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/23/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- system data types [SQL Server]
- data types [SQL Server]
- data types [SQL Server], about data types
ms.assetid: a54f7373-b247-4d61-8fb8-7f2ec7a8d0a4
caps.latest.revision: 45
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 8220765c51455b20a12439c18dcd2fb4bde6bb3d
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---

# <a name="data-types-transact-sql"></a>Tipos de dados (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], cada coluna, variável local, expressão e parâmetro tem um tipo de dados relacionado. O tipo de dados é um atributo que especifica o tipo de dados que o objeto pode manter: dados inteiros, dados de caractere, dados monetários, data e hora, cadeiasx de caracteres binárias etc.
  
O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece um conjunto de tipos de dados do sistema que define todos os tipos de dados que podem ser usados com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Você também pode definir seus próprios tipos de dados em [!INCLUDE[tsql](../../includes/tsql-md.md)] ou [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]. Os tipos de dados de alias têm como base os tipos de dados fornecidos pelo sistema. Para obter mais informações sobre tipos de dados de alias, consulte [CREATE TYPE &#40; Transact-SQL &#41; ](../../t-sql/statements/create-type-transact-sql.md). Os tipos definidos pelo usuário obtêm características dos métodos e operadores de uma classe criada com o uso de uma das linguagens de programação oferecidas por [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].
  
Quando duas expressões que possuem diferentes tipos de dados, agrupamentos, precisão, escala ou comprimento são combinadas por um operador, as características do resultado são determinadas pelo seguinte:
-   O tipo de dados do resultado é determinado pela aplicação das regras de precedência de tipos de dados em relação aos tipos de dados de expressões de entrada. Para obter mais informações, veja [Precedência de tipo de dados &#40;Transact-SQL&#41;](../../t-sql/data-types/data-type-precedence-transact-sql.md).  
-   O agrupamento do resultado é determinado pelas regras de precedência de agrupamento quando o tipo de dados do resultado é **char**, **varchar**, **texto**, **nchar**, **nvarchar**, ou **ntext**. Para obter mais informações, consulte [precedência de agrupamento &#40; Transact-SQL &#41; ](../../t-sql/statements/collation-precedence-transact-sql.md).  
-   A precisão, a escala e o tamanho do resultado dependem da precisão, da escala e do tamanho das expressões de entrada. Para obter mais informações, consulte [Precisão, escala e comprimento &#40;Transact-SQL&#41;](../../t-sql/data-types/precision-scale-and-length-transact-sql.md).  
  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]oferece sinônimos de tipos de dados para compatibilidade com ISO. Para obter mais informações, consulte [sinônimos de tipos de dados &#40; Transact-SQL &#41; ](../../t-sql/data-types/data-type-synonyms-transact-sql.md).
  
## <a name="data-type-categories"></a>Categorias de tipo de dados
Tipos de dados em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são organizados nas seguintes categorias:
  
|||  
|-|-|  
|Numéricos exatos|Cadeias de caracteres Unicode|  
|Numéricos aproximados|Cadeia de caracteres binária|  
|Data e hora|Outros tipos de dados|  
|Cadeias de caracteres||  
  
Em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], com base em suas características de armazenamento, alguns tipos de dados são designados como pertencendo aos seguintes grupos:
-   Tipos de dados de valor grande: **varchar (max)**, e **nvarchar (max)**  
-   Tipos de dados de objeto grande: **texto**, **ntext**, **imagem**, **varbinary (max)**, e **xml**  
  
    > [!NOTE]  
    >  sp_help retorna -1 como o comprimento de valor grande e **xml** tipos de dados.  
  
### <a name="exact-numerics"></a>Numéricos exatos
  
|||  
|-|-|  
|[bigint](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md)|[numeric](../../t-sql/data-types/decimal-and-numeric-transact-sql.md)|  
|[bit](../../t-sql/data-types/bit-transact-sql.md)|[smallint](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md)|  
|[decimal](../../t-sql/data-types/decimal-and-numeric-transact-sql.md)|[smallmoney](../../t-sql/data-types/money-and-smallmoney-transact-sql.md)|  
|[int](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md)|[tinyint](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md)|  
|[money](../../t-sql/data-types/money-and-smallmoney-transact-sql.md)||  
  
### <a name="approximate-numerics"></a>Numéricos aproximados
  
|||  
|-|-|  
|[float](../../t-sql/data-types/float-and-real-transact-sql.md)|[real](../../t-sql/data-types/float-and-real-transact-sql.md)|  
  
### <a name="date-and-time"></a>Data e hora
  
|||  
|-|-|  
|[date](../../t-sql/data-types/date-transact-sql.md)|[datetimeoffset](../../t-sql/data-types/datetimeoffset-transact-sql.md)|  
|[datetime2](../../t-sql/data-types/datetime2-transact-sql.md)|[smalldatetime](../../t-sql/data-types/smalldatetime-transact-sql.md)|  
|[datetime](../../t-sql/data-types/datetime-transact-sql.md)|[time](../../t-sql/data-types/time-transact-sql.md)|  
  
### <a name="character-strings"></a>Cadeias de caracteres
  
|||  
|-|-|  
|[char](../../t-sql/data-types/char-and-varchar-transact-sql.md)|[varchar](../../t-sql/data-types/char-and-varchar-transact-sql.md)|  
|[texto](../../t-sql/data-types/ntext-text-and-image-transact-sql.md)||  
  
### <a name="unicode-character-strings"></a>Cadeias de caracteres Unicode
  
|||  
|-|-|  
|[nchar](../../t-sql/data-types/nchar-and-nvarchar-transact-sql.md)|[nvarchar](../../t-sql/data-types/nchar-and-nvarchar-transact-sql.md)|  
|[ntext](../../t-sql/data-types/ntext-text-and-image-transact-sql.md)||  
  
### <a name="binary-strings"></a>Cadeia de caracteres binária
  
|||  
|-|-|  
|[binary](../../t-sql/data-types/binary-and-varbinary-transact-sql.md)|[varbinary](../../t-sql/data-types/binary-and-varbinary-transact-sql.md)|  
|[imagem](../../t-sql/data-types/ntext-text-and-image-transact-sql.md)||  
  
### <a name="other-data-types"></a>Outros tipos de dados
  
|||  
|-|-|  
|[cursor](../../t-sql/data-types/cursor-transact-sql.md)|[timestamp](../../t-sql/data-types/rowversion-transact-sql.md)|  
|[hierarchyid](../../t-sql/data-types/hierarchyid-data-type-method-reference.md)|[uniqueidentifier](../../t-sql/data-types/uniqueidentifier-transact-sql.md)|  
|[sql_variant](../../t-sql/data-types/sql-variant-transact-sql.md)|[xml](../../t-sql/xml/xml-transact-sql.md)|  
|[table](../../t-sql/data-types/table-transact-sql.md)|[Tipos espaciais](http://msdn.microsoft.com/library/d1715574-34b1-4ce5-a29f-25e35027a54c)|  
  
## <a name="see-also"></a>Consulte também
[CREATE PROCEDURE &#40;Transact-SQL&#41;](../../t-sql/statements/create-procedure-transact-sql.md)  
[CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)  
[DECLARAR @local_variable &#40; Transact-SQL &#41; ](../../t-sql/language-elements/declare-local-variable-transact-sql.md) 
 [EXECUTE &#40; Transact-SQL &#41;](../../t-sql/language-elements/execute-transact-sql.md)  
[Expressões &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)  
[Funções &#40; Transact-SQL &#41;](../../t-sql/functions/functions.md)  
[COMO &#40; Transact-SQL &#41;](../../t-sql/language-elements/like-transact-sql.md)  
[sp_droptype &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-droptype-transact-sql.md)  
[sp_help &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-transact-sql.md)  
[sp_rename &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-rename-transact-sql.md)
  
  
