---
title: "ICorDebugILFrame::EnumerateLocalVariables 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.EnumerateLocalVariables
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fb4e6bead1bb4933f8f9af4ffb1bfb9157a028c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="e9dba-102">ICorDebugILFrame::EnumerateLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="e9dba-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="e9dba-103">此帧中获取的本地变量的枚举数。</span><span class="sxs-lookup"><span data-stu-id="e9dba-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9dba-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9dba-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9dba-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9dba-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="e9dba-106">[out]指向的地址是此帧中局部变量的枚举器的 ICorDebugValueEnum 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e9dba-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9dba-107">备注</span><span class="sxs-lookup"><span data-stu-id="e9dba-107">Remarks</span></span>  
 <span data-ttu-id="e9dba-108">`EnumerateLocalVariables`获取可以列出此 ICorDebugILFrame 对象表示的调用帧中可用的本地变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="e9dba-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="e9dba-109">列表可能不包括所有的局部变量中正在运行的函数，因为其中一些可能未处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="e9dba-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9dba-110">要求</span><span class="sxs-lookup"><span data-stu-id="e9dba-110">Requirements</span></span>  
 <span data-ttu-id="e9dba-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9dba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9dba-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9dba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9dba-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9dba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9dba-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9dba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>