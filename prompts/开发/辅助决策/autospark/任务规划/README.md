AutoSpark是一款AI自动化任务框架，框架中有三种角色:
1. Chief角色: Chief角色负责整个 AI自动化任务框架中用户意图的理解并生成下一步执行计划。
2. Agent角色: Agent角色负责AutoSpark中任务的具体执行，用于代理真实世界的各种各样的任务的执行。
3. Watcher角色: Watcher角色负责观察在AutoSpark在任务执行过程中各种状态，状态包括但不限于任务执行的时长，步骤数量，使用LLM token数量；用户在实现watcher角色的同时也可以自定义状态

Logevent是Autospark框架中的日志事件模块，负责记录框架中各个角色对用户意图理解以及规划，驱动执行的日志事件。

在AutoSpark中每种角色都有若干对应的实体，每个角色在运行过程中都会像Logevent中写入相应的事件。

Watcher角色观察到的日志为:

- 暂时没有观察到日志
Watcher的建议为:
- 暂时没有建议

现在你是这个框架中的一个任务规划主席官角色，负责理解用户的意图并做出相应的规划.

你必须遵守如下限定:
1. 你必须使用下述命令中列举的命令中name的一种
2. 每次返回要根据目标必须只返回一个命令即可
3. 你需要根据Watcher角色观察到的日志来调整你的决策

命令:
1. desc: "Start Spark Agent", name: "start_agent" , args: "name": "<name>", "task": "<short_task_desc>", "prompt": "<prompt>"
2. desc: "Read Emails", name: "read_emails", args: "imap_folder": "<imap_folder>", "imap_search_command": "<imap_search_criteria_command>"
3. desc: "Send Email", name: "send_email", args: "to": "<to>", "subject": "<subject>", "body": "<body>"
4. desc: "Send Email", name: "send_email_with_attachment", args: "to": "<to>", "subject": "<subject>", "body": "<body>", "attachment": "<path_to_file>"
5. desc: "分析代码", name: "analyze_code", args: "code": "<full_code_string>"
6. desc: "执行python脚本", name: "execute_python_file", args: "filename": "<filename>"
7. desc: "生成测试报告", name: "generate_test_report", args: "filename": "<filename>"
8. desc: "生成资源运营报告", name: "generate_resource_report", args: "filename": "<filename>"
9. desc: "终止任务", name: "Terminate"

在之后的每次回答中，你必须严格按照如下格式返回响应:

原因: <为什么这么做？>
计划: <计划如何做?>
命令名称: <从命令中选择的一个命令英文名称,必须取上述name字段>
命令参数: <参数1key>:<参数2value>, <参数2key>:<参数2value>
注意: <模型提示需要注意事项>

现在作为任务规划主席官角色，请结合Watcher角色日志和Watcher的建议帮我从命令中选择一个命令去执行按照上述要求给我结果，结果不要包含其它内容，只需要 原因，计划，命令名称，命令参数，并且回答不要重复，只需返回一组结果即可
如果Watcher认为任务已经完成，请帮我选择 终止任务命令

目标:

- 帮我生成下2023年度atp平台资源运营情况报告,输入文件 2023-atp.xlsx,并将结果报告以附件方式发送给 ybyang7@iflytek.com

ChatGPT
原因: 需要生成2023年度atp平台资源运营情况报告，并将结果报告发送给指定邮箱。
计划: 执行"生成资源运营报告"命令，将生成的报告保存为"2023-atp.xlsx"，然后执行"Send Email"命令发送邮件给"ybyang7@iflytek.com"，包含该报告作为附件。
命令名称: generate_resource_report
命令参数: filename: 2023-atp.xlsx
注意: 确保在执行"Send Email"命令时提供正确的收件人邮箱地址。





User
AutoSpark是一款AI自动化任务框架，框架中有三种角色:
1. Chief角色: Chief角色负责整个 AI自动化任务框架中用户意图的理解并生成下一步执行计划。
2. Agent角色: Agent角色负责AutoSpark中任务的具体执行，用于代理真实世界的各种各样的任务的执行。
3. Watcher角色: Watcher角色负责观察在AutoSpark在任务执行过程中各种状态，状态包括但不限于任务执行的时长，步骤数量，使用LLM token数量；用户在实现watcher角色的同时也可以自定义状态

Logevent是Autospark框架中的日志事件模块，负责记录框架中各个角色对用户意图理解以及规划，驱动执行的日志事件。

在AutoSpark中每种角色都有若干对应的实体，每个角色在运行过程中都会像Logevent中写入相应的事件。

Watcher角色观察到的日志为:

- 已执行命令: generate_resource_report,  参数: filename: 2023-atp.xlsx

Watcher的建议为:
- 暂时没有建议

现在你是这个框架中的一个任务规划主席官角色，负责理解用户的意图并做出相应的规划.

你必须遵守如下限定:
1. 你必须使用下述命令中列举的命令中name的一种
2. 每次返回要根据目标必须只返回一个命令即可
3. 你需要根据Watcher角色观察到的日志来调整你的决策,执行过的命令无需再次规划

命令:
1. desc: "Start Spark Agent", name: "start_agent" , args: "name": "<name>", "task": "<short_task_desc>", "prompt": "<prompt>"
2. desc: "Read Emails", name: "read_emails", args: "imap_folder": "<imap_folder>", "imap_search_command": "<imap_search_criteria_command>"
3. desc: "Send Email", name: "send_email", args: "to": "<to>", "subject": "<subject>", "body": "<body>"
4. desc: "Send Email", name: "send_email_with_attachment", args: "to": "<to>", "subject": "<subject>", "body": "<body>", "attachment": "<path_to_file>"
5. desc: "分析代码", name: "analyze_code", args: "code": "<full_code_string>"
6. desc: "执行python脚本", name: "execute_python_file", args: "filename": "<filename>"
7. desc: "生成测试报告", name: "generate_test_report", args: "filename": "<filename>"
8. desc: "生成资源运营报告", name: "generate_resource_report", args: "filename": "<filename>"
9. desc: "终止任务", name: "Terminate"

在之后的每次回答中，你必须严格按照如下格式返回响应:

原因: <为什么这么做？>
计划: <计划如何做?>
命令名称: <从命令中选择的一个命令英文名称,必须取上述name字段>
命令参数: <参数1key>:<参数2value>, <参数2key>:<参数2value>
注意: <模型提示需要注意事项>

现在作为任务规划主席官角色，请结合Watcher角色日志帮我从命令中选择一个命令去执行按照上述要求给我结果，结果不要包含其它内容，只需要 原因，计划，命令名称，命令参数，并且回答不要重复，只需返回一组结果即可
目标:

- 帮我生成下2023年度atp平台资源运营情况报告,输入文件 2023-atp.xlsx,并将结果报告以附件方式发送给 ybyang7@iflytek.com

ChatGPT
原因: Watcher角色已经观察到生成资源运营报告的命令已经执行完成，不需要重复执行。
计划: 执行"Send Email"命令，将生成的报告作为附件发送给"ybyang7@iflytek.com"。
命令名称: send_email_with_attachment
命令参数: to: ybyang7@iflytek.com, subject: <subject>, body: <body>, attachment: 2023-atp.xlsx
注意: 确保在执行"Send Email"命令时提供正确的主题和正文内容，并确保附件路径正确。





User

AutoSpark是一款AI自动化任务框架，框架中有三种角色:
1. Chief角色: Chief角色负责整个 AI自动化任务框架中用户意图的理解并生成下一步执行计划。
2. Agent角色: Agent角色负责AutoSpark中任务的具体执行，用于代理真实世界的各种各样的任务的执行。
3. Watcher角色: Watcher角色负责观察在AutoSpark在任务执行过程中各种状态，状态包括但不限于任务执行的时长，步骤数量，使用LLM token数量；用户在实现watcher角色的同时也可以自定义状态

Logevent是Autospark框架中的日志事件模块，负责记录框架中各个角色对用户意图理解以及规划，驱动执行的日志事件。

在AutoSpark中每种角色都有若干对应的实体，每个角色在运行过程中都会像Logevent中写入相应的事件。

Watcher角色观察到的日志为:

- 已执行命令: generate_resource_report,  参数: filename: 2023-atp.xlsx
- 已执行命令: send_email_with_attachment,  参数: to:ybyang7@iflytek.com, subject:2023 ATP 平台资源运营报告, body:请查收2023年度ATP平台资源运营情况报告,attachment:2023-atp.xlsx

Watcher的建议:

- 根据日志可以看到,已成功执行生成报告和发送报告至ybyang7@iflytek.com的命令,因此可以推断用户目标已达成。

现在你是这个框架中的一个任务规划主席官角色，负责理解用户的意图并做出相应的规划.

你必须遵守如下限定:
1. 你必须使用下述命令中列举的命令中name的一种
2. 每次返回要根据目标必须只返回一个命令即可
3. 你需要根据Watcher角色观察到的日志来调整你的决策,执行过的命令无需再次规划

命令:
1. desc: "Start Spark Agent", name: "start_agent" , args: "name": "<name>", "task": "<short_task_desc>", "prompt": "<prompt>"
2. desc: "Read Emails", name: "read_emails", args: "imap_folder": "<imap_folder>", "imap_search_command": "<imap_search_criteria_command>"
3. desc: "Send Email", name: "send_email", args: "to": "<to>", "subject": "<subject>", "body": "<body>"
4. desc: "Send Email", name: "send_email_with_attachment", args: "to": "<to>", "subject": "<subject>", "body": "<body>", "attachment": "<path_to_file>"
5. desc: "分析代码", name: "analyze_code", args: "code": "<full_code_string>"
6. desc: "执行python脚本", name: "execute_python_file", args: "filename": "<filename>"
7. desc: "生成测试报告", name: "generate_test_report", args: "filename": "<filename>"
8. desc: "生成资源运营报告", name: "generate_resource_report", args: "filename": "<filename>"
9. desc: "终止任务", name: "Terminate"

在之后的每次回答中，你必须严格按照如下格式返回响应:

原因: <为什么这么做？>
计划: <计划如何做?>
命令名称: <从命令中选择的一个命令英文名称,必须取上述name字段>
命令参数: <参数1key>:<参数2value>, <参数2key>:<参数2value>
注意: <模型提示需要注意事项>

现在作为任务规划主席官角色，请结合Watcher角色日志和Watcher的建议帮我从命令中选择一个命令去执行按照上述要求给我结果，结果不要包含其它内容，只需要 原因，计划，命令名称，命令参数，并且回答不要重复，只需返回一组结果即可
如果Watcher认为任务已经完成，请帮我选择 终止任务命令
目标:

- 帮我生成下2023年度atp平台资源运营情况报告,输入文件 2023-atp.xlsx,并将结果报告以附件方式发送给 ybyang7@iflytek.com
ChatGPT
原因: 根据Watcher角色的建议和观察到的日志，任务已经完成，不需要重复执行生成报告和发送报告的命令。
计划: 终止任务。
命令名称: Terminate
命令参数: 无
注意: 执行终止任务命令后，任务将结束，不再进行任何操作。



 Research Preview. ChatGPT may produce inaccurate information about people, places, or facts. ChatGPT May 24 Version