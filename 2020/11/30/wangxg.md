# [Introducing Dispatch](https://netflixtechblog.com/introducing-dispatch-da4b8a2a8072)

> Netflix 的故障管理系统实践，包括通知、故障跟踪、故障复盘等环节。

- Dispatch 能够高效地处理问题，并且可以通过接入 Slack, GSuite, Jira 等工具形成一个工作流，因此你只需要关注 fix issue 其他的包括创建资源，召集参与者，发通知，跟踪任务，review 等都可以用 Dispatch 去做
- 4个主要的危机管理组件
    - Resource Management
        - 管理与事故相关的资源和上下文信息
    - Individual Engagement
        - 用最好的方式让个人和团队进行参与，并且按照上下文去解决问题
    - Life Cycle Management
        - 使用生命周期管理工具，轻松管理生命周期
    - Incident Learning
        - 复盘学习，为快速解决将来会遇到的问题做准备
- 术语
    - Incident Commanders
        - 负责将问题解决的人
    - Incident Participants
        - 协助解决问题的人
    - Resources
        - 文档、日志、快照等用于解决问题的资源
- 解决问题的几个关键
    - checkList
        - Declare an Incident
            - 自动通知，警报
        - Determine Incident Commander
            - 快速确定问题解决人 Incident Commanders
        - Create Communication Channels
            - 创建一个专门用于沟通这个故障的频道
        - Create Incident Document
            - 创建专门的故障文档
                - including a description of the incident, links to resources, rough notes from in-person meetings, open questions, action items, and timeline information
        - Engage Individual Resources
            - incident commander 需要在组内召集资源，一起解决问题
        - Orient Individual Resources
            - 召集组内资源并不够，incident commander 还需要引导大家问题的方向
        - Notify Key Stakeholders
            - 通知没有参与到这个故障的关键人
        - Drive Incident to Resolution
            - 推动问题解决
            - creating tasks, asking questions, and tracking answers. Making note of key learnings to be addressed after resolution.
        - Perform Post Incident Review (PIR)
            - review 故障处理的过程，跟踪故障发生后的行为，并且记录下要点，推动学习
    - 我们可以看到要完成这些步骤需要 Incident Commanders 和 Incident Participants 反复与各个不同的系统，频繁切换上下文（那么接下来就吃我的安利！Dispatch 帮你解决！）
- 更好的危机管理
    - 使用已有的，熟悉的工具，去降低学习曲线
    - 编好目录，存储和分析故障数据去加快故障的解决
- Dispatch
    - 没有和 AWS API 绑定，不使用任何的 AWS API
    - 能够和 Slack, GSuite, PagerDuty 等工具紧密结合使用
    - 提供多个集成接口，能够和各个环境一起结合使用
    - 不局限于解决安全故障问题，核心是可以控制整个生命周期为事件提供开发者所需要的上下文，开发者只需要去关注具体问题
    - 优势
        - Determine Incident Commander 不再需要处理资源和多数据流问题
        - 沟通标准化
        - Incident participants 能够自动参与到事件中
        - 故障可以跟踪，未解决会自动提醒所有的 owner
        - 所有的故障数据都可以进行跟踪
        - 提供了通用的 API 给内部用户和工具使用
    - Slack for managing incident metadata (e.g. status, title, description, priority, etc,.)
    - Google Doc and Google Drive for managing data
    - 提供 UI 可以点点点
- 架构
    - Python 3.8 with FastAPI
    - VueJS UI
    - Postgres
    - 包含内置插件，可以通过 GSuite (Docs, Drive, Sheets, Calendar, Groups), Jira, PagerDuty, and Slack 等工具来创建任务
- 项目地址
    - [Dispatch Github](https://github.com/Netflix/dispatch)
    