---
title: Conceder permissões ao serviço Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 0c2caa68-7834-4ea0-bd77-4f3a7c86d634
caps.latest.revision: 7
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 4de544925778a159fd16deb54833b1d94cf5d232
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37158607"
---
# <a name="grant-permissions-to-integration-services-service"></a>Conceder permissões ao serviço Integration Services
  Nas versões anteriores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], por padrão, quando você instalava o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , todos os usuários no grupo Usuários tinham acesso ao serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Quando você instala a versão atual do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], os usuários não têm acesso ao serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Por padrão, o serviço é protegido. Depois que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] é instalado, o administrador deve conceder acesso ao serviço.  
  
### <a name="to-grant-access-to-the-integration-services-service"></a>Para conceder acesso ao serviço Integration Services  
  
1.  Execute Dcomcnfg.exe. Dcomcnfg.exe fornece uma interface do usuário para modificar certas configurações no Registro.  
  
2.  Na caixa de diálogo **Serviços de Componentes**, expanda o nó Serviços de Componentes > Computadores > Meu Computador > Configuração de DCOM.  
  
3.  Clique com botão direito **Microsoft SQL Server Integration Services 12.0**e, em seguida, clique em **propriedades**.  
  
4.  Na guia **Segurança** , clique em **Editar** na área **Permissões de Inicialização e Ativação** .  
  
5.  Adicione os usuários e atribua permissões apropriadas e clique em Ok.  
  
6.  Repita as etapas 4 a 5 para Permissões de Acesso.  
  
7.  Reinicie o SQL Server Management Studio.  
  
8.  Reinicie o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .  
  
  
