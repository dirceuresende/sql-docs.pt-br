---
title: Usar uma expressão em uma restrição de precedência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- precedence constraints [Integration Services], adding expressions
- expressions [Integration Services], adding
ms.assetid: 601038bb-3b17-42ac-b09d-5b3a82fb6564
caps.latest.revision: 44
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 31e3e002996d523aa225e0d0bb607d1772d8b0e7
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37273062"
---
# <a name="use-an-expression-in-a-precedence-constraint"></a>Usar uma expressão em uma restrição de precedência
  Este procedimento descreve como adicionar uma expressão a uma restrição de precedência usando a caixa de diálogo **Editor de Restrição de Precedência**. Antes de você poder adicionar uma expressão a uma restrição de precedência, o pacote deve incluir pelo menos dois executáveis, tarefas ou contêineres, e eles devem ser conectados por uma restrição de precedência.  
  
### <a name="to-add-an-expression-to-a-precedence-constraint"></a>Como adicionar uma expressão a uma restrição de precedência  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.  
  
2.  No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.  
  
3.  Clique na guia **Fluxo de Controle** .  
  
4.  Na superfície de design da guia **Fluxo de Controle** , clique duas vezes na restrição de precedência. O **Editor de Restrição de Precedência** será aberto.  
  
5.  Selecione **Expressão**, **Expressão e Restrição**ou **Expressão ou Restrição** na lista **Operação de avaliação** .  
  
6.  Digite uma expressão na caixa de texto **Expressão** ou inicie o Construtor de Expressões para criar uma expressão.  
  
7.  Para validar a sintaxe da expressão, clique em **Testar**.  
  
8.  Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .  
  
## <a name="see-also"></a>Consulte também  
 [Restrições de precedência](control-flow/precedence-constraints.md)   
 [Como conectar tarefas e contêineres por meio de uma restrição de precedência padrão](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md)   
 [Defina o valor de uma restrição de precedência usando o Menu de atalho](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md)   
 [Definir as propriedades de uma restrição de precedência](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)   
 [Expressões do SSIS &#40;Integration Services&#41;](expressions/integration-services-ssis-expressions.md)  
  
  
