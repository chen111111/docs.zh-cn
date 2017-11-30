---
title: "ICorDebugFrameEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrameEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2139661621d7ebe2bf20e96b400096393964b89
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="b918b-102">ICorDebugFrameEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="b918b-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="b918b-103">获取指定的数量的 ICorDebugFrame 实例，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="b918b-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b918b-104">语法</span><span class="sxs-lookup"><span data-stu-id="b918b-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b918b-105">参数</span><span class="sxs-lookup"><span data-stu-id="b918b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b918b-106">[in]数`ICorDebugFrame`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="b918b-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="b918b-107">[out]一个指针，其中每个指向数组`ICorDebugFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="b918b-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b918b-108">[out]指向数`ICorDebugFrame`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="b918b-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="b918b-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="b918b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b918b-110">要求</span><span class="sxs-lookup"><span data-stu-id="b918b-110">Requirements</span></span>  
 <span data-ttu-id="b918b-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b918b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b918b-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b918b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b918b-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b918b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b918b-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b918b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>