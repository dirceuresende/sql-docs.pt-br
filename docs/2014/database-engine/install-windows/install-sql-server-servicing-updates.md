---
title: Instalar atualizações de serviço do SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 7d6c962b-c8d0-49f7-a2ac-00ad8dca930a
caps.latest.revision: 13
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: cd85a71e376fe4502372f5f9885dd4d048d21742
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37153097"
---
# <a name="install-sql-server-2014-servicing-updates"></a>Instalar atualizações de serviço do SQL Server 2014
  Este tópico fornece informações sobre como instalar atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. Esta seção fornece informações sobre o seguinte:  
  
-   Instalando atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durante uma nova instalação  
  
-   Instalando atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] depois que já tiver sido instalado.  
  
 Nós recomendamos que os clientes avaliem e instalem as atualizações mais recentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o mais rápido possível para ter certeza de que os sistemas estejam atualizados com as atualizações de segurança mais recentes.  
  
## <a name="installing-updates-for-includesscurrentincludessscurrent-mdmd-during-a-new-installation"></a>Instalando atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durante uma nova instalação  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integra as últimas atualizações de produto com a instalação principal de produto, de forma que o produto principal e suas atualizações aplicáveis sejam instalados ao mesmo tempo. A atualização de produto pode pesquisar as atualizações aplicáveis de:  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update (atualizar)  
  
-   Windows Server Update Services (WSUS)  
  
-   Uma pasta local  
  
-   Um compartilhamento de rede  
  
 Depois que a Instalação localizar as versões mais recentes das atualizações aplicáveis, ela baixará e integrará essas atualizações com o processo de instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atual. A Atualização de Produto pode incluir uma atualização cumulativa, service pack ou service pack mais atualização cumulativa. Funcionalidade de atualização de produto é uma extensão do [funcionalidade de instalação integrada](http://go.microsoft.com/fwlink/?LinkId=219945) que estava disponível no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.  
  
## <a name="installing-updates-for-includesscurrentincludessscurrent-mdmd-after-it-has-already-been-installed"></a>Instalando atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] depois que já tiver sido instalado  
 Em uma instância instalada do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], é recomendável que você aplique todas as atualizações disponíveis: versões de distribuição geral (GDR - atualizações críticas/de segurança), Service Packs (SP), bem como a mais recente disponível atualização cumulativa (CU).  
  
 Dependendo do tipo de versão de serviço, as atualizações do SQL Server estão disponíveis por meio do Microsoft Update (MU), Microsoft Download Center e/ou o hotfix de serviços de atendimento ao servidor. Atualizações críticas e de segurança para o SQL Server são fornecidas automaticamente pelo Microsoft Update (deve ser capaz de ver estas atualizações que necessárias para participar de MU por meio do Windows Update no painel de controle). Service Packs estão disponíveis no MU como opcional/importante baixa, bem como o Centro de Download. As atualizações cumulativas estão disponíveis no servidor de download do hotfix do Microsoft fornecido nos artigos da Base de dados de conhecimento do CU.  
  
## <a name="see-also"></a>Consulte também  
 [Instalar o SQL Server 2014 do Assistente de instalação &#40;programa de instalação&#41;](install-sql-server-from-the-installation-wizard-setup.md)   
 [Adicionar recursos a uma instância do SQL Server 2014 &#40;programa de instalação&#41;](add-features-to-an-instance-of-sql-server-setup.md)   
 [Remover uma instalação do SQL Server 2014](repair-a-failed-sql-server-installation.md)  
  
  
