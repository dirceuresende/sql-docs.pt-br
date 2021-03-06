---
title: JSON_QUERY (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/02/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: douglasl
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- JSON_QUERY
- JSON_QUERY_TSQL
helpviewer_keywords:
- JSON, extracting
- JSON, querying
- JSON_QUERY function
ms.assetid: 1ab0d90f-19b6-4988-ab4f-22fdf28b7c79
author: jovanpop-msft
ms.author: jovanpop
manager: craigg
ms.openlocfilehash: 5b2436f7ed1f8c32ba0d9b69f9d98e7092d340f7
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38022821"
---
# <a name="jsonquery-transact-sql"></a>JSON_QUERY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

 Extrai um objeto ou uma matriz de uma cadeia de caracteres JSON.  
  
 Para extrair um valor escalar de uma cadeia de caracteres JSON em vez de um objeto ou uma matriz, confira [JSON_VALUE &#40;Transact-SQL&#41;](../../t-sql/functions/json-value-transact-sql.md). Para obter informações sobre as diferenças entre **JSON_VALUE** e **JSON_QUERY**, confira [Comparar JSON_VALUE e JSON_QUERY](../../relational-databases/json/validate-query-and-change-json-data-with-built-in-functions-sql-server.md#JSONCompare).  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```sql  
JSON_QUERY ( expression [ , path ] )  
```  
  
## <a name="arguments"></a>Argumentos  
 *expressão*  
 Uma expressão. Normalmente, o nome de uma variável ou de uma coluna que contém o texto JSON.  
  
 Se **JSON_QUERY** localizar um JSON que não seja válido na *expressão* antes de encontrar o valor identificado por *path*, a função retornará um erro. Se **JSON_QUERY** não encontrar o valor identificado por *path*, ele verificará todo o texto e retornará um erro se encontrar um JSON que não seja válido em algum lugar na *expressão*.  
  
 *path*  
 Um demarcador JSON que especifica o objeto ou a matriz a ser extraída.

No [!INCLUDE[ssSQLv14_md](../../includes/sssqlv14-md.md)] e no [!INCLUDE[ssSDSfull_md](../../includes/sssdsfull-md.md)], você pode fornecer uma variável como o valor de *path*.

O demarcador JSON pode especificar o modo incerto ou estrito para análise. Se você não especificar o modo de análise, o modo incerto será o padrão. Para obter mais informações, confira [Expressões de demarcador JSON &#40;SQL Server&#41;](../../relational-databases/json/json-path-expressions-sql-server.md).  

O valor padrão para *path* é '$'. Como resultado, se você não fornecer um valor para *path*, **JSON_QUERY** retornará a *expressão* de entrada.

Se o formato de *path* não for válido, **JSON_QUERY** retornará um erro.  
  
## <a name="return-value"></a>Valor retornado  
 Retorna um fragmento JSON do tipo nvarchar(max). O agrupamento do valor retornado é o mesmo que o agrupamento da expressão de entrada.  
  
 Se o valor não for um objeto nem uma matriz:  
  
-   No modo incerto **JSON_QUERY** retornará nulo.  
  
-   No modo estrito, **JSON_QUERY** retornará um erro.  
  
## <a name="remarks"></a>Remarks  

### <a name="lax-mode-and-strict-mode"></a>Modo incerto e modo estrito

 Considere o seguinte texto JSON:  
  
```json  
{
    "info": {
        "type": 1,
        "address": {
            "town": "Bristol",
            "county": "Avon",
            "country": "England"
        },
        "tags": ["Sport", "Water polo"]
    },
    "type": "Basic"
} 
```  
  
 A tabela a seguir compara o comportamento de **JSON_QUERY** no modo incerto e no modo estrito. Para obter mais informações sobre a especificação de modo de demarcador opcional (incerto ou estrito), confira [Expressões de demarcador JSON &#40;SQL Server&#41;](../../relational-databases/json/json-path-expressions-sql-server.md).  
  
|Caminho|Valor retornado no modo incerto|Valor retornado no modo estrito|Obter mais informações|  
|----------|------------------------------|---------------------------------|---------------|  
|$|Retorna o texto JSON inteiro.|Retorna o texto JSON inteiro.|N/A|  
|$.info.type|NULL|Erro|Não é um objeto nem uma matriz.<br /><br /> Use **JSON_VALUE** nesse caso.|  
|$.info.address.town|NULL|Erro|Não é um objeto nem uma matriz.<br /><br /> Use **JSON_VALUE** nesse caso.|  
|$.info."address"|N'{ "town":"Bristol", "county":"Avon", "country":"England" }'|N'{ "town":"Bristol", "county":"Avon", "country":"England" }'|N/A|  
|$.info.tags|N'[ "Sport", "Water polo"]'|N'[ "Sport", "Water polo"]'|N/A|  
|$.info.type[0]|NULL|Erro|Não é uma matriz.|  
|$.info.none|NULL|Erro|A propriedade não existe.|  

### <a name="using-jsonquery-with-for-json"></a>Usando JSON_QUERY com FOR JSON

**JSON_QUERY** retorna um fragmento JSON válido. Como resultado, **FOR JSON** não usa escape para caracteres especiais no valor retornado de **JSON_QUERY**.

Se você estiver retornando resultados com FOR JSON e estiver incluindo dados que já estejam no formato JSON (em uma coluna ou como resultado de uma expressão), encapsule os dados JSON com **JSON_QUERY** sem o parâmetro *path*.

## <a name="examples"></a>Exemplos  
  
### <a name="example-1"></a>Exemplo 1  
 O exemplo a seguir mostra como retornar um fragmento JSON de uma coluna `CustomFields` nos resultados da consulta.  
  
```sql  
SELECT PersonID,FullName,
 JSON_QUERY(CustomFields,'$.OtherLanguages') AS Languages
FROM Application.People
```  
  
### <a name="example-2"></a>Exemplo 2  
O exemplo a seguir mostra como incluir fragmentos JSON na saída da cláusula FOR JSON.  
  
```sql  
SELECT StockItemID, StockItemName,
         JSON_QUERY(Tags) as Tags,
         JSON_QUERY(CONCAT('["',ValidFrom,'","',ValidTo,'"]')) ValidityPeriod
FROM Warehouse.StockItems
FOR JSON PATH
```  
  
## <a name="see-also"></a>Consulte Também  
 [Expressões de demarcador JSON &#40;SQL Server&#41;](../../relational-databases/json/json-path-expressions-sql-server.md)   
 [Dados JSON &#40;SQL Server&#41;](../../relational-databases/json/json-data-sql-server.md)  
