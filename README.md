# 🌾 农产品电商平台

基于 Spring Boot + Vue.js 的现代化农产品电商平台，为农户和消费者提供便捷的农产品交易服务。

## 📋 项目简介

本项目是一个功能完整的农产品电商平台，采用前后端分离架构，支持用户注册登录、商品管理、订单处理、支付结算、物流跟踪等核心电商功能。

### ✨ 主要特性

- 🔐 **用户认证系统** - JWT Token 认证，支持邮箱验证
- 🛒 **商品管理** - 商品分类、库存管理、商品推荐
- 📦 **订单系统** - 订单创建、状态跟踪、退款处理
- 💳 **支付集成** - 支付宝沙箱支付
- 📧 **邮件服务** - 注册验证、订单通知
- 🚚 **物流管理** - 物流信息跟踪
- ⭐ **评价系统** - 商品评价、用户反馈
- 📊 **数据统计** - 用户行为分析、销售统计

## 🏗️ 技术架构

### 后端技术栈
- **框架**: Spring Boot 3.4.1
- **数据库**: MySQL 8.0
- **ORM**: MyBatis Plus 3.5.7
- **安全**: Spring Security + JWT
- **文档**: Knife4j (Swagger)
- **工具**: Hutool、Lombok
- **邮件**: Spring Boot Mail
- **支付**: 支付宝 SDK

### 前端技术栈
- **框架**: Vue.js 2.6.14
- **UI组件**: Element UI 2.15.14
- **路由**: Vue Router 3.5.1
- **状态管理**: Vuex 3.6.2
- **HTTP客户端**: Axios 1.7.9
- **富文本编辑器**: WangEditor 5.1.23
- **图表**: ECharts 5.6.0
- **样式**: Less、Sass

## 📁 项目结构

```
springboot-农产品商城/
├── springboot/                 # 后端项目
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/           # Java 源码
│   │   │   └── resources/      # 配置文件
│   │   └── test/               # 测试代码
│   ├── doc/                    # API 文档
│   ├── files/                  # 文件存储
│   └── pom.xml                 # Maven 配置
├── vue_template/               # 前端项目
│   ├── src/
│   │   ├── api/               # API 接口
│   │   ├── components/        # Vue 组件
│   │   ├── views/             # 页面视图
│   │   ├── router/            # 路由配置
│   │   ├── utils/             # 工具函数
│   │   └── assets/            # 静态资源
│   └── package.json           # NPM 配置
├── 部署/                       # 部署相关文件
│   ├── apache-maven-3.9.5/   # Maven 工具
│   └── 部署文档.md             # 部署说明
└── README.md                  # 项目说明
```

## 🚀 快速开始

### 环境要求

- **JDK**: 17 或更高版本
- **Node.js**: 14.x 或更高版本
- **MySQL**: 8.0 或更高版本
- **Maven**: 3.6 或更高版本

### 1. 数据库配置

1. 创建数据库 `agricultural_product_system`
2. 导入 SQL 文件（位于项目根目录）
3. 默认用户密码均为 `123456`

**MySQL 5.7 用户需要执行：**
```sql
SET GLOBAL INNODB_LARGE_PREFIX = ON;
```

### 2. 后端启动

1. **配置数据库连接**
   编辑 `springboot/src/main/resources/application.properties`：
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/agricultural_product_system
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   ```

2. **配置邮箱服务**
   ```properties
   spring.mail.username=your_email@qq.com
   spring.mail.password=your_auth_code
   user.fromEmail=your_email@qq.com
   ```

3. **启动后端服务**
   ```bash
   cd springboot
   mvn spring-boot:run
   ```

### 3. 前端启动

1. **安装依赖**
   ```bash
   cd vue_template
   npm install
   ```

2. **启动开发服务器**
   ```bash
   npm run serve
   ```

3. **访问应用**
   - 前端地址: http://localhost:8080
   - 后端API: http://localhost:8081
   - API文档: http://localhost:8081/doc.html

## 📚 API 文档

项目提供完整的 RESTful API，主要模块包括：

### 核心模块
- **用户管理** (`/user`) - 用户注册、登录、信息管理
- **商品管理** (`/product`) - 商品CRUD、分类管理
- **订单管理** (`/order`) - 订单创建、状态更新、退款
- **购物车** (`/cart`) - 购物车操作
- **支付系统** (`/alipay`) - 支付宝支付集成
- **物流管理** (`/logistics`) - 物流信息跟踪
- **评价系统** (`/review`) - 商品评价管理

### 辅助模块
- **文件上传** (`/file`) - 图片、文档上传
- **邮件服务** (`/email`) - 邮件发送
- **通知公告** (`/notice`) - 系统通知
- **用户行为** (`/behavior`) - 行为统计分析

详细 API 文档请访问：http://localhost:8081/doc.html

## 🔧 配置说明

### 支付宝沙箱配置

1. 注册支付宝开放平台账号
2. 创建沙箱应用
3. 配置应用公钥和私钥
4. 更新 `application.properties` 中的支付配置

### 邮箱服务配置

1. 开启 QQ 邮箱 SMTP 服务
2. 获取授权码
3. 配置邮箱相关参数

## 🎯 功能特色

### 用户端功能
- 🏠 **首页展示** - 商品轮播、分类导航、推荐商品
- 🔍 **商品搜索** - 关键词搜索、分类筛选
- 🛒 **购物车** - 商品添加、数量调整、批量操作
- 📋 **订单管理** - 订单查看、状态跟踪、申请退款
- 💳 **在线支付** - 支付宝支付集成
- ⭐ **商品评价** - 购买后评价、查看他人评价
- 👤 **个人中心** - 个人信息、收货地址、订单历史

### 管理端功能
- 📊 **数据统计** - 销售数据、用户统计、商品分析
- 👥 **用户管理** - 用户列表、状态管理、权限控制
- 📦 **商品管理** - 商品发布、库存管理、分类设置
- 📋 **订单管理** - 订单处理、发货管理、退款审核
- 🎠 **轮播管理** - 首页轮播图设置
- 📢 **公告管理** - 系统公告发布

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request 来改进项目！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情

## 📞 联系方式

如有问题或建议，请通过以下方式联系：

- 📧 Email: [your-email@example.com]
- 🐛 Issues: [GitHub Issues](https://github.com/bctyq/springboot-/issues)

## 🙏 致谢

感谢所有为这个项目做出贡献的开发者！

---

⭐ 如果这个项目对你有帮助，请给个 Star 支持一下！
