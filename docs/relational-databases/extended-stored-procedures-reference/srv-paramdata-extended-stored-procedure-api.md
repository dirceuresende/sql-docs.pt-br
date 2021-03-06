---
title: srv_paramdata (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: extended-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- srv_paramdata
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_paramdata
ms.assetid: 3104514d-b404-47c9-b6d7-928106384874
caps.latest.revision: 30
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: d73d1e6f2cf07edf29d96ef358b085a89e427a5c
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32941511"
---
# <a name="srvparamdata-extended-stored-procedure-api"></a>srv_paramdata (API de procedimento armazenado estendido)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Em vez disso, use a Integração CLR.  
  
 Retorna o valor de um parâmetro de chamada de procedimento armazenado remoto. Essa função foi substituída pela função **srv_paraminfo**.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
void * srv_paramdata (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
```  
  
## <a name="arguments"></a>Argumentos  
 *srvproc*  
 É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto). A estrutura contém informações que a biblioteca do procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.  
  
 *n*  
 É o número do parâmetro. O primeiro parâmetro equivale ao número 1.  
  
## <a name="returns"></a>Retorna  
 Um ponteiro para o valor do parâmetro. Se o *n*-ésimo parâmetro for NULL, se não houver *n*-ésimo parâmetro ou não houver procedimento armazenado remoto, retornará NULL. Se o valor do parâmetro for uma cadeia de caracteres, ele não pode terminar com caractere nulo. Use **srv_paramlen** para determinar o tamanho da cadeia de caracteres.  
  
 Essa função retornará os valores a seguir se o parâmetro for um dos tipos de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Os dados de ponteiro indicam se o ponteiro para o tipo de dados é válido (VP), NULL ou não aplicável (N/A) e o conteúdo dos dados apontados.  
  
|Novos tipos de dados|Comprimento dos dados de entrada|  
|--------------------|-----------------------|  
|BITN|**NULL:** VP, NULL<br /><br /> **ZERO:** VP, NULL<br /><br /> **>=255:** N/A<br /><br /> **<255:** N/A|  
|BIGVARCHAR|**NULL:** NULL, N/A<br /><br /> **ZERO:** VP, NULL<br /><br /> **>=255:** VP, 255 chars<br /><br /> **<255:** VP, dados reais|  
|BIGCHAR|**NULL:** NULL, N/A<br /><br /> **ZERO:** VP, 255 espaços<br /><br /> **>=255:** VP, 255 chars<br /><br /> **<255:** VP, dados reais + preenchimento (até 255)|  
|BIGBINARY|**NULL:** NULL, N/A<br /><br /> **ZERO:** VP, 255 0x00<br /><br /> **>=255:** VP, 255 bytes<br /><br /> **<255:** VP, dados reais + preenchimento (até 255)|  
|BIGVARBINARY|**NULL:** NULL, N/A<br /><br /> **ZERO:** VP, 0x00<br /><br /> **>=255:** VP, 255 bytes<br /><br /> **<255:** VP, dados reais|  
|NCHAR|**NULL:** NULL, N/A<br /><br /> **ZERO:** VP, 255 espaços<br /><br /> **>=255:** VP, 255 chars<br /><br /> **<255:** VP, dados reais + preenchimento (até 255)|  
|NVARCHAR|**NULL:** NULL, N/A<br /><br /> **ZERO:** VP, NULL<br /><br /> **>=255:** VP, 255 chars<br /><br /> **<255:** VP, dados reais|  
|NTEXT|**NULL:** N/A<br /><br /> **ZERO:** N/A<br /><br /> **>=255:** N/A<br /><br /> **\<255:** N/A|  
  
 \* Os dados não terminam em nulo; nenhum aviso é emitido no truncamento de dados >255 caracteres.  
  
## <a name="remarks"></a>Remarks  
 Se você souber o nome do parâmetro, poderá usar **srv_paramnumber** para obter o número do parâmetro. Para determinar se um parâmetro é NULL, use **srv_paramlen**.  
  
 Quando uma chamada de procedimento armazenado remoto for feita com parâmetros, os parâmetros poderão ser passados pelo nome ou pela posição (sem-nome). Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro. Em caso de erro, o manipulador SRV_RPC ainda será chamado, mas aparecerá como se não houvesse parâmetros e **srv_rpcparams** retornará 0.  
  
> [!IMPORTANT]  
>  Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção. Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
## <a name="see-also"></a>Consulte Também  
 [srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;](../../relational-databases/extended-stored-procedures-reference/srv-rpcparams-extended-stored-procedure-api.md)  
  
  
