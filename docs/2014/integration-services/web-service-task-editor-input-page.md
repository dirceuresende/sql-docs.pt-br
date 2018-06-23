---
title: Editor da tarefa serviço da Web (página entrada) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.dts.designer.webservicestask.input.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 93529c88-f540-47f2-a10a-12c87318ed6f
caps.latest.revision: 29
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 8f458f4a2898915102ab2a05b04fb7ba223c5e30
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36119139"
---
# <a name="web-service-task-editor-input-page"></a>Editor da Tarefa Serviço da Web (página Entrada)
  Use a página **Entrada** da caixa de diálogo do **Editor da Tarefa Serviço da Web** para especificar o Serviço da Web, o método Web e os valores a serem fornecidos ao método Web como entrada. Os valores podem ser fornecidos digitando cadeias de caracteres diretamente na coluna Valor ou selecionando variáveis na coluna Valor.  
  
 Para saber mais sobre essa tarefa, consulte [Tarefa Serviço da Web](control-flow/web-service-task.md).  
  
## <a name="options"></a>Opções  
 **Serviço**  
 Selecione na lista um serviço da Web a ser usado para executar o método Web.  
  
 **Método**  
 Selecione na lista um método Web a ser executado pela tarefa.  
  
 **WebMethodDocumentation**  
 Digite uma descrição do método Web ou clique no botão Procurar **(...)** e digite a descrição na caixa de diálogo **Documentação do Método Web** .  
  
 **Nome**  
 Lista os nomes das entradas no método Web.  
  
 **Tipo**  
 Lista o tipo de dados das entradas.  
  
> [!NOTE]  
>  A tarefa Serviço da Web só suporta parâmetros dos seguintes tipos de dados: tipos primitivos, como números inteiros e cadeias de caracteres; matrizes e sequências de tipos primitivos; e enumerações.  
  
 **Variável**  
 Marque as caixas de seleção para usar variáveis para fornecer entradas.  
  
 **Value**  
 Se as caixas de seleção Variável forem marcadas, selecione as variáveis na lista para fornecer as entradas; caso contrário, digite os valores a serem usados nas entradas.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor da tarefa serviço da Web &#40;página geral&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor da tarefa serviço da Web &#40;de saída de página&#41;](../../2014/integration-services/web-service-task-editor-output-page.md)   
 [Página Expressões](expressions/expressions-page.md)  
  
  