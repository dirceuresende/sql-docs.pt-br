---
title: Omitindo valores para objetos opcionais de serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], omitted values
- XML Web service [Reporting Services], omitted values
- Report Server Web service, omitted values
- omitting values [Reporting Services]
ms.assetid: ceb68b8b-9214-4745-abc9-f47f33ecd6f7
caps.latest.revision: 36
author: douglaslM
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 47f3f940a7e4e8dfd7071c40b251e393dd7ad931
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36005837"
---
# <a name="omitting-values-for-optional-web-service-objects"></a>Omitindo valores para objetos de serviço Web opcionais
  Propriedades de vários tipos complexos de serviço Web Servidor de Relatórios têm uma propriedade complementar conhecida como propriedade Specified. O nome da propriedade consiste no nome de propriedade original com a palavra "Especificada" anexada a ele. A presença dessa propriedade indica que um valor da propriedade original às vezes pode ser omitido. Este é um resultado direto da conversão da WSDL (Web Service Description Language) em uma classe proxy [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Por exemplo, a propriedade de serviço Web <xref:ReportService2010.DataSourceDefinition.Enabled%2A> do tipo complexo <xref:ReportService2010.DataSourceDefinition> tem uma propriedade associada nomeada <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>. Se você estiver criando um aplicativo e não quiser definir um valor para a propriedade <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, não precisará fornecer um valor para <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; o valor padrão de `true` é usado. Porém, você ainda precisa definir <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> como `false`. Se você fornecer um valor para a propriedade <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, precisará definir <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> igual a `true`. Esse é o caso de propriedades graváveis. Para propriedades somente leitura, você não precisa tomar uma ação.  
  
> [!IMPORTANT]  
>  A falha em especificar uma propriedade usando a técnica supracitada pode resultar em comportamento de serviço Web imprevisível.  
  
 Os tipos de dados que costumam exigem que você trate a propriedade especificada adicional são `Boolean`, `DateTime`, e `Enumeration`.  
  
 Para obter um exemplo, consulte o método <xref:ReportService2010.ReportingService2010.CreateDataSource%2A>.  
  
## <a name="see-also"></a>Consulte também  
 [Criando aplicativos usando o serviço Web e o .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md)   
 [Referência técnica &#40;SSRS&#41;](../../technical-reference-ssrs.md)  
  
  