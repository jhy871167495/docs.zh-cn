---
title: Decimal 数据类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 9e256e93d7857c8674a1d711fa9cafd3ed9a29f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591608"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal 数据类型 (Visual Basic)
保存有符号表示 96 位 （12 个字节） 整数变量 10 的幂缩放的数字的 128 位 （16 个字节） 值。 缩放因子指定数字的小数点; 右侧数它的范围介于 0 到 28。 小数位数为 0 （没有小数位），最大可能值为 + 79228162514264337593543950335 / (+ /-7.9228162514264337593543950335E + 28)。 带 28 个小数的最大值是 + /-7.9228162514264337593543950335，和的最小的非零值为 + /-0.0000000000000000000000000001 （+ /-1E-28)。  
  
## <a name="remarks"></a>备注  
 `Decimal`数据类型提供大量的最大有效位数数。 它支持最多 29 个有效位，并且可表示值超出 7.9228 x 10 ^28。 它是特别适合于计算，如财务、，需要大量的数字，但不能容忍舍入误差。  
  
 `Decimal` 的默认值为 0。  
  
## <a name="programming-tips"></a>编程提示  
  
-   **精度。** `Decimal` 不是浮点数据类型。 `Decimal`结构保存二进制整数值，以及一个符号位的整数比例因子，用于指定值的哪些部分是小数部分。 因此，`Decimal`数字在比浮点类型的内存中具有更精确的表示形式 (`Single`和`Double`)。  
  
-   **性能。** `Decimal`数据类型时速度最慢的所有数值类型。 你应权衡针对性能，而不选择数据类型的精度的重要性。  
  
-   **扩大转换。** `Decimal`数据类型加宽到`Single`或`Double`。 这意味着你可以将转换`Decimal`而不会遇到这些类型的任一<xref:System.OverflowException?displayProperty=nameWithType>错误。  
  
-   **尾随零。** Visual Basic 不会存储中的尾随零`Decimal`文本。 但是，`Decimal`变量将保留任何计算所得的尾随零。 下面的示例阐释了这一点。  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     输出`MsgBox`在前面的示例是，如下所示：  
  
     d1 = 2.375，d2 = 1.625，d3 = 4.000，d4 = 4  
  
-   **类型字符。** 将文本类型字符 `D` 追加到文本会将其强制转换为 `Decimal` 数据类型。 将标识符类型字符 `@` 追加到任何标识符会将其强制转换为 `Decimal`。  
  
-   **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Decimal?displayProperty=nameWithType> 结构。  
  
## <a name="range"></a>范围  
 你可能需要使用`D`键入要分配到较大的值的字符`Decimal`变量或常量。 此要求是因为编译器会将解释为文本`Long`除非文本类型字符后面的文本，如以下示例所示。  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 声明`bigDec1`不产生溢出，因为分配给它的值是否在范围内`Long`。 `Long`值可以分配给`Decimal`变量。  
  
 声明`bigDec2`生成溢出错误，因为分配给它的值太大`Long`。 因为数值不能首先被解释为`Long`，不能将它分配给`Decimal`变量。  
  
 有关`bigDec3`，文本类型字符`D`可解决问题，通过强制编译器将解释为文本`Decimal`而不是作为`Long`。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Single 数据类型](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
