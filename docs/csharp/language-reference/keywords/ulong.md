---
title: ulong 关键字（C# 引用）
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: d0c7df4ebda13a59e51e9599699f6abf4bbf1d71
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143423"
---
# <a name="ulong-c-reference"></a>ulong（C# 参考）

`ulong` 关键字表示一种整型类型，该类型根据下表显示的大小和范围存储值。

|类型|范围|大小|.NET 类型|
|----------|-----------|----------|-------------------------|
|`ulong`|0 到 18,446,744,073,709,551,615|无符号 64 位整数|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a>文本

可以通过为其分配十进制文本、十六进制文本或（从 C# 7.0 开始）二进制文本来声明和初始化 `ulong` 变量。  如果整数文本在 `ulong` 范围之外（即，如果它小于 <xref:System.UInt64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在以下示例中，表示为十进制、十六进制和二进制文本且等于 7,934,076,125 的整数被分配给 `ulong` 值。

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> 使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。 十进制文本没有前缀。

从 C# 7.0 开始，添加了一些功能以增强可读性：

- C# 7.0 允许将下划线字符 (`_`) 用作数字分隔符。
- C# 7.2 允许将 `_` 用作二进制或十六进制文本的数字分隔符，位于前缀之后。 十进制文本不能够有前导下划线。

下面是一些示例。

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

整数文本还可包含表示类型的后缀。 后缀 `UL` 或 `ul` 将数字文本明确标识为 `ulong` 值。 如果文本值超过 <xref:System.Int64.MaxValue?displayProperty=nameWithType>，则 `L` 后缀表示 `ulong`。 如果文本值超过 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>，则 `U` 或 `u` 后缀表示 `ulong`。 以下示例使用 `ul` 后缀来表示长整型：

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：

1. [int](int.md)
2. [uint](uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>编译器重载解析

此后缀常用于调用重载方法。 以下面使用 `ulong` 和 [int](int.md) 参数的重载方法为例：

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

在 `ulong` 参数后加上后缀可保证调用正确的类型，例如：

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a>转换

存在从 `ulong` 到 [float](float.md)、[double](double.md) 或 [decimal](decimal.md) 的预定义隐式转换。

不存在从 `ulong` 到任何整型的隐式转换。 例如，如果不使用显式强制转换，以下语句会生成编译错误：

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

存在从 [byte](byte.md)、[ushort](ushort.md)、[uint](uint.md) 或 [char](char.md) 到 `ulong` 的预定义隐式转换。

此外，不存在从浮点类型到 `ulong` 类型的隐式转换。 例如，除非使用显式强制转换，否则以下语句将生成编译器错误：

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](float.md) 和 [double](double.md)。

有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](implicit-numeric-conversions-table.md)。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[整型类型](~/_csharplang/spec/types.md#integral-types)。 该语言规范是 C# 语法和用法的权威资料。

## <a name="see-also"></a>请参阅

- <xref:System.UInt64>
- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [整型表](integral-types-table.md)
- [内置类型表](built-in-types-table.md)
- [隐式数值转换表](implicit-numeric-conversions-table.md)
- [显式数值转换表](explicit-numeric-conversions-table.md)
