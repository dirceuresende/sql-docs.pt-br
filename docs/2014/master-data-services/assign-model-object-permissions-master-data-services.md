---
title: Atribuir permissões de objeto modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], assigning object permissions
- permissions [Master Data Services], assigning model object permissions
ms.assetid: 4b80148d-2318-415c-9479-28c240e48bcd
caps.latest.revision: 5
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 0a81b831ea324d71e6c5ac6c7cef92549e76cc65
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37309946"
---
# <a name="assign-model-object-permissions-master-data-services"></a>Atribuir permissões de objeto modelo (Master Data Services)
  No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], atribua permissões a objetos modelo quando você precisar fornecer a um usuário ou grupo o acesso aos dados na área funcional **Explorer** do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], ou quando precisar tornar um usuário ou grupo um administrador.  
  
> [!NOTE]  
>  Quando você atribui permissão a um modelo, a permissão a todos os outros modelos é negada implicitamente. Se você não atribuir permissões a objetos de modelo, o usuário ou grupo não poderá acessar nenhum dado no **Explorer**.  
  
## <a name="prerequisites"></a>Prerequisites  
 Para executar esse procedimento:  
  
-   Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).  
  
### <a name="to-assign-model-object-permissions"></a>Para atribuir permissões de objeto de modelo  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.  
  
2.  Na página **Usuários** ou **Grupos** , selecione a linha do usuário ou grupo que deseja editar.  
  
3.  Clique em **Editar usuário selecionado**.  
  
4.  Clique na guia **Modelos** .  
  
5.  Opcionalmente, selecione um modelo na lista **Modelo** .  
  
6.  Clique em **Editar**.  
  
7.  Expanda a árvore e clique no objeto de modelo ao qual deseja atribuir permissões.  
  
8.  No menu, selecione **somente leitura**, **atualização**, ou **Deny**.  
  
9. Clique em **Salvar**.  
  
## <a name="next-steps"></a>Próximas etapas  
  
-   (Opcional) [Atribuir permissões de membro de hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)  
  
## <a name="see-also"></a>Consulte também  
 [Excluir permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md)   
 [Permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md)   
 [Criar um administrador de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-administrator-master-data-services.md)  
  
  
