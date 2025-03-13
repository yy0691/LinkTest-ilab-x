# LinkTest-ilab-x
批量测试国家实验空间ilab-x中的实验联通性，并截图发送至指定邮箱

# 使用说明

- 运行`main.exe`文件，可以自动登录、打开实验界面截图，并发送至指定邮箱

- 运行前需要使用最新版本（132版本及以上）的`chrome`浏览器

  <img src="D:\PixPin\Temp\Pixpin_2501-11.png" alt="Pixpin_2501-11" style="zoom: 67%;" />

- 浏览器下载链接： https://musetransfer.com/s/bqqvxrpkl

# 配置文件

## 文件名称

`config.json`

## 配置内容

### 收件邮箱

- 可设置多个收件人
- 示例
  - 一个收件人代码： `"to_email": [ "XXX@rainier.net.cn" ],`
  - 两个收件人代码：`"to_email": [ "XXX@rainier.net.cn", "XXX@qq.com" ],`
  - 后续依次类推……

- 注意：只能修改 " " 符号中的内容，其他符号不要删除

### ilab-x账号

- 用户名：` "user": "XXXX"`	
- 密码：`"password": "XXXX"`
- 需要将`XXXX`部分替换为自己 ilab 账号（手机号/邮箱/用户名）和密码 

### 需要测试的实验修改

- 实验链接：`"url": "https://www.ilab-x.com/details/page?id=XXXXX&isView=true"`
- 实验名称：`"name": "XXX项目"`

### 特别说明

如有需要点击评审入口或者有安全风险的实验，需要按照以下说明添加 `"experiment_actions"` 部分的实验 `id`

#### 有评审入口的实验

- 添加名为 `"click_review_entry" action`的 `id`

#### 有安全风险的实验

- 添加名为 `"handle_insecure_connection" action`的 `id`

示例代码如下：

```json
"experiment_actions": {
        "20000": {
            "action": "handle_insecure_connection"
        },
        "11111": {
            "action": "handle_insecure_connection"
        },
        "1234": {
            "action": "click_review_entry"
        }
    }
```

# 创建自动任务

1. 打开**任务计划程序**：右键点击 “此电脑”，选择 “管理”，在计算机管理窗口中，点击左侧的 “任务计划程序”。
2. **创建基本任务**：点击右侧的 **“创建基本任务”**，输入任务的名称和描述，点击 “下一步”。
3. 设置触发器：**选择任务的触发条件**为 “每天”，然后根据所选的触发条件进行相应的设置，如指定具体的时间、日期等，点击 “下一步”。
4. **设置操作**：选择 “启动程序”，点击 “下一步”，在 “程序或脚本” 框内输入要运行的程序或脚本的路径，也可以点击 “浏览” 按钮查找，点击 “下一步”。
5. **完成任务创建**：查看设置好的内容，确认无误后点击 “完成”。
