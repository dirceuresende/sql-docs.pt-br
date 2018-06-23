---
title: Salvar um pacote como um modelo de pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- reusing packages
- templates [Integration Services]
ms.assetid: efe66cec-3933-4f6e-8d35-fe3d300de66c
caps.latest.revision: 16
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 9bf2bfd8cadad08243be765977b68115bf2ae6f6
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36005686"
---
# <a name="save-a-package-as-a-package-template"></a>Salvar um pacote como um modelo de pacote
  Este tópico descreve como designar e usar pacotes personalizados como modelos para criar novos pacotes do Integration Services no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. Por padrão, o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] usa um modelo de pacote que cria um pacote vazio quando você adiciona um novo pacote a um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Você não pode substituir este modelo padrão, mas pode adicionar novos modelos.  
  
 Você pode designar vários pacotes para serem usados como modelos. Antes de implementar os pacotes personalizados como modelos, é preciso criá-los.  
  
 Ao criar um pacote usando os pacotes personalizados como modelos, os novos pacotes apresentam o mesmo nome e GUID do modelo. Para obter a diferenciação dos pacotes, atualize o valor da propriedade `Name` e gere uma nova GUID para a propriedade `ID`. Para obter mais informações, consulte [Criar pacotes no SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) e [Definir Propriedades de Pacote](set-package-properties.md).  
  
### <a name="to-designate-a-custom-package-as-a-package-template"></a>Para designar um pacote personalizado como um modelo de pacote  
  
1.  No sistema de arquivos, localize o pacote que deseja usar como modelo.  
  
2.  Copie o pacote para a pasta DataTransformationItems. Por padrão, esta pasta está em C:\Arquivos de Programas\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.  
  
3.  Repita as etapas 1 e 2 para cada pacote que quiser usar como modelo.  
  
### <a name="to-use-a-custom-package-as-a-package-template"></a>Para usar um pacote personalizado como um modelo de pacote  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no qual você deseja criar um pacote.  
  
2.  No Gerenciador de Soluções, clique com o botão direito do mouse no projeto, aponte para **Adicionar** e clique em **Novo Item**.  
  
3.  Na caixa de diálogo **Adicionar Novo Item – \<nome do projeto**, clique no pacote que deseja usar como modelo.  
  
     A lista de modelos inclui o modelo padrão do pacote chamado Novo Pacote SSIS. O ícone do pacote identifica os modelos que podem ser usados como modelos de pacote.  
  
4.  Clique em **Adicionar**.  
  
## <a name="see-also"></a>Consulte também  
 [Criar pacotes no SQL Server Data Tools](create-packages-in-sql-server-data-tools.md)   
 [Pacotes do SSIS &#40;Integration Services&#41;](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  