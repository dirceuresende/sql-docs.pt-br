---
title: Transferir o Editor de tarefa de mensagens de erro (página mensagens) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.errormessages.F1
helpviewer_keywords:
- Transfer Error Messages Task Editor
ms.assetid: cb2226a0-3037-4fdf-966f-81eabc0da9cf
caps.latest.revision: 20
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2ee60f4bfe93996ee753f06063bcf7b16aef4d02
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37209416"
---
# <a name="transfer-error-messages-task-editor-messages-page"></a>Editor da Tarefa Transferir Mensagens de Erro (página Mensagens)
  Use a página **Mensagens** da caixa de diálogo **Editor da Tarefa Transferir Mensagens de Erro** para especificar as propriedades de cópia de uma ou mais mensagens de erro [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] definidas pelo usuário de uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para outra. Para obter mais informações sobre essa tarefa, consulte [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).  
  
## <a name="options"></a>Opções  
 **SourceConnection**  
 Selecione um gerenciador de conexões SMO na lista ou clique em **\<Nova conexão...>** para criar uma nova conexão com o servidor de origem.  
  
 **DestinationConnection**  
 Selecione um gerenciador de conexões SMO na lista ou clique em **\<Nova conexão...>** para criar uma nova conexão com o servidor de destino.  
  
 **IfObjectExists**  
 Selecione se a tarefa deve substituir mensagens de erro definidas pelo usuário existentes, ignorar mensagens existentes ou causar falha se mensagens de erro de mesmo nome já existirem no servidor de destino.  
  
 **TransferAllErrorMessages**  
 Selecione se a tarefa deve copiar todas ou somente as mensagens especificadas definidas pelo usuário do servidor de origem para o servidor de destino.  
  
 As opções desta propriedade estão listadas na seguinte tabela:  
  
|Valor|Description|  
|-----------|-----------------|  
|**Verdadeiro**|Copia todas as mensagens definidas pelo usuário.|  
|**Falso**|Copia só as mensagens definidas pelo usuário especificadas.|  
  
 **ErrorMessagesList**  
 Clique no botão Procurar **(...)** para selecionar as mensagens de erro para copiar.  
  
> [!NOTE]  
>  É necessário especificar o **SourceConnection** antes que seja possível selecionar mensagens de erro para copiar.  
  
 **ErrorMessageLanguagesList**  
 Clique no botão Procurar **(...)** para selecionar os idiomas para os quais copiar mensagens de erro definidas pelo usuário para o servidor de destino. Uma versão us_english (página de código 1033) da mensagem deve estar no servidor de destino para que seja possível transferir versões da mensagem em outro idioma para esse servidor.  
  
> [!NOTE]  
>  É necessário especificar o **SourceConnection** antes que seja possível selecionar mensagens de erro para copiar.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Tarefas do Integration Services](control-flow/integration-services-tasks.md)   
 [Editor de tarefa de mensagens de erro de transferência &#40;página geral&#41;](general-page-of-integration-services-designers-options.md)   
 [Gerenciador de Conexão do SMO](connection-manager/smo-connection-manager.md)   
 [Editor de tarefa de mensagens de erro de transferência &#40;página geral&#41;](general-page-of-integration-services-designers-options.md)   
 [Gerenciador de Conexões SMO](connection-manager/smo-connection-manager.md)  
  
  
