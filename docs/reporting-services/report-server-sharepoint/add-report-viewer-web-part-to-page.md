---
title: Adicionar a web part do Visualizador de Relatórios do SQL Server Reporting Services a uma página do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 09/26/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: report-server-sharepoint
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 3d63f40c62c1997be2d4944c8b67f328d2b64c2d
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38049124"
---
# <a name="add-sql-server-reporting-services-report-viewer-web-part-to-a-sharepoint-page"></a>Adicionar a web part do Visualizador de Relatórios do SQL Server Reporting Services a uma página do SharePoint

[!INCLUDE [ssrs-appliesto](../../includes/ssrs-appliesto.md)] [!INCLUDE[ssrs-appliesto-2016-and-later](../../includes/ssrs-appliesto-2016-and-later.md)] [!INCLUDE[ssrs-appliesto-sharepoint-2013-2016i](../../includes/ssrs-appliesto-sharepoint-2013-2016.md)] [!INCLUDE[ssrs-appliesto-pbirsi](../../includes/ssrs-appliesto-pbirs.md)]

Exiba um relatório, no SQL Server Reporting Services ou no Servidor de Relatórios do Power BI, adicionando uma web part do Visualizador de Relatórios a uma página do SharePoint.

![Web part do Visualizador de Relatórios em uma página do SharePoint](media/sharepoint-report-viewer-web-part-on-page.png)

## <a name="prerequisites"></a>Prerequisites

* Para que os relatórios sejam carregados com êxito, o C2WTS (Declarações para Serviço de Token do Windows) precisa ser configurado para a delegação restrita de Kerberos. Para obter mais informações sobre como configurar o C2WTS, consulte [C2WTS (Declarações para Serviço de Token do Windows) e Reporting Services](../install-windows/claims-to-windows-token-service-c2wts-and-reporting-services.md).

* A web part do Visualizador de Relatórios deve ser implantada no farm do SharePoint. Para obter informações sobre como implantar o projeto de solução da web part do Visualizador de Relatórios, consulte [Implantar a web part do Visualizador de Relatórios em um site do SharePoint](deploy-report-viewer-web-part.md).

* Para adicionar uma web part a uma página da Web, é necessário ter a permissão Adicionar e Personalizar Páginas no nível do site. Se você estiver usando as configurações de segurança padrão, essa permissão será concedida a membros do grupo **Proprietários** que tenham nível de permissão Controle Total.

## <a name="add-web-part"></a>Adicionar uma web part

1. No site do SharePoint, selecione o ícone de **engrenagem** no canto superior esquerdo e **Adicionar uma página**.

    ![Adicione uma página a um site do SharePoint por meio do ícone de engrenagem.](media/sharepoint-add-a-page.png)

2. Dê um nome à página e selecione **Criar**.

3. No designer de páginas, selecione a guia **Inserir** na faixa de opções. Em seguida, selecione **web part** na seção **Partes**.

    ![Insira uma web part por meio da faixa de opções do Office.](media/sharepoint-insert-web-part.png)

4. Em **Categorias**, selecione **SQL Server Reporting Services (modo Nativo). Em **Partes**, selecione **Visualizador de Relatórios**. Em seguida, selecione **Adicionar**.

    ![Adicione a web part do Visualizador de Relatórios.](media/sharepoint-report-viewer-web-part.png)

    Inicialmente, isso pode ser exibido com um erro. O erro ocorre porque a URL padrão do servidor de relatório é definida como *http://localhost* e pode não estar disponível nesse local.

## <a name="configure-the-report-viewer-web-part"></a>Configurar a web part do Visualizador de Relatórios

Para configurar a web part para que ela aponte para o relatório específico, realize o procedimento a seguir.

1. Ao editar a página do SharePoint, selecione a seta para baixo no canto superior direito da web part e selecione **Editar web part**.

    ![Edite a página da Web por meio do menu suspenso da web part.](media/sharepoint-edit-web-part.png)

2. Insira a **URL do Servidor de Relatório** do servidor de relatório que hospeda o relatório. Sua tabela deve ter a seguinte aparência *http://myrsserver/reportserver*.

3. Insira o caminho e o nome do relatório que deseja exibir na web part. Isso será semelhante a */AdventureWorks Sample Reports/Company Sales*. Neste exemplo, o relatório *Vendas da Empresa* está em uma pasta chamada *Relatórios de Exemplo do AdventureWorks*.

4. Se o relatório exigir parâmetros, depois de fornecer a URL do servidor de relatório e o nome do relatório, selecione **Carregar Parâmetros** na seção **Parâmetros**.

5. Selecione **OK** para salvar as alterações na configuração da web part.

6. Selecione **Salvar**, na faixa de opções do Office, para salvar as alterações na página do SharePoint.

![Web part do Visualizador de Relatórios em uma página do SharePoint](media/sharepoint-report-viewer-web-part-on-page.png)

## <a name="considerations-and-limitations"></a>Considerações e limitações

* A web part do Visualizador de Relatórios não pode ser usada em páginas modernas no SharePoint.
* Os relatórios do Power BI não podem ser usados com a web part do Visualizador de Relatórios.
* Se a web part do Visualizador de Relatórios não estiver visível, para adicioná-la à página, verifique se você [implantou a web part do Visualizador de Relatórios](deploy-report-viewer-web-part.md).

Ainda tem dúvidas? [Experimente perguntar no fórum do Reporting Services](http://go.microsoft.com/fwlink/?LinkId=620231)
