# 星栈 · StarStack

在懒猫微服上用自然语言查找自己 star 过的 GitHub 仓库。适用于 AMD64 微服，要求系统 1.6.0 或更高版本。[上游使用说明](https://github.com/ca-x/starstack) · [下载 LPK](https://github.com/lazycat-contrib/starstack-lzcapp/releases/latest)

1. 首次打开星栈时，填写你选择的用户名和密码，创建首个管理员。也可以在安装向导中同时填写初始管理员用户名和密码，打开星栈后直接登录。管理员可为其他人建立独立账号。每位微服用户首次登录成功后，客户端会为该用户填充登录表单。
2. 在「同步与索引」连接自己的 GitHub 账号。向导已填入星栈的公开 Client ID，打开应用后即可发起 Device Flow，也可以在安装参数中更换为自己的 Client ID。个人令牌可直接在用户设置中配置。
3. 在「同步与索引 → 模型市场」下载检索模型，然后同步收藏并建立索引。内置模型在微服上运行。聊天服务由管理员按需配置。
4. 在星栈内创建个人 MCP 令牌，将应用域名下的 `/mcp` 和令牌填入助手。数据库、模型和索引保存在应用持久目录。可以在「MCP 接入 → 检索与推荐」按账号开启 AI 查询改写。

## 配置 GitHub 设备授权

1. 在 GitHub 打开 **Settings → Developer settings → OAuth Apps → New OAuth App**。填写 **Application name**，将 **Homepage URL** 和 **Redirect URI** 都填为应用主页，例如 `https://github.com/ca-x/starstack`。星栈通过设备码向 GitHub 查询授权结果，无需在懒猫配置回调路径。[创建 OAuth App](https://github.com/settings/applications/new)
2. 取消勾选 **Allow wildcard matching**，勾选 **Enable Device Flow**。如果表单提供 **Expire user access tokens**，建议取消勾选。星栈目前尚未实现自动续期，令牌过期后需要重新授权。
3. 注册后复制 **Client ID**，填入懒猫应用配置「GitHub 设备授权客户端 ID」。保存后打开星栈，在「同步与索引」发起设备授权，按提示在 GitHub 输入短码。设备授权只需要 Client ID。

## 发布

发布工作流每日检查上游稳定版本，将镜像复制到懒猫镜像仓库，构建版本化 LPK，并将同一份安装包发布到喵喵商店和提交官方审核。官方商店素材包含桌面、手机各三张实机界面截图。维护者可在 Actions 手动运行工作流。需要组织或仓库级 Actions Secrets `LZC_API_TOKEN`、`APPSTORE_URL`、`APPSTORE_TOKEN`。
