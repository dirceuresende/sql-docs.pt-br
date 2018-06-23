---
title: Constantes grandes são digitadas como tipos de valor grande nos modos de compatibilidade 90 ou posterior | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binary constants
- CHARINDEX function
- constants
- character string constants
- PATINDEX function
ms.assetid: 6e309fa0-5fb9-45a1-9739-f13fae525bfe
caps.latest.revision: 17
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d40faa01af8e275e7d085a06475322e093786150
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36005827"
---
# <a name="large-constants-are-typed-as-large-value-types-in-90-or-later-compatibility-modes"></a>Constantes grandes são digitadas como tipos de valor grande no modo de compatibilidade 90 ou posterior
  O Supervisor de Atualização detectou a presença de constantes grandes. Constantes de cadeias de caracteres e constantes binárias maiores que 8.000 bytes são tratadas como tipos de dados de objeto grande no [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]. No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou em versões posteriores, caracteres grandes, Unicode e constantes binárias são digitadas como tipos do valor grande.  
  
## <a name="component"></a>Componente  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>Description  
 Quando funções de cadeia de caracteres, como CHARINDEX e PATINDEX, são usadas com constantes de cadeia de caracteres ou constantes binárias que excedem 8.000 bytes, o [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] retorna o erro 8116, e o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou versões posteriores retorna o erro 8152.  
  
 No [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], as funções de cadeia de caracteres retornam o erro 8116 quando são usadas com tipos de dados `text`, `ntext` e `image`.  
  
 No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou em versões posteriores, as constantes grandes são tratadas como tipos de dados `varchar(max)`, `nvarchar(max)` e `varbinary(max)`, respectivamente. Esses tipos de dados são compatíveis com funções de cadeia de caracteres.  
  
 No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou em versões posteriores, funções de cadeia de caracteres, como CHARINDEX e PATINDEX, assumem a cadeia de caracteres que tem a sequência de caracteres com menos de 8.000 bytes. É pos isso que o erro 8152 é exibido para CHARINDEX e PATINDEX.  
  
## <a name="see-also"></a>Consulte também  
 [Problemas de atualização de mecanismo de banco de dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [Supervisor de atualização do SQL Server 2014 &#91;novo&#93;](/sql/2014/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  