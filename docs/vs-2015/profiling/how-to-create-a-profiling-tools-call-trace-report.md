---
title: 如何：创建分析工具调用跟踪报告 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b643e0bf356e7ffb3bf6030ff46cf38ad4a1d98a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483934"
---
# <a name="how-to-create-a-profiling-tools-call-trace-report"></a>如何：创建分析工具调用跟踪报告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 创建分析工具调用跟踪报告](https://docs.microsoft.com/visualstudio/profiling/how-to-create-a-profiling-tools-call-trace-report)。  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具的调用跟踪报告将列出应用程序函数每个入口点和出口点的计时信息，以及该函数对其他函数的每次调用的计时信息。 仅当使用检测方法收集时，调用跟踪报告才可用于分析数据。  
  
> [!NOTE]
>  不能在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中显示调用跟踪报告。 必须使用 VSPerfReport 命令行工具才能生成逗号分隔值 (.csv) 或 XML 文件。 有关此工具的详细信息，请参阅 [VSPerfReport](../profiling/vsperfreport.md)。  
  
### <a name="to-create-a-call-trace-report"></a>创建调用跟踪报告  
  
1.  打开“命令提示符”窗口。  
  
2.  在命令提示符处，键入下列命令：  
  
     *ToolsPath* **VSPerfReport** *VSPFile*  **/CallTrace [/Xml]**  
  
    |||  
    |-|-|  
    |*ToolsPath*|分析工具命令行工具的路径。 有关详细信息，请参阅[指定命令行工具的路径](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)。|  
    |*VSPFile*|分析数据（.vsp 或 .vsps）文件。 接受完整和部分路径。|  
    |Xml|生成 Xml 格式的报告。|  
  
## <a name="see-also"></a>请参阅  
 [如何：收集 Windows 事件跟踪 (ETW) 数据](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)   
 [分析工具 API](../profiling/profiling-tools-apis.md)


