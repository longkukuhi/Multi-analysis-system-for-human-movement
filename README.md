# 人体运动与环境分析

这个 Windows 原型集合分别涉及摄像头环境分析、动作分析与预警，以及跌倒检测。要从源码了解摄像头画面如何进入分析流程，可先打开环境分析的 C# 解决方案。

| 模块 | 从哪里开始 | 现有材料 |
| --- | --- | --- |
| 环境分析 | [VideoFrameAnalysis.sln](Enviroment%20analysis/Enviroment%20analysis/VideoFrameAnalysis.sln) | 提供采集视频帧的共享库、控制台示例和带摄像头预览的 WPF 界面。 |
| 动作分析与预警 | [Post analysis and warning system](Post%20analysis%20and%20warning%20system) | 包含 Visual Studio 解决方案和当时生成的 Debug 程序。 |
| 跌倒检测 | [detection of falling down](detection%20of%20falling%20down) | 包含独立目录中的解决方案和 Debug 程序。 |

## 阅读或构建环境分析模块

在 Windows 的 Visual Studio 中打开上面的 C# 解决方案并还原 NuGet 包。`LiveCameraSample` 以 .NET Framework 4.5.2 为目标，调用 OpenCvSharp 获取视频帧。原始示例可将帧发给 Microsoft Cognitive Services 进行分析，在线功能依赖相应服务和用户自己的凭据。摄像头预览、控制台示例和服务设置见[上游示例说明](Enviroment%20analysis/Enviroment%20analysis/README.md)。该示例附有 [MIT 许可证](Enviroment%20analysis/Enviroment%20analysis/LICENSE.md)。

## 两个检测项目的构建条件

两个 `detection.sln` 均指向外部的 `MFC_DEMO01.vcxproj`。当前仓库里有两份解决方案和历史构建产物。若要重新编译，需要取得原来的 MFC 工程及其源文件。
