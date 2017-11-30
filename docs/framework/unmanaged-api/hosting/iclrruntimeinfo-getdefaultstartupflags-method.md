---
title: "ICLRRuntimeInfo::GetDefaultStartupFlags 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73ad12e99a1ba98f6ea61775155cf1389118f754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="9bb84-102">ICLRRuntimeInfo::GetDefaultStartupFlags 方法</span><span class="sxs-lookup"><span data-stu-id="9bb84-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="9bb84-103">获取启动标志和将用于启动运行时的主机配置文件。</span><span class="sxs-lookup"><span data-stu-id="9bb84-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bb84-104">语法</span><span class="sxs-lookup"><span data-stu-id="9bb84-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bb84-105">参数</span><span class="sxs-lookup"><span data-stu-id="9bb84-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="9bb84-106">[out]指向当前设置的主机启动标志的指针。</span><span class="sxs-lookup"><span data-stu-id="9bb84-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="9bb84-107">[out]当前的主机配置文件的目录路径指向的指针。</span><span class="sxs-lookup"><span data-stu-id="9bb84-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="9bb84-108">[在中，out]在输入的大小`pwzHostConfigFile`，若要避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="9bb84-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="9bb84-109">如果`pwzHostConfigFile`是 null，该方法返回的所需的大小`pwzHostConfigFile`进行预分配。</span><span class="sxs-lookup"><span data-stu-id="9bb84-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bb84-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9bb84-110">Return Value</span></span>  
 <span data-ttu-id="9bb84-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="9bb84-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9bb84-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9bb84-112">HRESULT</span></span>|<span data-ttu-id="9bb84-113">描述</span><span class="sxs-lookup"><span data-stu-id="9bb84-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9bb84-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9bb84-114">S_OK</span></span>|<span data-ttu-id="9bb84-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="9bb84-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bb84-116">备注</span><span class="sxs-lookup"><span data-stu-id="9bb84-116">Remarks</span></span>  
 <span data-ttu-id="9bb84-117">此方法返回的默认值标志值 (`STARTUP_CONCURRENT_GC`和`NULL`)，或通过以前调用提供的值[iclrruntimeinfo:: Setdefaultstartupflags 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)，或按任何设置的值`CorBind*`如果它们被绑定到此运行时的方法。</span><span class="sxs-lookup"><span data-stu-id="9bb84-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bb84-118">要求</span><span class="sxs-lookup"><span data-stu-id="9bb84-118">Requirements</span></span>  
 <span data-ttu-id="9bb84-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9bb84-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bb84-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9bb84-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9bb84-121">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9bb84-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9bb84-122">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bb84-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb84-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bb84-123">See Also</span></span>  
 [<span data-ttu-id="9bb84-124">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="9bb84-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="9bb84-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="9bb84-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="9bb84-126">承载</span><span class="sxs-lookup"><span data-stu-id="9bb84-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)