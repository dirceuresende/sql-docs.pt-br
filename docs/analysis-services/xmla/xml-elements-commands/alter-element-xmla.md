---
title: Elemento ALTER (XMLA) | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 5ff62bcde0aa40e9bb052691d4d3dee1317c1217
ms.sourcegitcommit: 808d23a654ef03ea16db1aa23edab496b73e5072
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34574598"
---
# <a name="alter-element-xmla"></a>Elemento Alter (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Contém elementos do Analysis Services Scripting Language (ASSL) usados pelo [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) método para alterar objetos em uma instância do Analysis Services.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Command>  
   <Alter Scope="enum" AllowCreate="boolean" ObjectExpansion="enum">  
      <Object>...</Object>  
      <ObjectDefinition>...</ObjectDefinition>  
   </Alter>  
</Command>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-n: Elemento opcional que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Comando](../../../analysis-services/xmla/xml-elements-properties/command-element-xmla.md)|  
|Elementos filho|[Objeto](../../../analysis-services/xmla/xml-elements-properties/object-element-xmla.md), [ObjectDefinition](../../../analysis-services/xmla/xml-elements-properties/objectdefinition-element-xmla.md)|  
  
## <a name="attributes"></a>Atributos  
  
|attribute|Description|  
|---------------|-----------------|  
|AllowCreate|(Atributo **Boolean** opcional) Indica se os objetos definidos no comando **Alter** devem ser criados se ainda não existirem.<br /><br /> Se definido como true, os objetos definidos no **ObjectDefinition** criadas no elemento de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instância se eles ainda não existir. Em outras palavras, o comando **Alter** é tratado como um comando **Create** se os objetos ainda não existirem na instância.<br /><br /> Se esse atributo for omitido ou definido como **false**, ocorrerá um erro se os objetos ainda não existirem.|  
|ObjectExpansion|(Atributo **Enum** opcional) Define a extensão da alteração a ser executada pelo método **Execute** .<br /><br /> Se for definido como *ObjectProperties*, o elemento **ObjectDefinition** deve conter somente a definição completa do principal objeto a ser alterado, incluindo os objetos menores subordinados. Os objetos grandes subordinados ao objeto a ser alterado permanecem iguais.<br /><br /> Observação: Ao usar o *ObjectProperties* configuração com o [ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md) tipo de dados, o [dados](../../../analysis-services/scripting/objects/data-element-assl.md) elemento associado [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) tipos de dados não precisa ser especificado. Se não for especificado, o elemento **ClrAssembly** usará os arquivos existentes.<br /><br /> Se for definido como *ExpandFull*, o elemento **ObjectDefinition** não deve conter apenas a definição do objeto a ser alterado, mas também as definições de todos os principais objetos que são descendentes do objeto a ser alterado.<br /><br /> Observação: O *ExpandFull* configuração não pode ser usada com a [Server](../../../analysis-services/scripting/objects/server-element-assl.md) elemento.|  
|Escopo|(Atributo **Enum** opcional) Define a duração dos objetos definidos no elemento **ObjectDefinition** .<br /><br /> Se for definido como *Session*, os objetos definidos no elemento **ObjectDefinition** existirão somente durante a sessão XMLA.<br /><br /> Observação: Ao usar o *sessão* configuração, o **ObjectDefinition** elemento só pode conter [dimensão](../../../analysis-services/scripting/objects/dimension-element-assl.md), [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md), ou [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) elementos ASSL.<br /><br /> Se esse atributo for omitido, os objetos definidos no **ObjectDefinition** elemento são mantidos no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instância.|  
  
## <a name="remarks"></a>Remarks  
 Cada **Alter** comando altera a definição de um objeto principal sob o objeto pai especificado o [ParentObject](../../../analysis-services/xmla/xml-elements-properties/parentobject-element-xmla.md) elemento.  
  
## <a name="see-also"></a>Confira também
 [Comandos &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-commands/xml-elements-commands.md)  
  
  
