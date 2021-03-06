---
title: 文本格式指南
description: 了解何时在 docs.microsoft.com 网站上发布的文章中使用粗体、斜体、代码和其他文本样式。
author: tdykstra
ms.author: tdykstra
ms.date: 01/30/2020
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 7b6927918c81fdc41e3c3887f94339b225e2a6e6
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336499"
---
# <a name="text-formatting-guidelines"></a>文本格式指南

如果文本元素的粗体、斜体和代码样式的使用恰当、一致，可提高可读性，并有助于避免误解。

## <a name="bold"></a>粗体

对 UI 元素（例如菜单选项、对话框名称和输入字段名称）使用粗体。

### <a name="examples"></a>示例

* 正确示例  ：在**解决方案资源管理器**中，右键单击项目节点，然后选择**添加 > 新建项**。
* 错误示例  ：在解决方案资源管理器中，右键单击项目节点，然后选择添加 > 新建项。
* 错误示例  ：在*解决方案资源管理器*中，右键单击项目节点，然后选择*添加 > 新建项*。

## <a name="italics"></a>斜体

将斜体用于以下内容：

* 带有定义或解释的新术语简介。
* 文件名称、文件夹名称、路径。
* 用户输入。

### <a name="examples"></a>示例

* 正确示例  ：在应用服务中，应用在*应用服务计划*中运行。 应用服务计划定义要运行 Web 应用的一组计算资源。
* 错误示例  ：在应用服务中，应用在“应用服务计划”中运行。 应用服务计划定义要运行 Web 应用的一组计算资源。
* 正确示例  ：将 *HttpTriggerCSharp.cs* 中的代码替换为以下代码。
* 错误示例  ：将 `HttpTriggerCSharp.cs` 中的代码替换为以下代码。
* 正确示例  ：输入 *ContosoUniversity* 作为**名称**，然后选择“**添加**”。
* 错误示例  ：输入“ContosoUniversity”作为**名称**，然后选择“**添加**”。

## <a name="code-style"></a>代码样式

将代码样式用于以下内容：

* 代码元素，如方法名称、属性名称和语言关键字。
* SQL 命令
* NuGet 包名称
* 命令行命令
* 数据库表和列名称
* 不应本地化的资源名称（例如虚拟机名称）
* 希望不可点击的 URL

**为什么？** 旧版样式指南指定对许多此类文本元素使用粗体。 但是，大多数文章都已本地化，代码样式会告诉翻译人员将这部分文本保留不译。

代码样式可以为内联（包括在 \` 中）或跨多行的隔离代码块（包括在 \`\`\` 中）   。 请将较长的代码片段和路径放在隔离代码块中。

### <a name="examples-using-inline-styles"></a>使用内联样式的示例

* 正确示例  ：默认情况下，实体框架将名为 `Id` 或 `ClassnameID` 的属性解释为主键。
* 错误示例  ：默认情况下，实体框架将名为 *Id* 或 *ClassnameID* 的属性解释为主键。
* 正确示例  ：`Microsoft.EntityFrameworkCore` 包为 EF Core 提供运行时支持。
* 错误示例  ：*Microsoft.EntityFrameworkCore* 包为 EF Core 提供运行时支持。

### <a name="examples-of-fenced-code-blocks"></a>隔离代码块示例

* 正确示例  ：没有命令通过只更改 `IQueryable` 的语句发送到数据库，例如以下代码：

  ```markdown
      ```csharp
      var students = context.Students.Where(s => s.LastName == "Davolio")
      ```
  ```

* 错误示例  ：没有命令通过只更改 **IQueryable** 的语句（例如 **var students = context.Students.Where(s => s.LastName == "Davolio")** ）发送到数据库。

* 正确示例  ：例如，若要在 `C:\Scripts` 目录运行 `Get-ServiceLog.ps1` 脚本，请键入：

  ```markdown
      ```powershell
      C:\Scripts\Get-ServiceLog.ps1
      ```
  ```

* 错误示例  ：例如，若要在 **C:\Scripts** 目录运行 **Get-ServiceLog.ps1** 脚本，请键入："C:\Scripts\Get-ServiceLog.ps1."

* 所有隔离代码块都必须具有已批准的语言标记  。 有关支持语言标记的列表，请参阅[如何在文档中包含代码](./code-in-docs.md#supported-languages)。

## <a name="headings-and-link-text"></a>标题和链接文本

不能将内联样式（如斜体、粗体或代码）应用于标题或超链接文本。

**为什么？**

人们依靠标准的超链接文本将文本元素识别为可点击的链接。 例如，将链接设置为代码会掩盖文本是链接的事实。 标题具有特定的样式，混用其他样式显得不美观。

### <a name="examples"></a>示例

* 正确示例  ：*function.json* 文件是由 NuGet 包 [Microsoft.NET.Sdk.Functions](http://www.nuget.org/packages/Microsoft.NET.Sdk.Functions) 生成的。
* 错误示例  ：*function.json* 文件是由 NuGet package [`Microsoft.NET.Sdk.Functions`](http://www.nuget.org/packages/Microsoft.NET.Sdk.Functions) 生成的。

* 正确示例  ：

  ```markdown
  ### The Microsoft.NET.Sdk.Functions package
  ```

* 错误示例  ：

  ```markdown
  ### The `Microsoft.NET.Sdk.Functions` package
  ```

## <a name="keys-and-keyboard-shortcuts"></a>键和键盘快捷方式

引用键或键组合时，请遵循以下约定：

* 将键名称的首字母大写。
* 不要应用斜体、粗体或代码等内联样式。
* 使用“+”连接同时按下的键。

### <a name="examples"></a>示例

* 正确示例  ：选择 Alt+Ctrl+S。
* 错误示例  ：按 **ALT+CTRL+S**。
* 错误示例  ：点击 `ALT+CTRL+S`。

有关详细信息，请参阅[描述与 UI 的交互](https://styleguides.azurewebsites.net/StyleGuide/Read?id=2700&topicid=26472)。

## <a name="exceptions"></a>例外

风格指南并非严格的规则。 如果它们降低了可读性，请进行部分改动。 例如，主要包含代码元素的 HTML 表格如果全部应用代码样式，可能看起来杂乱。 在此情况中，可选择使用粗体样式。

如果选择通常需要代码的替代文本样式，请确保该文本可在文章的本地化版本中进行翻译。 代码是唯一一种自动防止翻译的样式。 如果希望防止本地化但不使用代码样式，请参阅[非本地化字符串](markdown-reference.md#non-localized-strings)。
