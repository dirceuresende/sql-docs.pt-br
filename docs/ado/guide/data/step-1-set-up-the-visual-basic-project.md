---
title: 'Etapa 1: Configurar o projeto do Visual Basic | Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 77d3bfa5-fc9f-4a72-93b4-790c7d227988
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: eeecb16bd73df86dfdd40013b0a01cd8f90947ff
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35272855"
---
# <a name="step-1-set-up-the-visual-basic-project"></a>Etapa 1: Configurar o projeto do Visual Basic
Nesse cenário, supõe-se ter o Microsoft Visual Basic 6.0, ADO 2.5 ou posterior e o Microsoft OLE DB Provider para publicação de Internet instalado em seu sistema. Você primeiro crie um novo projeto e, em seguida, adicione alguns controles ao formulário padrão do projeto.  
  
### <a name="to-create-an-ado-project"></a>Para criar um projeto do ADO:  
  
1.  No Microsoft Visual Basic, crie um novo projeto EXE padrão.  
  
2.  No menu projeto, escolha as referências.  
  
3.  Selecione "Microsoft ActiveX Data Objects 2.5 Library" e clique em Okey.  
  
### <a name="to-insert-controls-on-the-main-form"></a>Para inserir controles no formulário principal:  
  
1.  Adicione um controle ListBox ao Form1. Defina sua propriedade Name **lstMain**.  
  
2.  Adicione outro controle ListBox ao Form1. Defina sua propriedade Name **lstDetails**.  
  
3.  Adicione um controle TextBox para Form1. Defina sua propriedade Name **txtDetails**.  
  
## <a name="see-also"></a>Consulte também  
 [Cenário de publicação na Internet](../../../ado/guide/data/internet-publishing-scenario.md)   
 [Etapa 2: Inicializar a caixa de listagem principal](../../../ado/guide/data/step-2-initialize-the-main-list-box.md)
