---
title: SQLGetData | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLGetData function
ms.assetid: 204848be-8787-45b4-816f-a60ac9d56fcf
caps.latest.revision: 42
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 04dce1dac418ed7ae2011928057bb09bf95c90c9
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43066515"
---
# <a name="sqlgetdata"></a>SQLGetData
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  **SQLGetData** é usado para recuperar dados de conjunto de resultados sem valores de coluna de associação. **SQLGetData** pode ser chamado sucessivamente na mesma coluna para recuperar grandes quantidades de dados em uma coluna com um tipo de dados **text**, **ntext**ou **image** .  
  
 Não há nenhum requisito de que aplicativo associe variáveis para buscar dados de conjunto de resultados. Os dados de qualquer coluna podem ser recuperados a partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC Native Client usando **SQLGetData**.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC Native Client não dá suporte ao uso **SQLGetData** para recuperar dados em ordem de coluna aleatória. Todas as colunas desassociadas processadas com **SQLGetData** devem ter ordinais de coluna mais altos que as colunas associadas no conjunto de resultados. O aplicativo deve processar dados do valor de coluna ordinal mais baixo desassociado para o mais alto. Tentar recuperar dados de uma coluna ordinalmente inferior resulta em um erro. Caso esteja usando cursores de servidor para informar linhas do conjunto de resultados, o aplicativo pode buscar novamente a linha atual e buscar o valor de uma coluna. Se uma instrução for executada no cursor somente de avanço, somente leitura, você deverá executar novamente a instrução para fazer backup de **SQLGetData**.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC Native Client informa com precisão o comprimento de **texto**, **ntext**, e **imagem** dados recuperados por meio **SQLGetData** . O aplicativo pode usar bem o retorno do parâmetro *StrLen_or_IndPtr* para recuperar dados longos rapidamente.  
  
> [!NOTE]  
>  Para tipos de valor grandes, *StrLen_or_IndPtr* retornará SQL_NO_TOTAL em caixas de truncamento de dados.  
  
## <a name="sqlgetdata-support-for-enhanced-date-and-time-features"></a>Suporte de SQLGetData a recursos aprimorados de data e hora  
 Os valores de coluna de resultado dos tipos de data/hora são convertidos conforme descrito em [conversões de SQL para C](../../relational-databases/native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).  
  
 Para obter mais informações, consulte [aprimoramentos de data e hora &#40;ODBC&#41;](../../relational-databases/native-client-odbc-date-time/date-and-time-improvements-odbc.md).  
  
## <a name="sqlgetdata-support-for-large-clr-udts"></a>Suporte de SQLGetData a UDTs grandes do CLR  
 **SQLGetData** dá suporte a UDTs (tipos definidos pelo usuário) grandes do CLR. Para obter mais informações, consulte [Large CLR User-Defined tipos &#40;ODBC&#41;](../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md).  
  
## <a name="example"></a>Exemplo  
  
```  
SQLHDBC     hDbc = NULL;  
SQLHSTMT    hStmt = NULL;  
long        lEmpID;  
PBYTE       pPicture;  
SQLINTEGER  pIndicators[2];  
  
// Get an environment, connection, and so on.  
...  
  
// Get a statement handle and execute a command.  
SQLAllocHandle(SQL_HANDLE_STMT, hDbc, &hStmt);  
  
if (SQLExecDirect(hStmt,  
    (SQLCHAR*) "SELECT EmployeeID, Photo FROM Employees",  
    SQL_NTS) == SQL_ERROR)  
    {  
    // Handle error and return.  
    }  
  
// Retrieve data from row set.  
SQLBindCol(hStmt, 1, SQL_C_LONG, (SQLPOINTER) &lEmpID, sizeof(long),  
    &pIndicators[0]);  
  
while (SQLFetch(hStmt) == SQL_SUCCESS)  
    {  
    cout << "EmployeeID: " << lEmpID << "\n";  
  
    // Call SQLGetData to determine the amount of data that's waiting.  
    if (SQLGetData(hStmt, 2, SQL_C_BINARY, pPicture, 0, &pIndicators[1])  
        == SQL_SUCCESS_WITH_INFO)  
        {  
        cout << "Photo size: " pIndicators[1] << "\n\n";  
  
        // Get all the data at once.  
        pPicture = new BYTE[pIndicators[1]];  
        if (SQLGetData(hStmt, 2, SQL_C_DEFAULT, pPicture,  
            pIndicators[1], &pIndicators[1]) != SQL_SUCCESS)  
            {  
            // Handle error and continue.  
            }  
  
        delete [] pPicture;  
        }  
    else  
        {  
        // Handle error on attempt to get data length.  
        }  
    }  
```  
  
## <a name="see-also"></a>Consulte também  
 [Função SQLGetData](http://go.microsoft.com/fwlink/?LinkId=59350)   
 [Detalhes da implementação da API do ODBC](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
