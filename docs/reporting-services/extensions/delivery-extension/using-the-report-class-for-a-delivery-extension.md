---
title: Usando a classe Report para uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: extensions
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- delivery extensions [Reporting Services], report information
- Report class
ms.assetid: 1145ac63-eafd-452a-82af-16f85b1676dd
caps.latest.revision: 34
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: e08443a3b986489def7c0621e78b4dc4f853450f
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "33016133"
---
# <a name="using-the-report-class-for-a-delivery-extension"></a>Usando a classe Report para uma extensão de entrega
  A classe de <xref:Microsoft.ReportingServices.Interfaces.Report> representa um relatório no banco de dados do servidor de relatório. Qualquer assinatura é associada a um relatório específico. O relatório está contido na notificação. A sua extensão de entrega pode usar o objeto de <xref:Microsoft.ReportingServices.Interfaces.Report> que faz parte da notificação para renderizar o relatório. O objeto de <xref:Microsoft.ReportingServices.Interfaces.Report> também contém propriedades específicas do relatório, como a URL para o relatório no servidor de relatório e o nome do relatório. Todas essas propriedades podem ser usadas como parte de seu provedor de entrega.  
  
 O método de <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> da classe de <xref:Microsoft.ReportingServices.Interfaces.Report> pode ser usado para renderizar um relatório. O método <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> retorna uma matriz de um ou mais objetos de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> que, juntos, formam um único relatório renderizado. O primeiro objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> é o relatório renderizado. Qualquer outro objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> será o recurso a ser entregue junto com os dados de relatório (por exemplo, um arquivo HTML e as imagens associadas). A renderização de extensões que são extensões de renderização de fluxo único (IMAGE, PDF, MHTML e Excel) retornará só um objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> na matriz.  
  
 O objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> que contém o fluxo de relatório pode ser incluído como parte de uma entrega.  
  
 Para obter um exemplo de como usar a classe <xref:Microsoft.ReportingServices.Interfaces.Report>, consulte [Amostras de produto do SQL Server Reporting Services](http://go.microsoft.com/fwlink/?LinkId=177889)  
  
## <a name="see-also"></a>Consulte Também  
 [Implementando uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)   
 [Biblioteca de extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)   
 [Usar a classe RenderedOutputFile para uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
  
  
