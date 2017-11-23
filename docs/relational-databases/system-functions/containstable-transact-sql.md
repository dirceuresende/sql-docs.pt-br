---
title: CONTAINSTABLE (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2015
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: system-functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CONTAINSTABLE
- CONTAINSTABLE_TSQL
dev_langs: TSQL
helpviewer_keywords:
- precise or fuzzy (less precise) matches [full-text search]
- fuzzy (less precise) word or phrase search [full-text search]
- word searches [full-text search]
- weighted values [full-text search]
- values [SQL Server], ranked
- LANGUAGE option
- NEAR option [full-text search]
- RANK column
- phrase searches [full-text search]
- conditions [SQL Server], CONTAINSTABLE
- relevance ranking values [full-text search]
- proximity searches [full-text search]
- CONTAINSTABLE function (Transact-SQL)
- ranked results [full-text search]
- rankings [full-text search]
- less precise (fuzzy) searches [full-text search]
ms.assetid: e580c210-cf57-419d-9544-7f650f2ab814
caps.latest.revision: "69"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 5efcf8fb5b5169bbf03390b02ddc068bf6a30d25
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="containstable-transact-sql"></a>CONTAINSTABLE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna uma tabela de zero, uma ou mais linhas para as colunas que contêm um correspondências precisas ou difusas (menos preciso) para palavras e frases únicas, a proximidade de palavras em uma certa distância entre si ou correspondências ponderadas. CONTAINSTABLE é usado no [cláusula FROM](../../t-sql/queries/from-transact-sql.md) de um [!INCLUDE[tsql](../../includes/tsql-md.md)] instrução SELECT e referenciado como se fosse um nome de tabela normal. Ele executa uma pesquisa de texto completo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em colunas indexadas de texto completo que contêm tipos de dados baseados em caracteres.  
  
 CONTAINSTABLE é útil para os mesmos tipos de correspondências como o [predicado CONTAINS](../../t-sql/queries/contains-transact-sql.md) e usa as mesmas condições de pesquisa que contém.  
  
 Diferentemente de CONTAINS, as consultas que usam CONTAINSTABLE retornam um valor de classificação de relevância (RANK) e uma chave de texto completo (KEY) para cada linha.  Para obter informações sobre os formulários de pesquisas de texto completo que são suportados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [consulta com pesquisa de texto completo](../../relational-databases/search/query-with-full-text-search.md).  
  
||  
|-|  
|**Aplica-se a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] por meio de [versão atual](http://go.microsoft.com/fwlink/p/?LinkId=299658)), [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([visualização em algumas regiões](http://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).|  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
CONTAINSTABLE   
( table , { column_name | ( column_list ) | * } , ' <contains_search_condition> '   
     [ , LANGUAGE language_term]   
  [ , top_n_by_rank ]   
)   
  
<contains_search_condition> ::=   
    { <simple_term>   
    | <prefix_term>   
    | <generation_term>   
    | <generic_proximity_term>   
    | <custom_proximity_term>   
    |  <weighted_term>   
    }   
    | { ( <contains_search_condition> )   
    { { AND | & } | { AND NOT | &! } | { OR | | } }   
     <contains_search_condition> [ ...n ]   
    }  
  
<simple_term> ::=   
     { word | "phrase" }  
<prefix term> ::=   
     { "word*" | "phrase*" }   
<generation_term> ::=   
     FORMSOF ( { INFLECTIONAL | THESAURUS } , <simple_term> [ ,...n ] )   
  
<generic_proximity_term> ::=   
     { <simple_term> | <prefix_term> } { { { NEAR | ~ }   
     { <simple_term> | <prefix_term> } } [ ...n ] }  
  
<custom_proximity_term> ::=   
  NEAR (   
     {  
        { <simple_term> | <prefix_term> } [ ,…n ]  
     |  
        ( { <simple_term> | <prefix_term> } [ ,…n ] )   
      [, <maximum_distance> [, <match_order> ] ]  
     }  
       )   
  
      <maximum_distance> ::= { integer | MAX }  
      <match_order> ::= { TRUE | FALSE }   
  
<weighted_term> ::=   
     ISABOUT  
    ( { {   
  <simple_term>   
  | <prefix_term>   
  | <generation_term>   
  | <proximity_term>   
  }   
   [ WEIGHT ( weight_value ) ]   
   } [ ,...n ]   
    )  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *table*  
 É o nome de uma tabela que foi indexada com texto completo. *tabela* pode ser um uma, duas, três ou nome de objeto de quatro partes do banco de dados. Durante a consulta a uma exibição, apenas uma tabela base indexada por texto completo pode ser envolvida.  
  
 *tabela* não é possível especificar um nome de servidor e não pode ser usado em consultas em servidores vinculados.  
  
 *nome da coluna*  
 É o nome de uma ou mais colunas indexadas para pesquisa de texto completo. As colunas podem ser do tipo **char**, **varchar**, **nchar**, **nvarchar**, **texto**, **ntext**, **imagem**, **xml**, **varbinary**, ou **varbinary (max)**.  
  
 *column_list*  
 Indica que várias colunas, separadas por uma vírgula, podem ser especificadas. *column_list* devem ser colocados entre parênteses. A menos que *language_term* for especificado, o idioma de todas as colunas de *column_list* devem ser iguais.  
  
 \*  
 Especifica que todos os completo colunas indexadas de texto em *tabela* deve ser usado para procurar o critério de pesquisa especificado. A menos que *language_term* for especificado, o idioma de todas as colunas da tabela deve ser o mesmo.  
  
 IDIOMA *language_term*  
 É o idioma cujos recursos serão usados para separação de palavras, lematização e dicionário de sinônimos e palavras de ruído (ou [palavra irrelevante](../../relational-databases/search/configure-and-manage-stopwords-and-stoplists-for-full-text-search.md)) remoção como parte da consulta. Esse parâmetro é opcional e pode ser especificado como uma cadeia de caracteres, um inteiro ou um valor hexadecimal que corresponda ao LCID (identificador de localidade) de um idioma. Se *language_term* for especificado, o idioma que ele representa será aplicado a todos os elementos da condição de pesquisa. Se nenhum valor for especificado, o idioma de texto completo da coluna será usado.  
  
 Se documentos de idiomas diferentes forem armazenados em conjunto como BLOBs (objetos binários grandes) em uma única coluna, o LCID de um determinado documento determinará qual idioma será usado para indexar seu conteúdo. Ao consultar uma coluna desse tipo, especificando *idioma**language_term* pode aumentar a probabilidade de uma boa correspondência.  
  
 Quando especificado como uma cadeia de caracteres, *language_term* corresponde do **alias** valor de coluna no [sys. syslanguages](../../relational-databases/system-compatibility-views/sys-syslanguages-transact-sql.md) exibição de compatibilidade.  A cadeia de caracteres deve ser colocada entre aspas, como em '*language_term*'. Quando especificado como um inteiro, *language_term* é o LCID real que identifica o idioma. Quando especificado como um valor hexadecimal, *language_term* é 0x seguido pelo valor hexadecimal do LCID. O valor hexadecimal não deve exceder oito dígitos, inclusive zeros à esquerda.  
  
 Se o valor está no formato DBCS (conjunto) de caracteres de byte duplo, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] converterá em Unicode.  
  
 Se o idioma especificado não for válido ou se não houver nenhum recurso instalado que corresponda ao idioma, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retornará um erro. Para usar os recursos de idioma neutro, especifique 0x0 como *language_term*.  
  
 *top_n_by_rank*  
 Especifica que somente o  *n*  correspondências mais bem classificadas, em ordem decrescente, são retornadas. Se aplica somente quando um valor inteiro,  *n* , é especificado. Se *top_n_by_rank* for combinado com outros parâmetros, a consulta retornará menos linhas do que o número de linhas que corresponde de fato a todos os predicados. *top_n_by_rank* permite aumentar o desempenho da consulta chamando novamente apenas as ocorrências mais relevantes.  
  
 <contains_search_condition>  
 Especifica o texto a ser pesquisado em *column_name* e as condições para uma correspondência. Para obter informações sobre critérios de pesquisa, consulte [CONTAINS &#40; Transact-SQL &#41; ](../../t-sql/queries/contains-transact-sql.md).  
  
## <a name="remarks"></a>Comentários  
 As funções e os predicados de texto completo trabalham em uma única tabela, que está implícita no predicado FROM. Para pesquisar em várias tabelas, use uma tabela unida na cláusula FROM para pesquisar em um conjunto de resultados que é o produto de duas ou mais tabelas.  
  
 A tabela retornada tem uma coluna denominada **chave** que contém valores de chave de texto completo. Cada tabela indexada de texto completo tem uma coluna cujos valores têm garantia de exclusividade e os valores retornados no **chave** coluna são os valores de chave de texto completo das linhas que correspondem aos critérios de seleção especificados de pesquisa contains condição. O **TableFulltextKeyColumn** propriedade, obtida da função OBJECTPROPERTYEX, fornece a identidade dessa coluna de chave exclusiva. Para obter a ID da coluna associada à chave de texto completo do índice de texto completo, use **fulltext_indexes**. Para obter mais informações, consulte [fulltext_indexes &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql.md).  
  
 Para obter as linhas desejadas da tabela original, especifique uma junção com as linhas CONTAINSTABLE. O formulário típico da cláusula FROM de uma instrução SELECT que usa CONTAINSTABLE é:  
  
```  
SELECT select_list  
FROM table AS FT_TBL INNER JOIN  
   CONTAINSTABLE(table, column, contains_search_condition) AS KEY_TBL  
   ON FT_TBL.unique_key_column = KEY_TBL.[KEY];  
```  
  
 A tabela produzida por CONTAINSTABLE contém uma coluna chamada **classificação**. O **classificação** coluna é um valor (de 0 a 1000) para cada linha que indica como uma linha de correspondência com os critérios de seleção. Geralmente, esse valor de classificação é usado de uma destas maneiras na instrução SELECT:  
  
-   Na cláusula ORDER BY para retornar as linhas com classificação mais alta como as primeiras linhas da tabela.  
  
-   Na lista de seleção para ver o valor de classificação atribuído à cada linha.  
  
## <a name="permissions"></a>Permissões  
 As permissões de execução estão disponíveis somente para usuários com os privilégios SELECT adequados na tabela ou nas colunas da tabela referenciada.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-simple-example"></a>A. Exemplo simples  
 O exemplo a seguir cria e preenche uma tabela simples de duas colunas, listando as 3 regiões e as cores em seus sinalizadores. O TI cria e preenche um catálogo de texto completo e o índice na tabela. Em seguida, o **CONTAINSTABLE** sintaxe é demonstrada. Este exemplo demonstra como o valor de classificação aumenta superior quando o valor de pesquisa é atendido várias vezes. A última consulta, Tanzânia que contém verde e preto tem uma classificação mais alta que Itália que contêm apenas uma das cores consultadas.  
  
```  
CREATE TABLE Flags (Country nvarchar(30) NOT NULL, FlagColors varchar(200));  
CREATE UNIQUE CLUSTERED INDEX FlagKey ON Flags(Country);  
INSERT Flags VALUES ('France', 'Blue and White and Red');  
INSERT Flags VALUES ('Italy', 'Green and White and Red');  
INSERT Flags VALUES ('Tanzania', 'Green and Yellow and Black and Yellow and Blue');  
SELECT * FROM Flags;  
GO  
  
CREATE FULLTEXT CATALOG TestFTCat;  
CREATE FULLTEXT INDEX ON Flags(FlagColors) KEY INDEX FlagKey ON TestFTCat;  
GO   
  
SELECT * FROM Flags;  
SELECT * FROM CONTAINSTABLE (Flags, FlagColors, 'Green') ORDER BY RANK DESC;  
SELECT * FROM CONTAINSTABLE (Flags, FlagColors, 'Green or Black') ORDER BY RANK DESC;  
```  
  
### <a name="b-returning-rank-values"></a>B. Retornando valores de classificação  
 O exemplo a seguir pesquisa todos os nomes de produtos que contêm as palavras "frame," "wheel" ou "tire", e diferentes pesos são dados a cada uma. Para cada linha retornada que corresponda a esses critérios de pesquisa, a proximidade relativa (valor de classificação) da correspondência é mostrada. Além disso, as linhas com classificação mais alta serão retornadas primeiro.  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT FT_TBL.Name, KEY_TBL.RANK  
    FROM Production.Product AS FT_TBL   
        INNER JOIN CONTAINSTABLE(Production.Product, Name,   
        'ISABOUT (frame WEIGHT (.8),   
        wheel WEIGHT (.4), tire WEIGHT (.2) )' ) AS KEY_TBL  
            ON FT_TBL.ProductID = KEY_TBL.[KEY]  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  
### <a name="c-returning-rank-values-greater-than-a-specified-value"></a>C. Retornando valores de classificação maiores que um valor especificado  
  
||  
|-|  
|**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].|  
  
 O exemplo a seguir usa NEAR para procurar "`bracket`" e "`reflector`" perto um do outro na tabela `Production.Document`. Somente linhas com um valor de classificação de 50 ou superior são retornadas.  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable   
INNER JOIN CONTAINSTABLE(Production.Document, Document,  
  'NEAR(bracket, reflector)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
WHERE KEY_TBL.RANK > 50  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  
> [!NOTE]  
>  Se uma consulta de texto completo não especificar um valor inteiro como a distância máxima, um documento que contenha apenas ocorrências cujos intervalos sejam maiores que 100 termos lógicos não atenderá aos requisitos de NEAR e terá uma classificação de 0.  
  
### <a name="d-returning-top-5-ranked-results-using-topnbyrank"></a>D. Retornando os 5 maiores resultados da classificação por meio de top_n_by_rank  
 O exemplo a seguir retorna a descrição dos cinco produtos cuja coluna `Description` contém a palavra "aluminum" próxima às palavras "light" ou "lightweight".  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT FT_TBL.ProductDescriptionID,  
   FT_TBL.Description,   
   KEY_TBL.RANK  
FROM Production.ProductDescription AS FT_TBL INNER JOIN  
   CONTAINSTABLE (Production.ProductDescription,  
      Description,   
      '(light NEAR aluminum) OR  
      (lightweight NEAR aluminum)',  
      5  
   ) AS KEY_TBL  
   ON FT_TBL.ProductDescriptionID = KEY_TBL.[KEY];  
GO  
```  
  
 `GO`  
  
### <a name="e-specifying-the-language-argument"></a>E. Especificando o argumento LANGUAGE  
 O exemplo a seguir mostra o uso do argumento `LANGUAGE`.  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT FT_TBL.ProductDescriptionID,  
   FT_TBL.Description,   
   KEY_TBL.RANK  
FROM Production.ProductDescription AS FT_TBL INNER JOIN  
   CONTAINSTABLE (Production.ProductDescription,  
      Description,   
      '(light NEAR aluminum) OR  
      (lightweight NEAR aluminum)',  
      LANGUAGE N'English',  
      5  
   ) AS KEY_TBL  
   ON FT_TBL.ProductDescriptionID = KEY_TBL.[KEY];  
GO  
```  
  
> [!NOTE]  
>  O idioma *language_term* argumentis não é necessário para usar *top_n_by_rank.*  
  
## <a name="see-also"></a>Consulte também  
 [Limite resultados de pesquisa com RANK](../../relational-databases/search/limit-search-results-with-rank.md)   
 [Consulta com pesquisa de texto completo](../../relational-databases/search/query-with-full-text-search.md)   
 [Criar consultas de pesquisa de texto completo &#40;Visual Database Tools&#41;](http://msdn.microsoft.com/library/537fa556-390e-4c88-9b8e-679848d94abc)   
 [CONTAINS &#40;Transact-SQL&#41;](../../t-sql/queries/contains-transact-sql.md)   
 [Consulta com pesquisa de texto completo](../../relational-databases/search/query-with-full-text-search.md)   
 [SELECT &#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [FROM &#40;Transact-SQL&#41;](../../t-sql/queries/from-transact-sql.md)  
  
  