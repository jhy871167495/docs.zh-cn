---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: 44954dcc1f3407a768ba23fe87ac4b4abcf1bac5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761332"
---
# <a name="createref-entity-sql"></a>CREATEREF (Entity SQL)
创建对实体集中的实体的引用。  
  
## <a name="syntax"></a>语法  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a>自变量  
 `entityset_identifier`  
 实体集标识符，不是字符串文本。  
  
 `row_typed_expression`  
 对应于实体类型的键属性的行类型化表达式。  
  
## <a name="remarks"></a>备注  
 `row_typed_expression` 必须在结构上等效于实体的键类型。 即，其字段的数目和类型以及顺序必须与实体键相同。  
  
 在下面的示例中，Orders 和 BadOrders 都是类型 Order 的实体集，而假定 Id 为 Order 的单个键属性。 该示例演示如何生成对 BadOrders 中的实体的引用。 请注意，该引用可以是无关联引用。  即，该引用可以不真正标识特定实体。 在这种情况下，对该引用的 `DEREF` 操作会返回 Null。  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 CREATEREF 运算符创建对实体集中的实体的引用。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
