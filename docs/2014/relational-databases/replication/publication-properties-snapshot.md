---
title: Propriedades da publicação, instantâneo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.pubproperties.snapshotformat.f1
ms.assetid: 8e9133b1-fc37-4a85-8a7c-d5eaf172fbef
caps.latest.revision: 23
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 1d238cd2bce87f65c1d29936457e2b966eee40a5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37214896"
---
# <a name="publication-properties-snapshot"></a>Propriedades da Publicação, Instantâneo
  A página **Instantâneo** da caixa de diálogo **Propriedades de Publicação** permite que você defina o formato do instantâneo, o local da pasta de instantâneo e os scripts a serem executados antes e depois da aplicação do instantâneo. A pasta de instantâneo deve ser designada como compartilhada e ter permissões adequadas para os agentes que leem e gravam arquivos na pasta. Para obter mais informações sobre como proteger a pasta adequadamente, consulte [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md) (Proteger a pasta de instantâneo).  
  
> [!NOTE]  
>  As alterações exigem um novo instantâneo para a publicação. Para obter mais informações, consulte [Alterar propriedade da publicação e do artigo](publish/change-publication-and-article-properties.md).  
  
## <a name="options"></a>Opções  
 **Formato do instantâneo**  
 Selecione modo nativo ou modo de caractere para o formato do instantâneo.  
  
-   Selecione **Native SQL Server - todos os Assinantes devem ser servidores executando o SQL Server** se todos os Assinantes forem instâncias do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diferentes do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)]. O formato de instantâneo nativo fornece o melhor desempenho.  
  
-   Selecione **Caractere - necessário se um Publicador ou Assinante não estiver executando o SQL Server** se nenhum Assinante estiver executando o [!INCLUDE[ssEW](../../includes/ssew-md.md)] ou forem Assinantes não[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Local dos arquivos de instantâneo**  
 Selecione o local para armazenar arquivos de instantâneo. Eles podem ser armazenados no local padrão; e também, em vez disso, podem ser armazenados em um local alternativo ou em outro local além do local padrão. Arquivos armazenados em um local alternativo podem ser compactados.  
  
-   Selecione **Colocar os arquivos na pasta padrão** para usar a pasta de instantâneo padrão para o Publicador. O local da pasta de instantâneo é somente leitura nessa caixa de diálogo porque ele só pode ser alterado para o Publicador na caixa de diálogo **Propriedades do Distribuidor** . Para obter mais informações, consulte [Specify the Default Snapshot Location &#40;SQL Server Management Studio&#41](specify-the-default-snapshot-location-sql-server-management-studio.md) [Especificar o local de instantâneo padrão (SQL Server Management Studio)].  
  
-   Selecione **Colocar os arquivos nesta pasta** para especificar, em vez disso, um local alternativo ou outro local além do padrão. Insira em um caminho na caixa de texto ou clique em **Procurar** e navegue até um local. Selecione **Compactar arquivos de instantâneo nesta pasta** para compactar os arquivos no local de instantâneo alternativo. O local alternativo pode ser em outro servidor, em uma unidade de rede ou em uma mídia removível, como um CD-ROM ou disco removível. Para obter mais informações, consulte [Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md) e [Compressed Snapshots](compressed-snapshots.md).  
  
 **Executar scripts adicionais**  
 Especifique scripts a serem executados antes e depois que o instantâneo for aplicado ao Assinante. Não poderão ser especificados scripts se o **Formato do instantâneo** for **Caractere**.  
  
 Os scripts são opcionais, mas fornecem um modo conveniente de executar comandos e aplicar alterações administrativas nos Assinantes. Para obter mais informações sobre a execução de scripts, consulte [Execute Scripts Before and After the Snapshot Is Applied](execute-scripts-before-and-after-the-snapshot-is-applied.md) (Executar scripts antes e após a aplicação do instantâneo).  
  
-   Insira um caminho na caixa de texto **Depois de aplicar o instantâneo, executar este script** ou clique em **Procurar** para especificar um local para o script.  
  
-   Insira um caminho na caixa de texto **Após aplicar o instantâneo, executar este script** ou clique em **Procurar** para especificar um local para o script.  
  
## <a name="see-also"></a>Consulte também  
 [Create a Publication](publish/create-a-publication.md)   
 [Exibir e modificar as propriedades da publicação](publish/view-and-modify-publication-properties.md)   
 [Criar e aplicar o instantâneo inicial](create-and-apply-the-initial-snapshot.md)   
 [Inicializar uma assinatura com um instantâneo](initialize-a-subscription-with-a-snapshot.md)   
 [Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md)  
  
  
