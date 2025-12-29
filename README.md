# 🧭 Travel Diary（旅游日记）

<p align="center">
  <img src="https://img.shields.io/badge/Status-MVP_Complete-success" alt="Status">
  <img src="https://img.shields.io/badge/Platform-WeChat_Mini_Program-green" alt="Platform">
  <img src="https://img.shields.io/badge/Backend-Spring_Boot_3-brightgreen" alt="Backend">
  <img src="https://img.shields.io/badge/Frontend-UniApp_Vue3-blue" alt="Frontend">
  <img src="https://img.shields.io/badge/License-MIT-lightgrey" alt="License">
</p>

> **记录每一刻的风景与感动。**
>
> Travel Diary 是一个基于 **时间轴 + 照片叙事** 的个人旅游记录微信小程序，辅助以结构化的开销统计和足迹地图可视化，旨在提供清晰、纯粹的旅行回忆体验。

---

## 📸 应用截图

<p align="center">
  <img src="https://gitee.com/easyxdc/easyxdc_blog/raw/master/Typora_Images/%E7%99%BB%E9%99%86%E9%A1%B5.png" width="150" alt="登陆页">
  <img src="https://gitee.com/easyxdc/easyxdc_blog/raw/master/Typora_Images/%E9%A6%96%E9%A1%B5.png" width="150" alt="首页">
  <img src="https://gitee.com/easyxdc/easyxdc_blog/raw/master/Typora_Images/%E8%A1%8C%E7%A8%8B%E8%AF%A6%E7%BB%86%E9%A1%B5.png" width="150" alt="行程详情">
  <img src="https://gitee.com/easyxdc/easyxdc_blog/raw/master/Typora_Images/%E7%BB%9F%E8%AE%A1%E9%A1%B5.png" width="150" alt="统计页">
  <img src="https://gitee.com/easyxdc/easyxdc_blog/raw/master/Typora_Images/%E4%B8%AA%E4%BA%BA%E4%B8%AD%E5%BF%83%E9%A1%B5.png" width="150" alt="个人中心">
</p>



<p align="center">
  <em>从左到右：登陆页、首页行程列表、行程详情时间轴、排行榜统计、个人中心足迹地图</em>
</p>

---

## 🛠️ 技术栈

本项目采用**前后端分离架构**，前端基于 uni-app 开发微信小程序，后端采用 Spring Boot 3 构建 RESTful API。

### 前端技术

| 技术 | 版本 | 说明 |
|------|------|------|
| **uni-app** | Vue 3 | 跨端开发框架 |
| **uView UI** | v2 | 高颜值 UI 组件库 |
| **ECharts** | lime-echart | 小程序端数据可视化 |

### 后端技术

| 技术 | 版本 | 说明 |
|------|------|------|
| **Spring Boot** | 3.x | 核心后端框架 |
| **MyBatis Plus** | 3.5.x | ORM 持久层框架 |
| **MySQL** | 8.x | 关系型数据库 |
| **Redis** | 7.x | 缓存服务 |
| **Flyway** | - | 数据库迁移管理 |
| **JWT** | jjwt 0.12.x | 用户身份认证 |
| **阿里云 OSS** | - | 对象存储服务 |

---

## ✨ 核心功能

### 🗺️ 行程管理

- **全周期记录**：创建、编辑及管理每一次完整的出行
- **时间轴叙事**：以"Day"为节点，按日期分组展示旅程脉络
- **状态切换**：支持「进行中」和「已完成」两种状态
- **封面自定义**：为每次旅行设置专属封面图片

### 📝 日记与记账

- **日记节点**：记录标题、内容、时间，支持多图上传
- **消费节点**：记录金额、分类、备注
- **灵活分类**：支持餐饮、交通、住宿、门票、购物等分类
- **快捷编辑**：支持节点的增删改操作

### 📊 数据统计（排行榜风格）

- **城市消费排行** TOP5
- **消费分类占比**（可视化进度条）
- **日均花费排行**
- **旅行时长排行** TOP3
- **新解锁城市**列表
- 支持**年月筛选**

### 🗾 足迹地图

- **中国地图**可视化已探索城市
- 散点大小根据**访问次数**动态变化
- **飞线动画**展示旅行轨迹
- **省份高亮**显示已到访区域
- 支持查看某城市的所有行程

### 🔧 更多功能

- **微信一键登录**（无需注册）
- **个人资料编辑**（昵称、头像）
- **数据导出**（CSV 格式）
- **API 文档**（自动生成）
- **日历视图**（标记旅行日期）

---

## 📁 项目结构

```
TravelDiary/
├── frontend/                 # 前端项目 (uni-app)
│   ├── src/
│   │   ├── components/       # 组件
│   │   │   ├── views/        # 核心视图 (HomeView, StatsView, ProfileView)
│   │   │   ├── AddMomentModal/
│   │   │   ├── AddTripModal/
│   │   │   └── ...
│   │   ├── pages/            # 页面
│   │   ├── service/          # API 服务层
│   │   └── static/           # 静态资源
│   └── package.json
│
├── backend/                  # 后端项目 (Spring Boot)
│   ├── src/main/java/com/travel/diary/
│   │   ├── controller/       # API 控制器
│   │   ├── service/          # 业务逻辑层
│   │   ├── entity/           # 实体类
│   │   ├── dto/              # 数据传输对象
│   │   ├── vo/               # 视图对象
│   │   ├── mapper/           # MyBatis 映射
│   │   ├── config/           # 配置类
│   │   └── common/           # 公共组件
│   ├── src/main/resources/
│   │   ├── application.yml   # 应用配置
│   │   └── db/migration/     # Flyway 迁移脚本
│   └── pom.xml
│
├── doc/                      # 文档
│   └── API.md                # 接口文档 (自动生成)
│
├── screenshots/              # 应用截图 (待添加)
│
└── README.md
```

---

## 🚀 快速开始

### 环境要求

- **Node.js** >= 16
- **JDK** >= 17
- **MySQL** >= 8.0
- **Redis** >= 7.0
- **微信开发者工具**

### 后端启动

1. **克隆项目**
   ```bash
   git clone <repository-url>
   cd TravelDiary/backend
   ```

2. **配置数据库**
   - 创建 MySQL 数据库 `TravelDiary`
   - 修改 `application.yml` 中的数据库连接配置

3. **配置 Redis**
   - 确保 Redis 服务已启动
   - 修改 `application.yml` 中的 Redis 配置

4. **配置阿里云 OSS**（可选，用于图片存储）
   - 在 `application.yml` 中配置 OSS 密钥

5. **启动服务**
   ```bash
   mvn spring-boot:run
   ```

6. **访问 API 文档**
   - Swagger UI: `http://localhost:8080/swagger-ui.html`
   - OpenAPI JSON: `http://localhost:8080/v3/api-docs`

### 前端启动

1. **安装依赖**
   ```bash
   cd TravelDiary/frontend
   npm install
   ```

2. **开发模式运行**
   ```bash
   npm run dev:mp-weixin
   ```

3. **微信开发者工具**
   - 打开微信开发者工具
   - 导入项目：`frontend/dist/dev/mp-weixin`
   - 配置 AppID（或使用测试号）

### 真机调试

修改 `frontend/src/service/api.js` 中的 `BASE_URL` 为电脑 IP 地址：

```javascript
const BASE_URL = 'http://192.168.x.x:8080';
```

---

## 📊 数据库设计

### 核心表结构

| 表名 | 说明 |
|------|------|
| `tb_user` | 用户表 |
| `tb_trip` | 行程表 |
| `tb_trip_node` | 行程节点表（日记/消费） |

详细字段请参阅 [需求文档](./旅游管理微信小程序需求文档.md)

---

## 🔗 API 接口

| 模块 | 端点 | 说明 |
|------|------|------|
| 用户 | `POST /api/user/login` | 微信登录 |
| 用户 | `GET /api/user/current` | 获取当前用户 |
| 行程 | `PUT /api/trip/create` | 创建行程 |
| 行程 | `GET /api/trip/list` | 行程列表 |
| 行程 | `GET /api/trip/{id}/detail` | 行程详情 |
| 节点 | `POST /api/node/add` | 添加节点 |
| 统计 | `GET /api/stats/ranking` | 排行榜统计 |
| 文件 | `POST /api/file/upload` | 上传文件 |

完整文档：[doc/API.md](./doc/API.md)

---

## 🎨 设计特点

- **Bento Grid** 风格统计卡片
- **毛玻璃效果** (Glassmorphism) 弹窗
- **主题绿色** (#748E63) 品牌色系
- **流畅动画** 过渡效果
- **响应式布局** 适配不同机型

---

## 📝 待办事项

- [ ] 添加应用截图到 `screenshots/` 文件夹
- [ ] 配置 GitHub Actions CI/CD
- [ ] 添加单元测试
- [ ] 支持多语言（i18n）
- [ ] 年度报告生成功能
- [ ] 地图轨迹记录功能

---

## 📄 开源协议

本项目采用 [MIT License](./LICENSE) 开源协议。

---

## 🙏 致谢

- [uni-app](https://uniapp.dcloud.io/) - 跨端开发框架
- [uView UI](https://www.uviewui.com/) - UI 组件库
- [ECharts](https://echarts.apache.org/) - 可视化图表库
- [Spring Boot](https://spring.io/projects/spring-boot) - 后端框架
