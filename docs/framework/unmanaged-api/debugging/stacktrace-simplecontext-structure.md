---
title: StackTrace_SimpleContext 结构
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf2ba752ace49ae288857dc22819a8e7e429a34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424048"
---
# <a name="stacktracesimplecontext-structure"></a>StackTrace_SimpleContext 结构
提供可用于代替完整的 `CONTEXT` 结构的简单上下文。  
  
## <a name="syntax"></a>语法  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`StackOffset`|堆栈指针或在 x86 上的输入堆栈指针 (ESP) 平台。|  
|`FrameOffset`|帧偏移量或在 x86 上的 EBP 寄存器平台。|  
|`InstructionOffset`|指令指针或输入指令指针 (EIP) 在 x86 平台。|  
  
## <a name="remarks"></a>备注  
 因为堆栈跟踪函数通常需要返回地址、 帧偏移量和堆栈地址，你可以选择使用`SimpleContext`而不是较大的结构`CONTEXT`结构。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** SOS_Stacktrace.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
