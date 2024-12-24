# Jenkins_CI_Test
用于测试jenkins持续构建服务
1. Jenkins安装与配置
下载并安装Jenkins。
配置Jenkins的全局工具（如JDK、Maven等）和插件（如Git插件、Maven插件等）。
配置Jenkins的用户和权限管理。
2. 新建Jenkins任务
在Jenkins首页点击“新建Item”创建一个新任务。
输入任务名称，并选择任务类型（如Freestyle Project、Pipeline等）。
配置任务的源码管理（如Git），并输入仓库地址和认证信息。
3. 配置构建触发器
在任务配置页面，选择“构建触发器”标签。
配置触发器类型（如Build periodically、Poll SCM、Git hook trigger等）。
如果选择Git hook trigger，则需要配置Git的Webhook，以便在代码提交时触发Jenkins构建。
4. 配置构建步骤
在任务配置页面，选择“构建”标签。
添加构建步骤（如执行Shell脚本、调用Maven构建等）。
在构建步骤中编写构建和测试的脚本。
5. 配置构建后操作
在任务配置页面，选择“构建后操作”标签。
添加构建后操作（如发送邮件通知、发布HTML报告、部署到远程服务器等）。
配置发布HTML报告的路径和邮件通知的模板。


配置Git Webhook触发Jenkins构建
1. 在Jenkins中配置Webhook触发器
进入Jenkins任务配置页面：
登录Jenkins。
在Jenkins首页，点击要配置的任务名称，进入任务配置页面。
配置构建触发器：
在任务配置页面中，找到“构建触发器”（Build Triggers）部分。
勾选“Git hook trigger for GITScm polling”（或类似的选项，具体取决于Jenkins插件和版本）。
保存配置。
2. 在Git平台上配置Webhook
进入Git仓库设置页面：
登录Git平台（如GitHub、GitLab、Gitee等）。
找到并点击进入要配置Webhook的仓库。
在仓库设置页面（通常位于右上角或侧边栏），找到并点击“Webhooks”或类似的选项。
添加Webhook：
在Webhooks页面，点击“Add webhook”（或类似的按钮）来添加一个新的Webhook。
填写Webhook URL和配置：
Payload URL：填写Jenkins中生成的Webhook URL。这个URL通常可以在Jenkins任务配置页面的“构建触发器”部分找到，或者通过Jenkins的系统配置页面生成。
Content type：选择“application/json”（或Git平台支持的其他内容类型）。
Secret（可选）：如果Jenkins配置了Webhook的Secret，则在这里填写相同的Secret。这有助于验证Webhook请求的来源。
Events：选择要触发Webhook的事件类型。对于大多数情况，选择“Push events”（代码提交事件）即可。
保存Webhook配置：
填写完Webhook的相关信息后，点击“Add webhook”（或类似的按钮）来保存配置。
3. 测试Webhook
在Git平台上触发事件：
回到Git仓库，进行一次代码提交（或其他触发Webhook的事件）。
检查Jenkins构建：
登录Jenkins，检查之前配置的任务是否因为Webhook的触发而开始构建。
如果构建成功，则Webhook配置正确。如果构建失败，则可能需要检查Webhook URL、Secret、事件类型等配置是否正确。
