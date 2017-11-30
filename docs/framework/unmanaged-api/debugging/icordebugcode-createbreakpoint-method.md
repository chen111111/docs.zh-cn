---
title: "ICorDebugCode::CreateBreakpoint 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 214d032129613230b8c55cdd286ea637227a626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="bcaf5-102">ICorDebugCode::CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="bcaf5-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="bcaf5-103">在此代码段中指定的偏移量处创建断点。</span><span class="sxs-lookup"><span data-stu-id="bcaf5-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcaf5-104">语法</span><span class="sxs-lookup"><span data-stu-id="bcaf5-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcaf5-105">参数</span><span class="sxs-lookup"><span data-stu-id="bcaf5-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="bcaf5-106">[in]若要创建断点送的偏移量。</span><span class="sxs-lookup"><span data-stu-id="bcaf5-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="bcaf5-107">[out]指向一个表示断点"ICorDebugFunctionBreakpoint"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="bcaf5-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcaf5-108">备注</span><span class="sxs-lookup"><span data-stu-id="bcaf5-108">Remarks</span></span>  
 <span data-ttu-id="bcaf5-109">断点处于活动状态之前，它必须添加到此进程对象中。</span><span class="sxs-lookup"><span data-stu-id="bcaf5-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="bcaf5-110">如果此代码为 Microsoft 中间语言 (MSIL) 代码，并且没有在实时 (JIT)-将在 JIT 编译代码以及应用已编译的本机版本的代码，该断点。</span><span class="sxs-lookup"><span data-stu-id="bcaf5-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="bcaf5-111">（相同如果为 true 的代码都是 JIT 编译更高版本。）</span><span class="sxs-lookup"><span data-stu-id="bcaf5-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcaf5-112">要求</span><span class="sxs-lookup"><span data-stu-id="bcaf5-112">Requirements</span></span>  
 <span data-ttu-id="bcaf5-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bcaf5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcaf5-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcaf5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcaf5-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcaf5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcaf5-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcaf5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcaf5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcaf5-117">See Also</span></span>  
 