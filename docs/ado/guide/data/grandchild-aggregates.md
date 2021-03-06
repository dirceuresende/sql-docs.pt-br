---
title: Agregações neto | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- grandchild aggregates [ADO]
- data shaping [ADO], grandchild aggregates
ms.assetid: 4162d35f-2ce1-4218-80a5-b6933348837e
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 05fc1ed0279157f581e5d5fd7bdad3eac555f34b
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35270205"
---
# <a name="grandchild-aggregates"></a>Agregações neto
A coluna de capítulo criada em uma cláusula de um comando de forma pode ser dado um *nome do alias do capítulo* (normalmente com a palavra-chave). Você pode identificar qualquer coluna em qualquer capítulo a forma **registros** com um nome totalmente qualificado que identifica o filho que contém a coluna. Por exemplo, se o capítulo pai, Cap1, contém um capítulo filho, chap2, que tem uma coluna de quantidade amt, e o nome qualificado seria chap1.chap2.amt. O nome qualificado, em seguida, pode ser usado como um argumento para uma das funções de agregação (SUM, AVG, MAX, MIN, COUNT, STDEV ou qualquer).  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de data shaping](../../../ado/guide/data/data-shaping-example.md)
