---
title: 将 ASP.NET Core Linux Docker 容器部署到 Docker Hub | Microsoft Docs
description: 了解如何使用 Visual Studio 容器工具将 ASP.NET Core Web 应用部署到 Docker Hub
author: ghogen
manager: jillfra
ms.technology: vs-azure
ms.devlang: dotnet
ms.topic: article
ms.date: 07/23/2019
ms.author: ghogen
ms.openlocfilehash: b033825bbe8facbeae3dcdee6a5b563461921522
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73188744"
---
# <a name="deploy-to-docker-hub"></a>部署到 Docker Hub

Docker Hub 为映像存储库提供了一种便利的托管服务。 可以轻松地以手动方式从 Visual Studio 部署到 Docker Hub。

## <a name="create-a-docker-account-and-docker-hub-repository"></a>创建 Docker 帐户和 Docker Hub 存储库

如果没有 Docker 帐户，请[注册](https://hub.docker.com/signup) Docker 帐户。

如果没有 Docker Hub 存储库，请在 [Docker Hub](https://hub.docker.com/) 创建一个存储库。

## <a name="publish-the-image-for-a-single-project-to-docker-hub"></a>将单个项目的映像发布到 Docker Hub

1. 右键单击项目节点，然后选择“发布...”  。显示部署选项的屏幕随即出现。

   ![](media/deploy-docker-hub/container-tools-docker-hub-deploy.png)

1. 在“选取发布目标”下，选择“容器注册表”，然后选择“Docker Hub”    。 系统随即显示“Docker Hub”对话框  。

   ![](media/deploy-docker-hub/container-tools-docker-hub-credentials.png)

1. 如果要连接到自己的存储库（不属于组织），请选中“发布到个人存储库”复选框  。 如果存储库归组织所有，请清除该复选框，然后输入组织名称。 输入具有要连接到的存储库的访问权限的 Docker 帐户的 Docker 用户名和密码，然后选择“保存”  。  

   Visual Studio 尝试将映像部署到 Docker Hub。  如果成功，系统将显示“发布”屏幕，其中包含存储库映像的 URL、映像标记、存储库和生成配置**（例如，“版本”）   。

   ![](media/deploy-docker-hub/container-tools-docker-hub-finished.png)

1. 单击此页上的“发布”按钮即可随时更新该映像  。  也可以通过使用 URL 下面的链接来修改或删除配置文件。

## <a name="next-steps"></a>后续步骤

请按照[部署到 Azure 容器注册表](hosting-web-apps-in-docker.md)中的步骤发布到 [Azure 容器注册表](/azure/container-registry/)。

使用 [Azure Pipelines](/azure/devops/pipelines/?view=azure-devops) 设置持续集成和持续交付 (CI/CD)。

## <a name="see-also"></a>请参阅

[部署到 Azure 应用服务](deploy-app-service.md)
[Visual Studio 容器工具](/visualstudio/containers/)。