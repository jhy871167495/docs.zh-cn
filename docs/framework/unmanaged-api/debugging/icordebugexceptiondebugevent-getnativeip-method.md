---
title: "ICorDebugExceptionDebugEvent::GetNativeIP 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 616f0a9787220aba0cc4d460c80b856076e1e437
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="dbfc4-102">ICorDebugExceptionDebugEvent::GetNativeIP 方法</span><span class="sxs-lookup"><span data-stu-id="dbfc4-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="dbfc4-103">获取此异常调试事件的本机指令指针。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbfc4-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbfc4-104">Syntax</span></span>  
  
```  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbfc4-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbfc4-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="dbfc4-106">[out] 指向此异常调试事件的指令指针的指针。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="dbfc4-107">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbfc4-108">备注</span><span class="sxs-lookup"><span data-stu-id="dbfc4-108">Remarks</span></span>  
 <span data-ttu-id="dbfc4-109">此指令指针的含义取决于事件类型，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="dbfc4-110">事件类型</span><span class="sxs-lookup"><span data-stu-id="dbfc4-110">Event type</span></span>|<span data-ttu-id="dbfc4-111">`pStackPointer` 值的含义</span><span class="sxs-lookup"><span data-stu-id="dbfc4-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="dbfc4-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="dbfc4-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="dbfc4-113">出错指令的地址。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="dbfc4-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="dbfc4-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="dbfc4-115">在框架中的代码地址由[GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)如果未不引发任何异常将继续执行的方法。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-115">The code address in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="dbfc4-116">此异常可能会，也可能不会导致在此帧中执行的不同代码（例如，`try/catch/finally` 子句的 catch 块）。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="dbfc4-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="dbfc4-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="dbfc4-118">代码地址`catch`通过指示的帧中，将开始处理程序执行[GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="dbfc4-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="dbfc4-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="dbfc4-120">`pIP` 为 0。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="dbfc4-121">事件类型是可从[icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbfc4-122">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbfc4-123">要求</span><span class="sxs-lookup"><span data-stu-id="dbfc4-123">Requirements</span></span>  
 <span data-ttu-id="dbfc4-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbfc4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbfc4-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbfc4-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbfc4-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbfc4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbfc4-127">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbfc4-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbfc4-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbfc4-128">See Also</span></span>  
 [<span data-ttu-id="dbfc4-129">ICorDebugExceptionDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="dbfc4-129">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="dbfc4-130">调试接口</span><span class="sxs-lookup"><span data-stu-id="dbfc4-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)