# 仿小红书前端项目

## 🎯 项目介绍
本项目是一个模仿小红书的前端项目。Vue 在移动端的"最佳实践"，使用了最新的 Vue 技术栈，基于 Vue3、Vite5、Pinia实现。数据使用浏览器内置的 IndexDB 数据库进行本地存储。
![image.png](https://cloundpic.obs.cn-east-3.myhuaweicloud.com/images/result.jpeg)

## 👀 在线访问


## 💡特性

- 用户认证：登录、注册、退出
- 笔记管理：发布、编辑、删除笔记
- 个人中心：用户信息管理
- 数据持久化：使用 IndexDB 实现本地数据存储
- 响应式设计：基本适配各种移动端设备
- 瀑布流布局：首页、分类页、搜索页、笔记详情页

## 👻项目技术栈

- 核心框架：Vue 3
- 构建工具：Vite 5
- 状态管理：Pinia
- 数据存储：IndexDB
- 路由管理：Vue Router
- 开发语言：TypeScript

## 项目目录结构

├── src/
│ ├── components/ # 公共组件
│ ├── stores/ # Pinia 状态管理
│ ├── views/ # 页面视图
│ ├── router/ # 路由配置
│ ├── utils/ # 工具函数
│ ├── App.vue # 根组件
│ └── main.ts # 入口文件
├── public/ # 静态资源
├── index.html # HTML 模板
└── package.json # 项目配置文件

## 📖安装与运行

```bash
git clone https://github.com/kitcaf/htmlProject.git
cd htmlProject
npm install
```