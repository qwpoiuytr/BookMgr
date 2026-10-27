# BadLudan · 图书管理系统（BookMgr）

自己的期末作业，布局和代码都很差~不要在意啦~

一个 ASP.NET Web Forms 的图书借阅/购买管理系统：登录注册、图书浏览、购物车、下单，以及后台图书管理。

## 技术栈

| 层 | 内容 |
| --- | --- |
| 表现层 | ASP.NET Web Forms（`.aspx` + MasterPage），.NET Framework 4.0 |
| 业务层 | `BLL` 项目（C#） |
| 数据层 | `DAL` 项目（C#，ADO.NET） |
| 实体 | `Model` 项目（C#） |
| 数据库 | SQL Server 2012（`数据库2012/BookMgr.mdf`） |
| 工具 | Visual Studio 2013+（`书籍管理系统/Login.sln`） |

## 目录结构

```
BookMgr/
├── 书籍管理系统/             # VS 解决方案
│   ├── Login.sln
│   ├── Model/                # 实体类
│   ├── DAL/                  # 数据访问
│   ├── BLL/                  # 业务逻辑
│   └── web/                  # 网站
│       ├── Default.aspx      # 默认页
│       ├── login.aspx*       # 登录
│       ├── Register.aspx     # 注册
│       ├── home_page.aspx    # 首页 / 图书列表
│       ├── bookShow.aspx     # 图书详情
│       ├── BookMin.aspx      # 图书管理（后台）
│       ├── ShopingCart.aspx  # 购物车
│       ├── Indent.aspx       # 下单 / 订单
│       └── MasterPage2.master
└── 数据库2012/
    ├── BookMgr.mdf           # 数据库文件
    ├── BookMgr_log.LDF
    └── sql说明.txt            # 默认数据库账号说明
```

## 本地跑起来

1. **附加数据库**：SQL Server Management Studio → 右键「数据库」→「附加」→ 选 `数据库2012/BookMgr.mdf`
2. **改连接串**：`书籍管理系统/web/Web.config` 里的 `connectionString`，按你本机的实例名和账号调整
3. **打开解决方案**：`书籍管理系统/Login.sln`，把 `web` 设为启动项目，F5 运行

> 数据库走 SQL Server 身份验证，默认账号见 `数据库2012/sql说明.txt`。

## 说明与待改进

- `Web.config` 里是明文的 `sa` 账号密码，放公开仓库不合适；建议改成 `Integrated Security=true`，或放进环境变量 / `Web.Release.config`。
- `*.suo`、`UpgradeLog.htm`、`Bin/` 这类本地产物不该进版本库，用 `.gitignore` 排掉。
- 前端布局比较粗糙，功能优先。
