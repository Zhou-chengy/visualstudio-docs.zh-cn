---
title: 将许可证分配给 Visual Studio 订阅的用户组 | Microsoft Docs
author: evanwindom
ms.author: v-evwin
manager: cabuschl
ms.assetid: c2853359-18fd-4be4-97a6-02230c862f92
ms.date: 10/22/2020
ms.topic: how-to
description: 了解管理员如何使用批量添加功能或 Microsoft Azure Active Directory 组将许可证分配给多个订阅者
ms.openlocfilehash: 6cb3613d76faca2adc9c6e946f6a8ec2c73770f1
ms.sourcegitcommit: a731a9454f1fa6bd9a18746d8d62fe2e85e5ddb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2020
ms.locfileid: "92467539"
---
# <a name="assign-subscriptions-to-multiple-users"></a>将订阅分配给多个用户
你可以在订阅管理门户中一次添加一个多个用户，也可以采用大用户组形式添加。  要添加各个用户，请参阅[添加单个用户](assign-license.md)。

若要添加大批量用户，可以使用批量添加功能，或者，如果你的组织使用的是 Microsoft Azure Active Directory (Azure AD)，则可以使用 Azure AD 组。 本文将介绍这两种方法的具体过程。  观看此视频或继续阅读，了解有关批量添加功能的详细信息。 

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vxNq]

## <a name="use-bulk-add-to-assign-subscriptions"></a>使用批量添加功能分配订阅
1. 登录 Visual Studio 订阅管理门户，网址： <https://manage.visualstudio.com> 。

1. 若要一次添加多个订阅者，请导航到“管理订阅者”选项卡。选择“添加”选项卡，然后选择下拉列表中的“批量添加”。  

1. 批量添加功能会使用 Microsoft Excel 模板上传订阅者信息。 在“上传多个订阅者”对话框中，选择“下载”下载模板。
   > [!div class="mx-imgBorder"]
   > ![下载 Excel 模板以上传多个订阅者](media/download-template-upload-subscribers.png "下载空白 Excel 模板，开始批量分配过程。")
   >
   > [!NOTE]
   > 请务必下载本模板的最新版本。 如果使用旧版本，批量上传可能会失败。

1. 在 Excel 电子表格的字段中，填写想要为其分配订阅的个人的信息。 （“引用”是可选字段。）完成后将文件保存在本地。

    > [!NOTE]
    > 管理员可以使用模板中的一个字段启用或禁用订阅者下载软件的功能。  如果禁用下载，则还会禁用他们对产品密钥的访问权限。

   为顺利地完成上传，请查看以下最佳做法：

    - 确保所有表单域均不含逗号。
    - 删除表单域前后的空格。
    - 确保用户名在名字和姓氏两部分之间不含额外空格（例如，用户姓名为两部分的“Maggie May”，则应输成“MaggieMay”，因为系统不会删减额外空格）。
    - 确保填写所有必填字段。 
    - 检查“错误消息”列。  如果列出了任何错误，请先修复这些错误，然后再尝试上传文件。 

1. 返回到 Visual Studio 订阅管理门户。 在“上传多个订阅者”对话框中，选择“浏览” 。
   > [!div class="mx-imgBorder"]
   > ![浏览到之前保存的模板以上传多个订阅者](media/bulk-add-browse-saved-template.png "你可以浏览到文件位置，或将其拖放到此对话框中。")

1. 导航到之前保存的 Excel 文件，然后选择“确定”。
   > [!div class="mx-imgBorder"]
   > ![上传 Excel 模板以上传多个订阅者](media/bulk-upload-subscribers.png "此处将显示包含你的数据的模板。选择“确定”开始上传。")

    将显示上传进度对话框。

    如果模板中存在错误，则无法上传。系统会显示该错误，你可以更正模板，然后再次尝试批量上传。
   > [!div class="mx-imgBorder"]
   > ![如果上传多个订阅者失败，将显示错误消息](_img/assign-license-bulk/bulk-add-upload-failure.png "如果上传的文件包含错误，则将显示此消息。解决错误，然后再次执行批量添加过程。")

   如果失败，请按照以下步骤操作：
   1. 打开你创建的 Excel 文件、更正问题，然后保存文件。
   0. 返回到管理门户并关闭错误消息。
   0. 选择“添加”。
   0. 选择“批量添加”。
   0. 由于你已保存 Excel 文件，因此无需下载模板。  选择“浏览”，找到刚才保存的文件，然后选择“打开” 。
   0. 选择“确定” 。


    上传成功后，系统会显示订阅者列表和一条确认消息。
   > [!div class="mx-imgBorder"]
   > ![如果上传多个订阅者成功，将显示确认消息](_img/assign-license-bulk/bulk-add-upload-success.png "上传成功完成后，你将收到一条确认消息。")

## <a name="use-azure-active-directory-groups-to-assign-subscriptions"></a>使用 Azure Active Directory 组分配订阅 
使用此功能可以轻松地控制订阅分配。 可以在订阅管理门户中添加 Azure Active Directory 安全组，这将确保为组中的每个成员都分配一个订阅。 为了便于操作，当有成员离开你的组织并且从 Azure Active Directory 中删除时，他们对订阅的访问权限也会相应地删除。 


> [!IMPORTANT]
>
> 以下限制适用于使用 Azure AD 组添加订阅者的情况：
> - 在最初将组添加到管理门户时，管理员必须是 AAD 租户的成员。  添加组后，对组成员身份进行更改不需要管理员参与。 
> - 组必须至少包含一个成员。  不支持空组。
> - 组中的用户数必须少于 1,000 个。 
> - 所有用户都必须处于组的顶层。  不支持嵌套组。
> - 仅支持受信任协议。
> - 组的所有成员都必须具有与其 Azure AD 帐户关联的电子邮件地址。
> - 对于使用 Azure AD 组添加的订阅，不支持对通知使用不同的电子邮件地址。  

观看此视频或继续阅读，了解有关使用 Azure Active Directory 组功能添加订阅者的详细信息。 
<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4rvvW]

1. 登录 Visual Studio 订阅管理门户，网址：[https://manage.visualstudio.com](https://manage.visualstudio.com)。

2. 若要一次添加多个订阅者，请导航到“管理订阅者”选项卡。

3. 选择“添加”选项卡，然后选择下拉列表中的“Azure Active Directory 组”。  

   > [!div class="mx-imgBorder"]
   > ![使用 Azure AD 选择批量添加](_img/assign-license-bulk/bulk-add-aad.png "选择“使用 Azure AD 功能批量添加”以从 Azure Active Directory 组拉取订阅者。")

4. 开始输入要添加到表单域的 Azure AD 组的名称。 这将搜索组织内可用的 Azure AD 组。 

5. 选择组后，该字段将自动填充组名。 在添加用户之前，可以选择查看该组中的用户。 接下来，可以选择组的订阅级别、下载权限和通信首选项。 可以根据需要在引用字段中添加详细信息。 

   > [!div class="mx-imgBorder"]
   > ![选择 Azure AD 组](_img/assign-license-bulk/bulk-add-aad-details.png "选择 Azure AD 组的名称以添加该组中的订阅者。")

6. 选择“添加”，然后选择“确认” 。 

7. 若要查看添加的组，请滚动到用户列表的底部。  

8. 选择“查看订阅者”以显示组的成员。 可以查看有关组中订阅者的详细信息，但不能对订阅者或对分配给他们的订阅进行任何编辑。    

> [!NOTE]
> 如果已单独为用户（这些用户随后将作为 Azure AD 组的一部分进行添加）分配了订阅，则这些用户将添加到组中，并且不再单独列出。 但是，如果单个订阅对应于不同的订阅级别，则他们将拥有两个订阅。  示例：如果用户有一个单独的 Visual Studio Professional 订阅，并且他们是组的成员，该组已分配有 Visual Studio Enterprise 订阅，则他们将同时拥有这两个订阅。  
>
> 如果从已分配有订阅的 Azure Active Directory 组中删除订阅者，则最长可能需要 24 小时才能在管理门户中反映更新。 


## <a name="frequently-asked-questions"></a>常见问题
### <a name="q-can-i-choose-multiple-subscription-levels-to-be-assigned-within-an-azure-ad-group"></a>问：能否选择要在 Azure AD 组内分配的多个订阅级别？ 
答：不能。组中的每个人都会收到相同的订阅。 

### <a name="q-can-i-edit-subscriber-details-of-individuals-added-in-an-azure-ad-group"></a>问：能否编辑 Azure AD 组中添加的成员的订阅者详细信息？  
答：不能。要修改单个订阅者的信息，需要将其从 Azure AD 安全组中删除，并分别为其分配订阅。  

### <a name="q-i-added-someone-to-my-azure-ad-security-group-but-i-dont-see-them-added-in-the-subscriptions-administration-portal-and-they-dont-have-a-subscription-why-not"></a>问：我已将某人添加到我的 Azure AD 安全组，但我在订阅管理门户中看不到该用户，而且该用户没有订阅。 为什么看不到？  
答：根据组织对 Azure AD 的配置，在看到已添加的用户之前，可能存在延迟（最多可能有 24 小时）。 如果延迟超过 24 小时，请[联系支持人员](https://visualstudio.microsoft.com/support/support-overview-vs)。  

## <a name="see-also"></a>请参阅
- [Visual Studio 文档](/visualstudio/)
- [Azure DevOps 文档](/azure/devops/)
- [Azure 文档](/azure/)
- [Microsoft 365 文档](/microsoft-365/)

## <a name="next-steps"></a>后续步骤
- 只有一两个订阅者要添加？  请查阅[添加单个用户](assign-license.md)
- 需要帮助？ 联系 [Visual Studio 管理和订阅支持](https://visualstudio.microsoft.com/support/support-overview-vs)。