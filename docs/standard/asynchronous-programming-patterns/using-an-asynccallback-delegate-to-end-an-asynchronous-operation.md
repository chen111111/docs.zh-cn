---
title: 使用 AsyncCallback 委托结束异步操作
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 856273c9592aa32feb3e8cc66c850cb34ad0812f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44181467"
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>使用 AsyncCallback 委托结束异步操作
如果应用可以在等待异步操作结果期间继续执行其他工作，不得阻止应用一直到操作完成。 请使用下列方法之一，在应用等待异步操作完成期间继续执行指令：  
  
-   使用 <xref:System.AsyncCallback> 委托，在单独的线程中处理异步操作结果。 本主题介绍的就是这种方法。  
  
-   使用异步操作的 BeginOperationName****** 方法返回的 <xref:System.IAsyncResult> 的 <xref:System.IAsyncResult.IsCompleted%2A> 属性，确定操作是否已完成。 有关展示这种方法的示例，请参阅[轮询异步操作状态](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例展示了如何使用 <xref:System.Net.Dns> 类中的异步方法，检索用户指定计算机的域名系统 (DNS) 信息。 此示例创建引用 `ProcessDnsInformation` 方法的 <xref:System.AsyncCallback> 委托。 每次异步请求获取 DNS 信息，都会调用一次此方法。  
  
 请注意，将用户指定主机传递给 <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> 参数。 有关展示了如何定义和使用更复杂状态对象的示例，请参阅[使用 AsyncCallback 委托和状态对象](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)。  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>请参阅

- [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
- [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
- [使用 IAsyncResult 调用异步方法](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
- [使用 AsyncCallback 委托和状态对象](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
