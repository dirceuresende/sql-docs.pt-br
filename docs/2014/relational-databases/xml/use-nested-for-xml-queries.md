---
title: Usar consultas FOR XML aninhadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], nested FOR XML
- nested FOR XML queries
ms.assetid: 7604161a-a958-446d-b102-7dee432979d0
caps.latest.revision: 41
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: e8ce91a3ee069562a6a4d3f9d6aa3c02999e4dff
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36010158"
---
# <a name="use-nested-for-xml-queries"></a>Usar consultas FOR XML aninhadas
  O `xml` tipo de dados e o [diretiva TYPE em consultas FOR XML](type-directive-in-for-xml-queries.md) habilitam o XML retornado por consultas FOR XML seja processado no servidor e no cliente.  
  
## <a name="processing-with-xml-type-variables"></a>Processando com variáveis de tipo xml  
 É possível atribuir o resultado da consulta FOR XML a uma variável de tipo `xml`, ou usar a XQuery para consultar o resultado e atribuir esse resultado a uma variável de tipo `xml` para processamento adicional.  
  
```  
DECLARE @x xml  
SET @x=(SELECT ProductModelID, Name  
        FROM Production.ProductModel  
        WHERE ProductModelID=122 or ProductModelID=119  
        FOR XML RAW, TYPE)  
SELECT @x  
-- Result  
--<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
--<row ProductModelID="119" Name="Bike Wash" />  
```  
  
 Além disso, você pode processar o XML retornado na variável, `@x`, usando um do `xml` métodos de tipo de dados. Por exemplo, é possível recuperar o valor do atributo `ProductModelID` usando o [método value()](/sql/t-sql/xml/value-method-xml-data-type).  
  
```  
DECLARE @i int;  
SET @i = (SELECT @x.value('/row[1]/@ProductModelID[1]', 'int'));  
SELECT @i;  
```  
  
 No exemplo a seguir, o resultado da consulta `FOR XML` é retornado como um tipo `xml`, porque a diretiva `TYPE` é especificada na cláusula `FOR XML`.  
  
```  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=119 or ProductModelID=122  
FOR XML RAW, TYPE,ROOT('myRoot');  
  
```  
  
 Este é o resultado:  
  
```  
<myRoot>  
  <row ProductModelID="122" Name="All-Purpose Bike Stand" />  
  <row ProductModelID="119" Name="Bike Wash" />  
</myRoot>  
```  
  
 Como o resultado é de `xml` tipo, você pode especificar um o `xml` métodos diretamente em relação a esse XML de tipo de dados conforme mostrado na consulta a seguir. Na consulta, o [método query() (tipo de dados xml)](/sql/t-sql/xml/query-method-xml-data-type) é usado para recuperar o primeiro elemento filho <`row`> do elemento <`myRoot`>.  
  
```  
SELECT  (SELECT ProductModelID, Name  
         FROM Production.ProductModel  
         WHERE ProductModelID=119 or ProductModelID=122  
         FOR XML RAW, TYPE,ROOT('myRoot')).query('/myRoot[1]/row[1]');  
  
```  
  
 Este é o resultado:  
  
```  
<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
```  
  
## <a name="returning-inner-for-xml-query-results-to-outer-queries-as-xml-type-instances"></a>Retornando resultados de consulta FOR XML interna para consultas externas como instâncias de tipo xml  
 Você pode escrever aninhada `FOR XML` consultas onde o resultado da consulta interna é retornado como um `xml` tipo para a consulta externa. Por exemplo:  
  
```  
SELECT Col1,   
       Col2,   
       ( SELECT Col3, Col4   
        FROM  T2  
        WHERE T2.Col = T1.Col  
        ...  
        FOR XML AUTO, TYPE )  
FROM T1  
WHERE ...  
FOR XML AUTO, TYPE;  
```  
  
 Observe o seguinte na consulta anterior:  
  
-   O XML gerado pela consulta `FOR XML` interna é adicionado ao XML gerado pela `FOR XML`externa.  
  
-   A consulta interna especifica a diretiva `TYPE` . Portanto, os dados XML retornados pela consulta interna são de tipo `xml`. Se a diretiva TYPE não for especificada, o resultado da consulta `FOR XML` interna será retornado como `nvarchar(max)` e os dados XML terão a entidade definida.  
  
## <a name="controlling-the-shape-of-resulting-xml-data"></a>Controlando a forma dos dados XML resultantes  
 Consultas FOR XML aninhadas fornecem mais controle para definir a forma dos dados XML resultantes. É possível usar consultas aninhadas FOR XML para construir XML parcialmente centrado em atributo e parcialmente centrado em elemento.  
  
 Para obter mais informações sobre como especificar um XML centrado em atributo e em elemento com consultas FOR XML aninhadas, veja [Consulta FOR XML comparada com consulta FOR XML aninhada](../xml/for-xml-query-compared-to-nested-for-xml-query.md) e [Formar XML com consultas FOR XML aninhadas](../xml/shape-xml-with-nested-for-xml-queries.md).  
  
 É possível gerar hierarquias XML que incluem irmãos especificando consultas aninhadas FOR XML em modo AUTO. Para obter mais informações, veja [Gerar irmãos com uma consulta aninhada em modo AUTO](../xml/generate-siblings-with-a-nested-auto-mode-query.md).  
  
 Independentemente do modo usado, consultas FOR XML aninhadas fornecem mais controle para descrever a forma do XML resultante. Elas podem ser usadas no lugar de consultas em modo EXPLICIT.  
  
## <a name="examples"></a>Exemplos  
 Os tópicos a seguir fornecem exemplos de consultas FOR XML aninhadas.  
  
 [Consulta FOR XML comparada com consulta FOR XML aninhada](../xml/for-xml-query-compared-to-nested-for-xml-query.md)  
 Compara uma consulta FOR XML de nível único com uma consulta FOR XML aninhada. Este exemplo inclui uma demonstração de como especificar XML centrado em atributo e centrado em elemento como o resultado da consulta.  
  
 [Gerar irmãos com uma consulta aninhada em modo AUTO](../xml/generate-siblings-with-a-nested-auto-mode-query.md)  
 Mostra como gerar irmãos usando uma consulta aninhada em modo AUTO  
  
 [Usar consultas FOR XML aninhadas no ASP.NET](use-nested-for-xml-queries-in-asp-net.md)  
 Demonstra como um aplicativo ASPX pode usar FOR XML para retornar XML do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 [Formar XML com consultas FOR XML aninhadas](../xml/shape-xml-with-nested-for-xml-queries.md)  
 Mostra como usar consultas FOR XML aninhadas para controlar a estrutura de um documento XML criado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
  