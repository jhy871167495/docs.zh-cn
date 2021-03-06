---
title: 使用跟踪对应用程序进行故障排除
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: ee9aaaae80f213f026a222ac1754ae8b4fdf2d37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517038"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>使用跟踪对应用程序进行故障排除
Windows Workflow Foundation (WF) 允许你跟踪工作流相关信息，以执行 Windows Workflow Foundation 应用程序或服务提供详细信息。 Windows Workflow Foundation 主机将能够在执行工作流实例期间捕获工作流事件。 如果你的工作流产生错误或异常，则可以使用 Windows Workflow Foundation 跟踪详细信息以诊断其处理故障。  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>使用 WF 跟踪对 WF 进行故障诊断  
 若要检测的 Windows Workflow Foundation 活动处理中的错误，你可以启用查询的跟踪配置文件的跟踪<xref:System.Activities.Tracking.ActivityStateRecord>与出错的状态。 在以下代码中指定了相应的查询。  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 如果某个错误发生传播并且在错误处理程序（如 <xref:System.Activities.Statements.TryCatch> 活动）中得到了处理，则可以使用 <xref:System.Activities.Tracking.FaultPropagationRecord> 检测到此错误。 <xref:System.Activities.Tracking.FaultPropagationRecord> 可指示错误的源活动以及错误处理程序的名称。 <xref:System.Activities.Tracking.FaultPropagationRecord> 包含错误的异常堆栈形式的错误详细信息。用于订阅 <xref:System.Activities.Tracking.FaultPropagationRecord> 的查询如以下示例中所示。  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 如果某个错误未在工作流中处理，则它会导致工作流实例出现未经处理的异常并且工作流实例被中止。 若要了解未经处理的异常的详细信息，跟踪配置文件必须查询具有以下示例中指定的 `state name="UnhandledException"` 的工作流实例记录。  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 当工作流实例遇到未经处理的异常，<xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>对象，如果已启用 Windows Workflow Foundation 跟踪发出。  
  
 此跟踪记录包含异常堆栈形式的错误详细信息。 它具有的错误 （例如，活动） 错误状态，并且导致未经处理的异常的源的详细信息。若要从 Windows Workflow Foundation，订阅的错误事件，请通过添加跟踪参与者启用跟踪。 通过查询 `ActivityStateQuery (state="Faulted")`、<xref:System.Activities.Tracking.FaultPropagationRecord> 和 `WorkflowInstanceQuery (state="UnhandledException")` 的跟踪配置文件配置此参与者。  
  
 如果使用 ETW 跟踪参与者启用跟踪，则会向 ETW 会话发出错误事件。 可以使用事件查看器查看这些事件。 这可以在节点下找到**事件查看器-> 应用程序和服务日志-> Microsoft-> Windows-> 应用程序服务器-应用程序**在分析通道。  
  
## <a name="see-also"></a>请参阅  
 [Windows Server App Fabric 监视](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [使用 App Fabric 监视应用程序](http://go.microsoft.com/fwlink/?LinkId=201275)
