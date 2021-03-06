---
title: 'Etapa 7: Adicionando e configurando o destino OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: tutorial
applies_to:
- SQL Server 2016
ms.assetid: 442c841d-d528-4bf0-8724-7156f909ee50
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 5280503f66c70f5d9fe2955d376a71c139e27e27
ms.sourcegitcommit: de5e726db2f287bb32b7910831a0c4649ccf3c4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2018
ms.locfileid: "35329330"
---
# <a name="lesson-1-7---adding-and-configuring-the-ole-db-destination"></a>Lição 1-7 – adicionar e configurar o destino OLE DB
Seu pacote agora extrai dados de uma fonte de arquivo simples e transforma esses dados em um formato compatível com o destino. A próxima tarefa é carregar os dados transformados no destino. Para carregar os dados, você deve adicionar um destino OLE DB ao fluxo de dados. O destino do OLE DB pode usar uma tabela, exibição de banco de dados ou um comando SQL para carregar os dados em uma diversidade de bancos de dados compatíveis com o OLE DB.  
  
Neste procedimento, você adiciona e configura um destino OLE DB para usar o gerenciador de conexões OLE DB criado anteriormente.  
  
### <a name="to-add-and-configure-the-sample-ole-db-destination"></a>Para adicionar e configurar a amostra de destino do OLE DB  
  
1.  Na **Caixa de Ferramentas do SSIS**, expanda **Outros Destinos**e arraste **Destino OLE DB** até a superfície de design da guia **Fluxo de Dados** . Coloque o destino de OLE DB diretamente abaixo da transformação **Chave de Data de Pesquisa** .  
  
2.  Clique na transformação **Chave de Data de Pesquisa** e arraste a seta verde sobre o **Destino OLE DB** recém-adicionado para conectar os dois componentes.  
  
3.  Na caixa de diálogo **Seleção de Saída e Entrada** , na caixa de listagem **Saída** , clique em **Saída de Correspondência de Pesquisa**e em **OK**.  
  
4.  Na superfície de design de **Fluxo de Dados** , clique em **Destino OLE DB** , no componente **Destino de OLE DB** recém-adicionado e altere o nome para **Destino OLE DB de Exemplo**.  
  
5.  Clique duas vezes em **Destino OLE DB de Exemplo**.  
  
6.  Na caixa de diálogo **Editor de Destino do OLE DB** , verifique se **localhost.AdventureWorksDW2012** está selecionado na caixa **Gerenciador de Conexões OLE DB** .  
  
7.  Na caixa **Nome da tabela ou da exibição** , digite ou selecione **[dbo].[FactCurrencyRate]**.  
  
8.  Clique no botão **Novo** para criar uma nova tabela.  Altere o nome da tabela no script para **NewFactCurrencyRate**.  Clique em **OK**.  
  
9. Depois de clicar em **OK**, a caixa de diálogo será fechada e o **Nome da tabela ou da exibição** será alterado automaticamente para **NewFactCurrencyRate**.  
  
10. Clique em **Mapeamentos**.  
  
11. Verifique se as colunas de entrada **AverageRate**, **CurrencyKey**, **EndOfDayRate**e **DateKey** estão mapeadas corretamente para as colunas de destino. Se forem mapeadas colunas com o mesmo nome, o mapeamento estará correto.  
  
12. Clique em **OK**.  
  
13. Clique com o botão direito do mouse no destino **Destino OLE DB de Exemplo** e clique em **Propriedades**.  
  
14. Na janela Propriedades, verifique se a propriedade **LocaleID** está definida como **Inglês (Estados Unidos)** e se a propriedade**DefaultCodePage** está definida como **1252**.  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
[Etapa 8: Tornando o pacote da Lição 1 mais fácil de compreender](../integration-services/lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
## <a name="see-also"></a>Consulte Também  
[Destino OLE DB](../integration-services/data-flow/ole-db-destination.md)  
  
  
  
