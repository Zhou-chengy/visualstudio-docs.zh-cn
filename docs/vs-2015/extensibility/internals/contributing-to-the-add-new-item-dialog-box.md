---
title: 参与到添加新建项对话框 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add New Item dialog box, contributing to
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f5fcbac8b9e26bcca5a588846c14972156761d5b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468517"
---
# <a name="contributing-to-the-add-new-item-dialog-box"></a>构成“添加新项”对话框
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[到添加新项对话框中参与](https://docs.microsoft.com/visualstudio/extensibility/internals/contributing-to-the-add-new-item-dialog-box)。  
  
项目子类型可以提供完整的项的新目录**添加新项**对话框中的注册**添加项**下的模板`Projects`注册表子项。  
  
## <a name="registering-add-new-item-templates"></a>注册添加新项模板  
 本部分位于**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects**注册表中。 下面的注册表项假定[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]项目假设项目子类型进行聚合。 为项[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]下面列出了项目。  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}]  
@="#2143"  
"DefaultProjectExtension"="vbproj"  
"PossibleProjectExtensions"="vbproj;vbp"  
"ProjectTemplatesDir"="visualStudioInstallPath\\Vb\\.\\VBProjects"  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}\AddItemTemplates\TemplateDirs\{12345678-1234-1234-1122334455667788}\/1]  
@="#100"  
"TemplatesDir"="projectSubTypeTemplatesDir\\VBProjectItems"  
```  
  
 `AddItemTemplates\TemplateDirs`子项包含注册表项，项所做中可用的目录的路径**添加新项**放置对话框。  
  
 环境会自动加载的所有`AddItemTemplates`下的数据`Projects`注册表子项。 这可以包括基础项目实现的数据以及特定项目子类型类型数据。 每个项目子类型由项目类型`GUID`。 项目子类型可以指定的设置备用`Add Item`模板应该用于通过支持的特定风格的项目实例`VSHPROPID_ AddItemTemplatesGuid`来自枚举<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>中<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>实现，以返回 GUID项目子类型的值。 如果`VSHPROPID_AddItemTemplatesGuid`未指定属性，使用 GUID 的基础项目。  
  
 您可以筛选中的项**添加新项**对话框中，通过实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg>项目子类型聚合器对象上的接口。 例如，通过聚合来实现数据库项目的项目子类型才能[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]项目中，可以筛选[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]中的特定于项**添加新项**通过实现筛选，然后在对话框打开，可以添加通过支持数据库项目的特定项`VSHPROPID_ AddItemTemplatesGuid`在<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>。 有关详细信息筛选和添加的项**添加新项**对话框中，请参阅[将项添加到添加新项对话框](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [通常用于扩展项目的对象的 CATID](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)
