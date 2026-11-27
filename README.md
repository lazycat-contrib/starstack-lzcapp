# 星栈 · StarStack

在懒猫微服上用自然语言查找自己 star 过的 GitHub 仓库。适用于 AMD64 微服，要求系统 1.6.0 或更高版本。[上游使用说明](https://github.com/ca-x/starstack) · [下载 LPK](https://github.com/lazycat-contrib/starstack-lzcapp/releases/latest)

1. 安装时保存初始管理员密码，打开星栈，以 `admin` 登录。管理员可为其他人建立独立账号。每位微服用户首次登录成功后，客户端会为该用户填充登录表单。
2. 在「同步与索引」连接自己的 GitHub 账号。使用设备授权时，在安装参数中填写已启用 Device Flow 的 OAuth App Client ID。个人令牌可直接在用户设置中配置。
3. 下载检索模型，然后同步收藏并建立索引。内置模型在微服上运行。聊天服务由管理员按需配置。
4. 在星栈内创建个人 MCP 令牌，将应用域名下的 `/mcp` 和令牌填入助手。数据库、模型和索引保存在应用持久目录。

发布工作流每日检查上游稳定版本，将镜像复制到懒猫镜像仓库，构建版本化 LPK，并将同一份安装包发布到喵喵商店和提交官方审核。官方商店素材包含桌面、手机各三张实机界面截图。维护者可在 Actions 手动运行工作流。需要组织或仓库级 Actions Secrets `LZC_API_TOKEN`、`APPSTORE_URL`、`APPSTORE_TOKEN`。
