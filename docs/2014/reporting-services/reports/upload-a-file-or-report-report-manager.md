---
title: Carregar um arquivo ou relatório (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
ms.assetid: 79027e11-f4ba-4bfd-bd8c-d334e3da02a1
caps.latest.revision: 41
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 44dd1787da648e332c2234b83323990784b0d4bc
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39085438"
---
# <a name="upload-a-file-or-report-report-manager"></a>Carregar um arquivo ou relatório (Gerenciador de Relatórios)
  O Gerenciador de Relatórios fornece um recurso de carregamento que permite adicionar relatórios, modelos e outros arquivos a um servidor de relatório sem publicar esses itens a partir de um aplicativo cliente. Os arquivos carregados a partir do sistema de arquivos são armazenados como itens no servidor de relatório. O tipo de arquivo carregado determina o modo de armazenamento:  
  
-   Os arquivos .rdl são armazenados como relatórios.  
  
-   Os arquivos .smdl são armazenados como modelos de relatório.  
  
-   Todos os outros arquivos, incluindo os arquivos de fonte de dados compartilhada (.rds), são carregados como recursos. Os recursos não são processados por um servidor de relatório, mas podem ser exibidos no Gerenciador de Relatórios se o servidor de relatório oferecer suporte ao tipo MIME de arquivo.  
  
### <a name="to-upload-a-file-or-report"></a>Para carregar um arquivo ou relatório  
  
1.  Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).  
  
2.  No Gerenciador de Relatórios, navegue até a página **Conteúdo** . Navegue até a pasta à qual deseja adicionar um item.  
  
3.  Clique em **Carregar Arquivo**.  
  
4.  Clique em **Procurar** para selecionar o arquivo a ser carregado. Você pode carregar um arquivo de definição de relatório, uma imagem, um documento ou qualquer arquivo que deseje disponibilizar no servidor de relatório.  
  
5.  Digite um nome para o novo item. Um nome de item pode incluir espaços, mas não pode incluir os caracteres reservados: ; ? : \@ & = +, $ / * \< > |.  
  
6.  Se desejar substituir um item existente pelo novo item, selecione **Substituir item, se existir**.  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Criar, excluir ou modificar uma fonte de dados compartilhada &#40;Gerenciador de relatórios&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md)   
 [Página de conteúdo &#40;Gerenciador de relatórios&#41;](../contents-page-report-manager.md)   
 [Página Carregar Arquivo &#40;Gerenciador de Relatórios&#41;](../upload-file-page-report-manager.md)   
 [Carregar arquivos em uma pasta](../report-server/upload-files-to-a-folder.md)  
  
  
