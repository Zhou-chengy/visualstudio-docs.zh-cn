---
title: XML 文档验证 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 990aceabc2fa5fa38ea6902eec9de39da7cb9eff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480772"
---
# <a name="xml-document-validation"></a>XML 文档验证
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[XML 文档验证](https://docs.microsoft.com/visualstudio/xml-tools/xml-document-validation)。  
  
  
“XML 编辑器”检查 XML 1.0 语法，还会在您键入时执行数据验证。 编辑器可以使用文档类型定义 (DTD) 或架构进行验证。 红色的波浪形下划线突出显示任何 XML 1.0 格式正确的错误。 蓝色的波浪形下划线根据 DTD 或架构验证显示语义错误。 每个错误在错误列表中有关联的条目。 将鼠标光标暂时停留在波浪形下划线上，也可以查看错误消息。  
  
 将已编译架构的 `targetNamespace` 与元素的 xmlns 声明进行匹配，可以找到验证中使用的架构。 已编译架构从下列位置之一加载（按优先级顺序列出）：  
  
-   在指定的文件名称**架构**字段的文档属性窗口。  
  
-   内联架构或 DTD。  
  
-   外部 DTD 或 `xsd:schemaLocation` 和 `xsd:noNamespaceSchemaLocation` 属性  
  
-   “x-schema”XDR 架构命名空间 URI。  
  
 如果架构具有非空目标命名空间，在下列附加位置也可以找到架构：  
  
-   包含架构的另一个编辑器窗口。  
  
-   当前解决方案中的架构。  
  
-   架构缓存目录中的架构。  
  
## <a name="xslt-files"></a>XSLT 文件  
 在编辑 XSLT 文件时，使用架构缓存中的 xslt.xsd 文件进行验证。 验证错误以蓝色的波浪形下划线显示。 XSLT 编译器中的错误显示为红色的波浪形下划线。  
  
## <a name="xml-schema-xsd-files"></a>XML 架构 (XSD) 文件  
 在编辑 XML 架构文件时，使用架构缓存中的 xsdschema.xsd 文件进行验证。 验证错误以蓝色的波浪形下划线显示。 任何编译错误也会显示为红色的波浪形下划线。  
  
## <a name="see-also"></a>请参阅  
 [XML 编辑器](../xml-tools/xml-editor.md)


