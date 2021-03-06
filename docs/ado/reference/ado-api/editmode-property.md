---
title: Propriedade EditMode | Microsoft Docs
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
- Recordset15::EditMode
helpviewer_keywords:
- EditMode property
ms.assetid: a1b04bb2-8c8b-47f9-8477-bfd0368b6f68
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1fd943679fc15cde9a3349b455decc778889b0c6
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35277925"
---
# <a name="editmode-property"></a>Propriedade EditMode
Indica o status de edição do registro atual.  
  
## <a name="return-value"></a>Valor retornado  
 Retorna um [EditModeEnum](../../../ado/reference/ado-api/editmodeenum.md) valor.  
  
## <a name="remarks"></a>Remarks  
 ADO mantém um buffer de edição associado ao registro atual. Essa propriedade indica se foram feitas alterações a esse buffer, ou se um novo registro foi criado. Use o **EditMode** propriedade para determinar o status de edição do registro atual. Você pode testar alterações pendentes se um processo de edição foi interrompido e determinar se é necessário usar o [atualização](../../../ado/reference/ado-api/update-method.md) ou [CancelUpdate](../../../ado/reference/ado-api/cancelupdate-method-ado.md) método.  
  
 Em *modo de atualização imediata* o **EditMode** propriedade é redefinida para **adEditNone** após uma chamada bem-sucedida para o **atualizar** é chamado de método . Quando uma chamada para [excluir](../../../ado/reference/ado-api/delete-method-ado-recordset.md) com êxito exclui o registro ou os registros na fonte de dados (por exemplo, devido a violações de integridade referencial), o [registros](../../../ado/reference/ado-api/recordset-object-ado.md) permanece no modo de edição (**EditMode** = **adEditInProgress**). Portanto, **CancelUpdate** deve ser chamado antes de mover fora do registro atual (por exemplo, com [mover](../../../ado/reference/ado-api/move-method-ado.md), [NextRecordset](../../../ado/reference/ado-api/nextrecordset-method-ado.md), ou [fechar](../../../ado/reference/ado-api/close-method-ado.md) ).  
  
 Em *o modo de atualização em lotes* (no qual o provedor armazena em cache várias alterações e grava a fonte de dados somente quando você chamar o [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md) método), o valor da **EditMode**  propriedade é alterada quando a primeira operação é executada e ele não é redefinido por uma chamada para o **atualização** método. As operações subsequentes não alteram o valor de **EditMode** propriedade, mesmo se forem executadas operações diferentes. Por exemplo, se a primeira operação é para adicionar um novo registro, e o segundo faz alterações a um existente registro, a propriedade de **EditMode** ainda será **adEditAdd**. O **EditMode** propriedade não é redefinida para **adEditNone** até após a chamada a **UpdateBatch**. Para determinar quais operações foram executadas, defina o [filtro](../../../ado/reference/ado-api/filter-property.md) propriedade [adFilterPending](../../../ado/reference/ado-api/filtergroupenum.md) para que somente os registros com alterações pendentes serão visíveis e examine o [Status](../../../ado/reference/ado-api/status-property-ado-recordset.md) propriedade de cada registro para determinar quais alterações foram feitas nos dados.  
  
> [!NOTE]
>  **EditMode** pode retornar um valor válido somente se houver um registro atual. **EditMode** retornará um erro se [BOF ou EOF](../../../ado/reference/ado-api/bof-eof-properties-ado.md) for true, ou se o registro atual foi excluído.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de propriedades EditMode (VB), CursorType e LockType](../../../ado/reference/ado-api/cursortype-locktype-and-editmode-properties-example-vb.md)   
 [Exemplo de propriedades EditMode (VC + +), CursorType e LockType](../../../ado/reference/ado-api/cursortype-locktype-and-editmode-properties-example-vc.md)   
 [Método AddNew (ADO)](../../../ado/reference/ado-api/addnew-method-ado.md)   
 [Excluir método (conjunto de registros ADO)](../../../ado/reference/ado-api/delete-method-ado-recordset.md)   
 [Método CancelUpdate (ADO)](../../../ado/reference/ado-api/cancelupdate-method-ado.md)   
 [Método Update](../../../ado/reference/ado-api/update-method.md)
