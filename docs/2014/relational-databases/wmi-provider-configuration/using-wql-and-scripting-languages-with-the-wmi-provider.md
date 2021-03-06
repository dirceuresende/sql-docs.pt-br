---
title: Usando o WQL linguagens e de scripts com o provedor WMI para gerenciamento de configuração | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- queries [WMI]
- scripts [WMI]
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
- WMI Provider for Configuration Management, scripts
ms.assetid: c1e64905-3c2b-4974-88f4-abf17cf7e289
caps.latest.revision: 17
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 7a55fc42e5186615dbe3e455668eb8cc5f7c199c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37202876"
---
# <a name="using-wql-and-scripting-languages-with-the-wmi-provider-for-configuration-management"></a>Usando as linguagens WQL e de scripts com o provedor WMI para gerenciamento de configuração
  Os aplicativos de gerenciamento acessam os serviços e configurações de rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Provedor WMI (Instrumentação de Gerenciamento do Windows) para objetos de Gerenciamento de Configuração de duas maneiras:  
  
-   Usando um editor de WQL ou ferramenta de consulta, como o WBEMTest.exe para consultar o objeto definido com WQL (Linguagem de Instrumentação de Gerenciamento do Windows).  
  
-   Usando uma linguagem de scripts, como o VBScript.  
  
 Como alternativa, os serviços e configurações de rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser gerenciados via programação usando objetos gerenciados WMI no SMO. Para obter mais informações sobre a programação de WMI objetos gerenciados, consulte [gerenciamento de serviços e configurações de rede usando o provedor de WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).  
  
 O Provedor WMI para Gerenciamento de Configuração pode ser acessado usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager e o Console de Gerenciamento [!INCLUDE[msCoName](../../includes/msconame-md.md)]. Para obter mais informações sobre como acessar o provedor WMI de uma interface de usuário, consulte [Gerenciando tópicos de instruções de serviços &#40;SQL Server Configuration Manager&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).  
  
## <a name="see-also"></a>Consulte também  
 [Acessar o provedor WMI para gerenciamento de configuração usando o WQL](access-wmi-provider-for-configuration-management-using-wql.md)   
 [Modificar as propriedades avançadas do serviço do SQL Server usando o VBScript](access-wmi-provider-for-configuration-management-using-vbscript.md)  
  
  
