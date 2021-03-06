---
title: MultiLineString | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-spatial
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiLineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 95deeefe-d6c5-4a11-b347-379e4486e7b7
caps.latest.revision: 19
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: c340afc52dbd60f4accb1da7d3883e62d36974f6
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37288522"
---
# <a name="multilinestring"></a>MultiLineString
  Um `MultiLineString` é uma coleção de zero ou mais `geometry` ou **geographyLineString** instâncias.  
  
## <a name="multilinestring-instances"></a>Instâncias MultiLineString  
 A ilustração a seguir mostra exemplos de `MultiLineString` instâncias.  
  
 ![Exemplos de instâncias geométricas MultiLineString](../../database-engine/media/multilinestring.gif "Exemplos de instâncias geométricas MultiLineString")  
  
 Conforme mostrado na ilustração:  
  
-   Figura 1 é um simples `MultiLineString` instância cujo limite são os quatro pontos de extremidade de seus dois `LineString` elementos.  
  
-   A Figura 2 é uma instância `MultiLineString` simples porque apenas os pontos de extremidade da interseção de elementos `LineString` se cruzam. O limite são os dois pontos de extremidade que não se sobrepõem.  
  
-   A Figura 3 é uma instância `MultiLineString` não simples porque apenas o interior de um de seus elementos `LineString` se cruzam. O limite dessa `MultiLineString` instância é de quatro pontos de extremidade.  
  
-   Figura 4 é um não simples, não fechada `MultiLineString` instância.  
  
-   A Figura 5 é uma instância `MultiLineString` simples, não fechada. Não é fechada porque seus `LineStrings` elementos não estão fechados. É simple porque nenhum dos interiores de qualquer um do `LineStrings` instâncias se cruzam.  
  
-   Figura 6 é uma simples e fechada `MultiLineString` instância. Ela é fechada porque todos os seus elementos não estão fechados. Ela é simples porque nenhum de seus elementos se cruzam nos interiores.  
  
### <a name="accepted-instances"></a>Instâncias aceitas  
 Para um `MultiLineString` instância para ser aceita, ela precisa estar vazia ou conter apenas `LineString` instâncias que são aceitos. Para obter mais informações sobre aceitas `LineString` instâncias, consulte [LineString](../spatial/linestring.md). Veja a seguir exemplos de instâncias `MultiLineString` aceitas.  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
```  
  
 O exemplo a seguir gera uma `System.FormatException` porque o segundo `LineString` instância não é válida.  
  
```  
DECLARE @g geometry = 'MULTILINESTRING((1 1, 3 5),(-5 3))';  
```  
  
### <a name="valid-instances"></a>Instâncias válidas  
 Para um `MultiLineString` instância seja válida, ela deve atender aos seguintes critérios:  
  
1.  Todas as instâncias contendo a instância `MultiLineString` devem ser instâncias `LineString` válidas.  
  
2.  Duas instâncias `LineString` contendo a instância `MultiLineString` não podem se sobrepor em um intervalo. Apenas em um número finito de pontos, é possível encontrar as instâncias `LineString` se cruzando ou se tocando umas com as outras, ou com outras instâncias `LineString`.  
  
 O exemplo a seguir mostra três instâncias `MultiLineString` válidas e uma instância `MultiLineString` que não é válida.  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 `@g4` não é válido porque a segunda `LineString` instância sobrepõe a primeira `LineString` instância em um intervalo. Elas se tocam em um número infinito de pontos.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria uma instância simples do `geometry``MultiLineString` , que contém dois elementos de `LineString` com o SRID 0.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
```  
  
 Para instanciar essa instância com um SRID diferente, use `STGeomFromText()` ou `STMLineStringFromText()`. Também é possível usar `Parse()` e, em seguida, modificar o SRID, conforme mostrado no exemplo a seguir.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
SET @g.STSrid = 13;  
```  
  
## <a name="see-also"></a>Consulte também  
 [STLength &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)   
 [STIsClosed &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)   
 [LineString](../spatial/linestring.md)   
 [Dados espaciais &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)  
  
  
