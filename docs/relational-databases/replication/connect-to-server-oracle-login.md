---
title: Conectar ao Servidor (Oracle), Logon | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: replication
ms.reviewer: ''
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.rep.oracleconnection.login.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 86ed91a1-a07c-46f2-a913-67317ef2255e
caps.latest.revision: 20
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 80438932eb33a1a3fbb93136980d65b7bf354266
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37350158"
---
# <a name="connect-to-server-oracle-login"></a>Conectar ao Servidor (Oracle), Logon
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Use a guia **Logon** da caixa de diálogo **Conectar ao Servidor** para especificar a conta na qual as conexões são feitas do Distribuidor [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o Editor Oracle. Você deve usar a mesma conta especificada para o esquema de usuário administrativo de replicação durante a configuração do Publicador. Para obter mais informações, consulte [Configure an Oracle Publisher](../../relational-databases/replication/non-sql/configure-an-oracle-publisher.md) (Configurar um publicador do Oracle).  
  
## <a name="options"></a>Opções  
 **Instância de servidor**  
 O nome TNS (Transparent Network Substrate) do Editor Oracle, especificado durante a configuração do software cliente Oracle instalado no Distribuidor.  
  
 **Autenticação**  
 Selecione **Autenticação Padrão da Oracle** (recomendado) ou **Autenticação do Windows**. Se você selecionar **Autenticação do Windows**:  
  
-   O servidor Oracle deve ser configurado para permitir conexões que usam credenciais do Windows. Para obter mais informações, consulte a documentação Oracle.  
  
-   Você deve estar registrado atualmente na mesma conta [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows especificada para o esquema de usuário administrativo de replicação.  
  
 **Logon** e **Senha**  
 Se você tiver selecionado **Autenticação Padrão da Oracle** para a opção **Autenticação** , especifique o logon e a senha a serem usados, que devem ser os mesmos que os especificados para o esquema de usuário administrativo de replicação.  
  
## <a name="see-also"></a>Consulte Também  
 [Glossary of Terms for Oracle Publishing](../../relational-databases/replication/non-sql/glossary-of-terms-for-oracle-publishing.md)  
  
  
