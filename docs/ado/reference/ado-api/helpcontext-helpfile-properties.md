---
title: HelpContext, HelpFile propriedades | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Error::GetHelpContext
- Error::GetHelpFile
- Error::get_HelpFile
- Error::get_HelpContext
- Error::HelpContext
- Error::HelpFile
helpviewer_keywords:
- HelpContext property [ADO]
- HelpFile property [ADO]
ms.assetid: 2b9ef441-993c-44d4-8f87-fac0979dac1d
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 708ce57e129ed84dcbafa837916c299a76739e0d
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35278905"
---
# <a name="helpcontext-helpfile-properties"></a>Propriedades HelpContext e HelpFile
Indica o arquivo de Ajuda e o tópico associado a um [erro](../../../ado/reference/ado-api/error-object.md) objeto.  
  
## <a name="return-values"></a>Valores de retorno  
  
-   **IdentificaçãoDoContextoDaAjuda** retorna uma ID de contexto, como um **longo** valor para um tópico em um arquivo de Ajuda.  
  
-   **Arquivo de Ajuda** retorna um **cadeia de caracteres** valor que é avaliada como um caminho totalmente resolvido para um arquivo de Ajuda.  
  
## <a name="remarks"></a>Remarks  
 Se um arquivo de Ajuda é especificado no **HelpFile** propriedade, o **HelpContext** propriedade é usada para exibir o tópico da Ajuda, ele identifica automaticamente. Se não houver nenhum tópico da Ajuda relevante disponíveis, o **HelpContext** propriedade retorna zero e o **HelpFile** propriedade retorna uma cadeia de caracteres de comprimento zero ("").  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Error](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>Consulte também  
 [Descrição, HelpContext, HelpFile, NativeError, número, fonte e exemplo de propriedades de SQLState (VB)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Descrição, HelpContext, HelpFile, NativeError, número, fonte e exemplo de propriedades de SQLState (VC + +)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
 [Propriedade Description](../../../ado/reference/ado-api/description-property.md)   
 [Propriedade de número (ADO)](../../../ado/reference/ado-api/number-property-ado.md)   
 [Propriedade Source (Erro ADO)](../../../ado/reference/ado-api/source-property-ado-error.md)
