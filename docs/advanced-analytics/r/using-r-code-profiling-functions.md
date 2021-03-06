---
title: Usando funções (aprendizado de máquina do SQL Server) da criação de perfil de código de R | Microsoft Docs
ms.prod: sql
ms.technology: machine-learning
ms.date: 04/15/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: 05689ae356d415f9655b8709c619e40e6d8fa817
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31202168"
---
# <a name="using-r-code-profiling-functions"></a>Usando funções de criação de perfil de código de R
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

Além de usar recursos do SQL Server e ferramentas para monitorar a execução do script R, você pode usar ferramentas de desempenho fornecidas por outros pacotes de R para obter mais informações sobre chamadas de função internas. Este tópico fornece uma lista de alguns recursos básicos para você começar. Para obter diretrizes, recomendamos o capítulo [Performance](http://adv-r.had.co.nz/Performance.html) (Desempenho) no livro "Advanced R" (R avançado), de Hadley Wickham.

## <a name="using-rprof"></a>Usando RPROF

*rprof* é uma função incluída no pacote base **utils**, que é carregado por padrão. Uma vantagem de *rprof* é que ele executa a amostragem, reduzindo a carga de desempenho do monitoramento.

Para usar o R de criação de perfil em seu código, você chama essa função e especifica seus parâmetros, incluindo o nome do local do arquivo de log que será gravado. Consulte a ajuda do *rprof* para obter detalhes.

Em geral, a função *rprof* funciona escrevendo a pilha de chamadas em um arquivo aos intervalos especificados. Você pode usar a função *summaryRprof* para processar o arquivo de saída. 

A criação de perfil pode ser ativada e desativada em seu código. Para ativar a criação de perfil, suspender a criação de perfil e então reiniciá-la, você usaria uma sequência de chamadas para *rprof*:

1. Especifique o arquivo de saída de criação de perfil.

    ```R
    varOutputFile <- "C:/TEMP/run001.log")
    Rprof(varOutputFile)
    ```
2. Desligar a criação de perfil
    ```R
    Rprof(NULL)
    ```
    
3. Reiniciar criação de perfil
    ```R
    Rprof(append=TRUE)
    ```


> [!NOTE]
> Usar essa função requer que o Windows Perl esteja instalado no computador em que o código é executado. Portanto, é recomendável criar o perfil de código durante o desenvolvimento em um ambiente de R e, em seguida, implantar o código depurado no SQL Server.  


## <a name="r-system-functions"></a>Funções do Sistema R

A linguagem R inclui muitas funções de pacote básico para retornar o conteúdo de variáveis do sistema. 

Por exemplo, como parte do seu código R, você pode usar `Sys.timezone` para obter o fuso horário atual ou `Sys.Time` para obter a hora do sistema de R. 

Para obter informações sobre funções individuais do sistema R, digite o nome da função como argumento para a função R `help()` em um prompt de comando de R.

```R
help("Sys.time")
```

## <a name="debugging-and-profiling-in-r"></a>Depuração e criação de perfil em R

A documentação do Microsoft R Open, que é instalado por padrão, inclui um manual sobre o desenvolvimento de extensões para a linguagem R que aborda a criação de perfis e depuração em detalhes.

O capítulo também está disponível online: [https://cran.r-project.org/doc/manuals/r-release/R-exts.html#Debugging](https://cran.r-project.org/doc/manuals/r-release/R-exts.html#Debugging)

### <a name="location-of-r-help-files"></a>Local dos arquivos de ajuda do R

C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\R_SERVICES\doc\manual



