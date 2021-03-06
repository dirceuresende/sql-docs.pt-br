---
title: O elemento &lt;xsd:redefine&gt; | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
caps.latest.revision: 13
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 21f11e1d27ce94c62e2d3115134bf714c918a5d1
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37175158"
---
# <a name="the-ltxsdredefinegt-element"></a>O elemento &lt;xsd:redefine&gt;
  O elemento **redefine** do W3C XSD fornece suporte para redefinição de componentes de esquema. Entretanto, há suporte para essa diretiva é potencialmente cara para o desempenho e também requer que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalide todas as instâncias da `xml` tipo de dados associado ao esquema redefinido. Portanto o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não oferece suporte a esse elemento. Esquemas XML que incluem o elemento **\<xsd:redefine>** são rejeitados pelo servidor.  
  
 Para atualizar um esquema ou seus componentes, é possível fazer o seguinte:  
  
1.  Crie uma nova coleção de esquema XML com os componentes do esquema modificado.  
  
2.  Redefina o tipo de todos os tipos de dados `xml` (XML DT) que usam a coleção de esquema XML a serem redefinidos para usarem a nova coleção de esquema XML. Para isso, use a opção ALTER COLUMN do comando ALTER TABLE para redefinir o tipo das colunas ou altere as restrições da coleção de esquema XML sobre variáveis ou parâmetros.  
  
3.  Descarte a versão antiga da coleção de esquema XML.  
  
## <a name="see-also"></a>Consulte também  
 [Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
