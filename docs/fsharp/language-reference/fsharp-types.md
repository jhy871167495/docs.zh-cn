---
title: "F# 类型"
description: "了解有关在 F # 和 F # 类型如何命名和描述中使用的类型。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c7272a0d-5ab6-4eae-bceb-e49af498b917
ms.openlocfilehash: 9b7235637f301f91ae2cc8fbc59adc27cdfd5bd0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="f-types"></a><span data-ttu-id="31ce8-104">F# 类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-104">F# Types</span></span>

<span data-ttu-id="31ce8-105">本主题介绍在 F # 和 F # 类型如何命名和描述中使用的类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-105">This topic describes the types that are used in F# and how F# types are named and described.</span></span>


## <a name="summary-of-f-types"></a><span data-ttu-id="31ce8-106">F # 类型摘要</span><span class="sxs-lookup"><span data-stu-id="31ce8-106">Summary of F# Types</span></span>
<span data-ttu-id="31ce8-107">某些类型被视为*基元类型*，例如布尔类型`bool`和整型和浮点型的各种大小，包括字节和字符类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-107">Some types are considered *primitive types*, such as the Boolean type `bool` and integral and floating point types of various sizes, which include types for bytes and characters.</span></span> <span data-ttu-id="31ce8-108">中介绍了这些类型[基元类型](primitive-types.md)。</span><span class="sxs-lookup"><span data-stu-id="31ce8-108">These types are described in [Primitive Types](primitive-types.md).</span></span>

<span data-ttu-id="31ce8-109">其他内置于语言的类型包括元组、 列表、 数组、 序列、 记录，并可区分联合。</span><span class="sxs-lookup"><span data-stu-id="31ce8-109">Other types that are built into the language include tuples, lists, arrays, sequences, records, and discriminated unions.</span></span> <span data-ttu-id="31ce8-110">如果你有其他.NET 语言的经验，但学习 F #，你应阅读的主题有关上述每种类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-110">If you have experience with other .NET languages and are learning F#, you should read the topics for each of these types.</span></span> <span data-ttu-id="31ce8-111">有关这些类型的详细信息的链接都将纳入[相关主题](https://msdn.microsoft.com/library/#rel)本主题的部分。</span><span class="sxs-lookup"><span data-stu-id="31ce8-111">Links to more information about these types are included in the [Related Topics](https://msdn.microsoft.com/library/#rel) section of this topic.</span></span> <span data-ttu-id="31ce8-112">这些 F # 的特定类型支持功能的编程语言通用的编程样式。</span><span class="sxs-lookup"><span data-stu-id="31ce8-112">These F#-specific types support styles of programming that are common to functional programming languages.</span></span> <span data-ttu-id="31ce8-113">许多这些类型具有关联的 F # 库中的模块支持对这些类型的常见操作。</span><span class="sxs-lookup"><span data-stu-id="31ce8-113">Many of these types have associated modules in the F# library that support common operations on these types.</span></span>

<span data-ttu-id="31ce8-114">函数的类型包括信息的参数类型和返回类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-114">The type of a function includes information about the parameter types and return type.</span></span>

<span data-ttu-id="31ce8-115">.NET Framework 是对象类型、 接口类型、 委托类型和其他的源。</span><span class="sxs-lookup"><span data-stu-id="31ce8-115">The .NET Framework is the source of object types, interface types, delegate types, and others.</span></span> <span data-ttu-id="31ce8-116">就像任何其他.NET 语言中，你可以定义自己的对象类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-116">You can define your own object types just as you can in any other .NET language.</span></span>

<span data-ttu-id="31ce8-117">此外，F # 代码可以定义别名，分别名为*类型缩写，用*，都为类型的可选名称。</span><span class="sxs-lookup"><span data-stu-id="31ce8-117">Also, F# code can define aliases, which are named *type abbreviations*, that are alternative names for types.</span></span> <span data-ttu-id="31ce8-118">类型可能会在将来更改，并且你想要避免更改取决于类型的代码时，你可能使用类型缩写。</span><span class="sxs-lookup"><span data-stu-id="31ce8-118">You might use type abbreviations when the type might change in the future and you want to avoid changing the code that depends on the type.</span></span> <span data-ttu-id="31ce8-119">或者，可能会将类型缩写用作一种类型，可使代码易于阅读和理解的友好名称。</span><span class="sxs-lookup"><span data-stu-id="31ce8-119">Or, you might use a type abbreviation as a friendly name for a type that can make code easier to read and understand.</span></span>

<span data-ttu-id="31ce8-120">F # 提供有用的集合设计也考虑了函数编程记住的类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-120">F# provides useful collection types that are designed with functional programming in mind.</span></span> <span data-ttu-id="31ce8-121">使用这些集合类型，可帮助你编写是样式功能更强的代码。</span><span class="sxs-lookup"><span data-stu-id="31ce8-121">Using these collection types helps you write code that is more functional in style.</span></span> <span data-ttu-id="31ce8-122">有关详细信息，请参阅[F # 集合类型](fsharp-collection-types.md)。</span><span class="sxs-lookup"><span data-stu-id="31ce8-122">For more information, see [F# Collection Types](fsharp-collection-types.md).</span></span>


## <a name="syntax-for-types"></a><span data-ttu-id="31ce8-123">类型的语法</span><span class="sxs-lookup"><span data-stu-id="31ce8-123">Syntax for Types</span></span>
<span data-ttu-id="31ce8-124">在 F # 代码中，通常需要写出类型的名称。</span><span class="sxs-lookup"><span data-stu-id="31ce8-124">In F# code, you often have to write out the names of types.</span></span> <span data-ttu-id="31ce8-125">每个类型具有一个语法形式，并使用语法的窗体类型批注、 抽象方法声明、 委托声明、 签名和其他构造。</span><span class="sxs-lookup"><span data-stu-id="31ce8-125">Every type has a syntactic form, and you use these syntactic forms in type annotations, abstract method declarations, delegate declarations, signatures, and other constructs.</span></span> <span data-ttu-id="31ce8-126">每当声明解释器中的新程序构造，解释器将打印其类型的构造和语法的名称。</span><span class="sxs-lookup"><span data-stu-id="31ce8-126">Whenever you declare a new program construct in the interpreter, the interpreter prints the name of the construct and the syntax for its type.</span></span> <span data-ttu-id="31ce8-127">此语法可能只是一个标识符为用户定义的类型或内置标识符等的`int`或`string`，但对于更复杂类型，语法是更复杂。</span><span class="sxs-lookup"><span data-stu-id="31ce8-127">This syntax might be just an identifier for a user-defined type or a built-in identifier such as for `int` or `string`, but for more complex types, the syntax is more complex.</span></span>

<span data-ttu-id="31ce8-128">下表显示 F # 类型类型语法的各个方面。</span><span class="sxs-lookup"><span data-stu-id="31ce8-128">The following table shows aspects of the type syntax for F# types.</span></span>



|<span data-ttu-id="31ce8-129">类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-129">Type</span></span>|<span data-ttu-id="31ce8-130">类型语法</span><span class="sxs-lookup"><span data-stu-id="31ce8-130">Type syntax</span></span>|<span data-ttu-id="31ce8-131">示例</span><span class="sxs-lookup"><span data-stu-id="31ce8-131">Examples</span></span>|
|----|-----------|--------|
|<span data-ttu-id="31ce8-132">基元类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-132">primitive type</span></span>|<span data-ttu-id="31ce8-133">*类型名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-133">*type-name*</span></span>|`int`<br /><br />`float`<br /><br />`string`|
|<span data-ttu-id="31ce8-134">聚合类型 （类、 结构、 联合、 记录、 枚举和等等）</span><span class="sxs-lookup"><span data-stu-id="31ce8-134">aggregate type (class, structure, union, record, enum, and so on)</span></span>|<span data-ttu-id="31ce8-135">*类型名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-135">*type-name*</span></span>|`System.DateTime`<br /><br />`Color`|
|<span data-ttu-id="31ce8-136">类型缩写</span><span class="sxs-lookup"><span data-stu-id="31ce8-136">type abbreviation</span></span>|<span data-ttu-id="31ce8-137">*类型缩写名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-137">*type-abbreviation-name*</span></span>|`bigint`|
|<span data-ttu-id="31ce8-138">完全限定的类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-138">fully qualified type</span></span>|<span data-ttu-id="31ce8-139">*namespaces.type 名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-139">*namespaces.type-name*</span></span><br /><br /><span data-ttu-id="31ce8-140">或</span><span class="sxs-lookup"><span data-stu-id="31ce8-140">or</span></span><br /><br /><span data-ttu-id="31ce8-141">*modules.type 名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-141">*modules.type-name*</span></span><br /><br /><span data-ttu-id="31ce8-142">或</span><span class="sxs-lookup"><span data-stu-id="31ce8-142">or</span></span><br /><br /><span data-ttu-id="31ce8-143">*namespaces.modules.type 名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-143">*namespaces.modules.type-name*</span></span>|`System.IO.StreamWriter`|
|<span data-ttu-id="31ce8-144">array</span><span class="sxs-lookup"><span data-stu-id="31ce8-144">array</span></span>|<span data-ttu-id="31ce8-145">*类型名称*[] 或</span><span class="sxs-lookup"><span data-stu-id="31ce8-145">*type-name*[] or</span></span><br /><br /><span data-ttu-id="31ce8-146">*类型名称*数组</span><span class="sxs-lookup"><span data-stu-id="31ce8-146">*type-name* array</span></span>|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|<span data-ttu-id="31ce8-147">二维数组</span><span class="sxs-lookup"><span data-stu-id="31ce8-147">two-dimensional array</span></span>|<span data-ttu-id="31ce8-148">*类型名称*[、]</span><span class="sxs-lookup"><span data-stu-id="31ce8-148">*type-name*[,]</span></span>|`int[,]`<br /><br />`float[,]`|
|<span data-ttu-id="31ce8-149">三维数组</span><span class="sxs-lookup"><span data-stu-id="31ce8-149">three-dimensional array</span></span>|<span data-ttu-id="31ce8-150">*类型名称*[、]</span><span class="sxs-lookup"><span data-stu-id="31ce8-150">*type-name*[,,]</span></span>|`float[,,]`|
|<span data-ttu-id="31ce8-151">tuple</span><span class="sxs-lookup"><span data-stu-id="31ce8-151">tuple</span></span>|<span data-ttu-id="31ce8-152">*类型 name1* &#42;*类型 name2* ...</span><span class="sxs-lookup"><span data-stu-id="31ce8-152">*type-name1* &#42; *type-name2* ...</span></span>|<span data-ttu-id="31ce8-153">例如，`(1,'b',3)`具有类型`int * char * int`</span><span class="sxs-lookup"><span data-stu-id="31ce8-153">For example, `(1,'b',3)` has type `int * char * int`</span></span>|
|<span data-ttu-id="31ce8-154">Generic Type — 泛型类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-154">generic type</span></span>|<span data-ttu-id="31ce8-155">*类型参数**泛型类型名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-155">*type-parameter* *generic-type-name*</span></span><br /><br /><span data-ttu-id="31ce8-156">或</span><span class="sxs-lookup"><span data-stu-id="31ce8-156">or</span></span><br /><br /><span data-ttu-id="31ce8-157">*泛型类型名称*&lt;*类型参数列表*&gt;</span><span class="sxs-lookup"><span data-stu-id="31ce8-157">*generic-type-name*&lt;*type-parameter-list*&gt;</span></span>|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|<span data-ttu-id="31ce8-158">构造类型 （具有提供的特定类型自变量的泛型类型）</span><span class="sxs-lookup"><span data-stu-id="31ce8-158">constructed type (a generic type that has a specific type argument supplied)</span></span>|<span data-ttu-id="31ce8-159">*类型参数**泛型类型名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-159">*type-argument* *generic-type-name*</span></span><br /><br /><span data-ttu-id="31ce8-160">或</span><span class="sxs-lookup"><span data-stu-id="31ce8-160">or</span></span><br /><br /><span data-ttu-id="31ce8-161">*泛型类型名称*&lt;*类型自变量列表*&gt;</span><span class="sxs-lookup"><span data-stu-id="31ce8-161">*generic-type-name*&lt;*type-argument-list*&gt;</span></span>|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|<span data-ttu-id="31ce8-162">具有单个参数的函数类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-162">function type that has a single parameter</span></span>|<span data-ttu-id="31ce8-163">*参数 type1*  - &gt; *返回类型*</span><span class="sxs-lookup"><span data-stu-id="31ce8-163">*parameter-type1* -&gt; *return-type*</span></span>|<span data-ttu-id="31ce8-164">采用的函数`int`并返回`string`具有类型`int -> string`</span><span class="sxs-lookup"><span data-stu-id="31ce8-164">A function that takes an `int` and returns a `string` has type `int -> string`</span></span>|
|<span data-ttu-id="31ce8-165">具有多个参数的函数类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-165">function type that has multiple parameters</span></span>|<span data-ttu-id="31ce8-166">*参数 type1*  - &gt; *参数 type2*  - &gt; ...-&gt; *返回类型*</span><span class="sxs-lookup"><span data-stu-id="31ce8-166">*parameter-type1* -&gt; *parameter-type2* -&gt; ... -&gt; *return-type*</span></span>|<span data-ttu-id="31ce8-167">采用的函数`int`和`float`并返回`string`具有类型`int -> float -> string`</span><span class="sxs-lookup"><span data-stu-id="31ce8-167">A function that takes an `int` and a `float` and returns a `string` has type `int -> float -> string`</span></span>|
|<span data-ttu-id="31ce8-168">高阶函数作为参数</span><span class="sxs-lookup"><span data-stu-id="31ce8-168">higher order function as a parameter</span></span>|<span data-ttu-id="31ce8-169">(*函数类型*)</span><span class="sxs-lookup"><span data-stu-id="31ce8-169">(*function-type*)</span></span>|<span data-ttu-id="31ce8-170">`List.map`具有类型`('a -> 'b) -> 'a list -> 'b list`</span><span class="sxs-lookup"><span data-stu-id="31ce8-170">`List.map` has type `('a -> 'b) -> 'a list -> 'b list`</span></span>|
|<span data-ttu-id="31ce8-171">委托</span><span class="sxs-lookup"><span data-stu-id="31ce8-171">delegate</span></span>|<span data-ttu-id="31ce8-172">委托的*函数类型*</span><span class="sxs-lookup"><span data-stu-id="31ce8-172">delegate of *function-type*</span></span>|`delegate of unit -> int`|
|<span data-ttu-id="31ce8-173">可变类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-173">flexible type</span></span>|<span data-ttu-id="31ce8-174">#*类型名称*</span><span class="sxs-lookup"><span data-stu-id="31ce8-174">#*type-name*</span></span>|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a><span data-ttu-id="31ce8-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="31ce8-175">Related Topics</span></span>


|<span data-ttu-id="31ce8-176">主题</span><span class="sxs-lookup"><span data-stu-id="31ce8-176">Topic</span></span>|<span data-ttu-id="31ce8-177">描述</span><span class="sxs-lookup"><span data-stu-id="31ce8-177">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="31ce8-178">基元类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-178">Primitive Types</span></span>](primitive-types.md)|<span data-ttu-id="31ce8-179">介绍如整型、 布尔值类型和字符类型的内置简单类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-179">Describes built-in simple types such as integral types, the Boolean type, and character types.</span></span>|
|[<span data-ttu-id="31ce8-180">Unit 类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-180">Unit Type</span></span>](unit-type.md)|<span data-ttu-id="31ce8-181">描述`unit`类型，该类型具有一个值，并由 （）; 等效于`void`在 C# 和`Nothing`在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="31ce8-181">Describes the `unit` type, a type that has one value and that is indicated by (); equivalent to `void` in C# and `Nothing` in Visual Basic.</span></span>|
|[<span data-ttu-id="31ce8-182">元组</span><span class="sxs-lookup"><span data-stu-id="31ce8-182">Tuples</span></span>](tuples.md)|<span data-ttu-id="31ce8-183">描述的元组类型，在对、 三元组、 四重等分组的任何类型的关联值组成的类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-183">Describes the tuple type, a type that consists of associated values of any type grouped in pairs, triples, quadruples, and so on.</span></span>|
|[<span data-ttu-id="31ce8-184">选项</span><span class="sxs-lookup"><span data-stu-id="31ce8-184">Options</span></span>](options.md)|<span data-ttu-id="31ce8-185">描述的选项类型，可以具有一个值，或为空的类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-185">Describes the option type, a type that may either have a value or be empty.</span></span>|
|[<span data-ttu-id="31ce8-186">列表</span><span class="sxs-lookup"><span data-stu-id="31ce8-186">Lists</span></span>](lists.md)|<span data-ttu-id="31ce8-187">描述列表，它是有序的、 不可变序列元素的所有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-187">Describes lists, which are ordered, immutable series of elements all of the same type.</span></span>|
|[<span data-ttu-id="31ce8-188">阵列</span><span class="sxs-lookup"><span data-stu-id="31ce8-188">Arrays</span></span>](arrays.md)|<span data-ttu-id="31ce8-189">介绍数组，它有序集的相同类型的可变元素占用连续的内存块，并具有固定大小。</span><span class="sxs-lookup"><span data-stu-id="31ce8-189">Describes arrays, which are ordered sets of mutable elements of the same type that occupy a contiguous block of memory and are of fixed size.</span></span>|
|[<span data-ttu-id="31ce8-190">序列</span><span class="sxs-lookup"><span data-stu-id="31ce8-190">Sequences</span></span>](sequences.md)|<span data-ttu-id="31ce8-191">描述序列类型，它表示逻辑的一系列值;仅在必要时计算每个值。</span><span class="sxs-lookup"><span data-stu-id="31ce8-191">Describes the sequence type, which represents a logical series of values; individual values are computed only as necessary.</span></span>|
|[<span data-ttu-id="31ce8-192">记录</span><span class="sxs-lookup"><span data-stu-id="31ce8-192">Records</span></span>](records.md)|<span data-ttu-id="31ce8-193">描述记录类型，一个小型命名值的聚合。</span><span class="sxs-lookup"><span data-stu-id="31ce8-193">Describes the record type, a small aggregate of named values.</span></span>|
|[<span data-ttu-id="31ce8-194">可区分联合</span><span class="sxs-lookup"><span data-stu-id="31ce8-194">Discriminated Unions</span></span>](discriminated-unions.md)|<span data-ttu-id="31ce8-195">描述可区分联合类型，其值可以是任何一种可能的类型的一组的类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-195">Describes the discriminated union type, a type whose values can be any one of a set of possible types.</span></span>|
|[<span data-ttu-id="31ce8-196">函数</span><span class="sxs-lookup"><span data-stu-id="31ce8-196">Functions</span></span>](functions/index.md)|<span data-ttu-id="31ce8-197">说明函数值。</span><span class="sxs-lookup"><span data-stu-id="31ce8-197">Describes function values.</span></span>|
|[<span data-ttu-id="31ce8-198">类</span><span class="sxs-lookup"><span data-stu-id="31ce8-198">Classes</span></span>](classes.md)|<span data-ttu-id="31ce8-199">描述的类类型，对应于一个.NET 引用类型的对象类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-199">Describes the class type, an object type that corresponds to a .NET reference type.</span></span> <span data-ttu-id="31ce8-200">类类型可包含成员、 属性、 实现的接口和基类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-200">Class types can contain members, properties, implemented interfaces, and a base type.</span></span>|
|[<span data-ttu-id="31ce8-201">结构</span><span class="sxs-lookup"><span data-stu-id="31ce8-201">Structures</span></span>](structures.md)|<span data-ttu-id="31ce8-202">描述`struct`类型、 对应于一个.NET 值类型的对象类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-202">Describes the `struct` type, an object type that corresponds to a .NET value type.</span></span> <span data-ttu-id="31ce8-203">`struct`类型通常表示一个小型的数据聚合。</span><span class="sxs-lookup"><span data-stu-id="31ce8-203">The `struct` type usually represents a small aggregate of data.</span></span>|
|[<span data-ttu-id="31ce8-204">接口</span><span class="sxs-lookup"><span data-stu-id="31ce8-204">Interfaces</span></span>](interfaces.md)|<span data-ttu-id="31ce8-205">描述接口类型，它们是表示一组的成员提供某种功能，但不包含数据的类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-205">Describes interface types, which are types that represent a set of members that provide certain functionality but that contain no data.</span></span> <span data-ttu-id="31ce8-206">必须由要很有用的对象类型实现的接口类型。</span><span class="sxs-lookup"><span data-stu-id="31ce8-206">An interface type must be implemented by an object type to be useful.</span></span>|
|[<span data-ttu-id="31ce8-207">委托</span><span class="sxs-lookup"><span data-stu-id="31ce8-207">Delegates</span></span>](delegates.md)|<span data-ttu-id="31ce8-208">描述的委托类型，它表示为对象的函数。</span><span class="sxs-lookup"><span data-stu-id="31ce8-208">Describes the delegate type, which represents a function as an object.</span></span>|
|[<span data-ttu-id="31ce8-209">枚举</span><span class="sxs-lookup"><span data-stu-id="31ce8-209">Enumerations</span></span>](enumerations.md)|<span data-ttu-id="31ce8-210">介绍枚举类型，其值所属的一组命名的值。</span><span class="sxs-lookup"><span data-stu-id="31ce8-210">Describes enumeration types, whose values belong to a set of named values.</span></span>|
|[<span data-ttu-id="31ce8-211">特性</span><span class="sxs-lookup"><span data-stu-id="31ce8-211">Attributes</span></span>](attributes.md)|<span data-ttu-id="31ce8-212">描述了属性，用于指定另一个类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="31ce8-212">Describes attributes, which are used to specify metadata for another type.</span></span>|
|[<span data-ttu-id="31ce8-213">异常类型</span><span class="sxs-lookup"><span data-stu-id="31ce8-213">Exception Types</span></span>](exception-handling/exception-types.md)|<span data-ttu-id="31ce8-214">描述指定错误的信息的异常。</span><span class="sxs-lookup"><span data-stu-id="31ce8-214">Describes exceptions, which specify error information.</span></span>|