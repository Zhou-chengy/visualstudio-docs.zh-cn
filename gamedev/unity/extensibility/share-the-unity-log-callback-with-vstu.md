---
title: 与 VSTU 共享 Unity 日志回叫 | Microsoft Docs
description: 与在 Visual Studio Tools for Unity (VSTU) 中注册的回调共享 Unity 日志回调，以将其控制台流式传输到 Visual Studio。
ms.custom: ''
ms.date: 07/26/2018
ms.technology: vs-unity-tools
ms.prod: visual-studio-dev16
ms.topic: how-to
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
author: therealjohn
ms.author: johmil
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: a1f4e7be068a152fc76c95160bdc7930f61e1f74
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "94341155"
---
# <a name="share-the-unity-log-callback-with-vstu"></a>与 VSTU 共享 Unity 日志回调
Visual Studio Tools for Unity 对 Unity 注册了一个日志回调，能够将其控制台流式传输到 Visual Studio。 如果编辑器脚本也对 Unity 注册了一个日志回调，则 VSTU 回调可能会妨碍你的回调。 若要防止这种可能性，则使用 `VisualStudioIntegration.LogCallback` 事件与 VSTU 协作。

## <a name="demonstrates"></a>演示
 如何共享由 Visual Studio Tools for Unity 创建的 Unity 日志回调。

## <a name="example"></a>示例

```csharp
#if ENABLE_VSTU
using System;

using UnityEngine;
using UnityEditor;

using SyntaxTree.VisualStudio.Unity.Bridge;

[InitializeOnLoad]
public class LogCallbackHook
{
    static LogCallbackHook()
    {
        VisualStudioIntegration.LogCallback += (string condition, string trace, LogType type) =>
        {
            // place code that implements your log callback here
        };
    }
}
#endif
```

## <a name="see-also"></a>另请参阅
 [示例：项目文件生成](./customize-project-files-created-by-vstu.md)
