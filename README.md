# Warehouse Management System

#### 介绍
Course Design of DataBase, HFUT, 2020

#### 软件运行截图

##### 用户管理界面
![用户管理界面](https://gitee.com/hfut-xyc/Warehouse-Management-System/raw/master/screenshot/user.jpg)

##### API文档
![API文档](https://gitee.com/hfut-xyc/Warehouse-Management-System/raw/master/screenshot/api-doc.jpg)

前期为了调试方便，暂时把登录验证给去掉了，可以直接通过localhost:8080/home访问主页
测试登录接口可以用
- 用户名：admin
- 密码：admin

#### 项目运行和注意事项
1. 安装Java 8+、Maven、node.js和npm
2. npm安装@vue/cli和vue的开发服务器(建议换成阿里镜像源cnpm)
3. 安装MySQL 8.0+，配置root用户的密码为root，服务器端口号为3306
4. 运行init.sql，初始化数据库
5. 启动数据库服务程序`systemctl start mysql`(Linux)
6. 启动后端服务器`mvn spring-boot:run`
7. 启动前端服务器`npm run serve`
8. 实体类通过使用Lombok库的注解来自动生成setter和getter方法，提高了开发效率，代码变得简洁易读。如果在`Intellij Idea`上运行，记得要去`settings->plugins`下搜索安装Lombok插件(==需要科学上网==)，不然代码会报错(不安装的话不影响运行，但是报错总会让人不舒服=_=)
9. 后端程序运行后，可以访问 [localhost:8081/swagger-ui.html](localhost:8081/swagger-ui.html) 来查看所有的API文档，并且支持在文档上测试接口

#### RESTful API设计约定
1. 后端程序统一返回json格式给前端，只负责提供数据，不用管页面如何跳转
2. 数据库交互时，select操作一律采用`GET`请求，insert和update操作使用`POST`请求，delete操作使用`DELETE`请求
3. 接口url的设计示例如下,以用户为例
> - 查询用户列表： /users
> - 添加用户： /user/add
> - 删除用户： /user/{id}/delete
> - 修改用户：/user/{id}/edit

4. 后期设计其他模块也是如此，以员工为例
> - 查询员工列表： /employees
> - 添加员工： /employee/add
> - 删除员工： /employee/{id}/delete
> - 修改员工：/employee/{id}/edit

#### 后端技术

| 技术                 | 说明                | 官网                                                 |
| -------------------- | ------------------- | ---------------------------------------------------- |
| SpringBoot           | 容器+MVC框架        | https://spring.io/projects/spring-boot               |
| SpringSecurity       | 认证和授权框架      | https://spring.io/projects/spring-security           |
| MyBatis              | ORM框架,用于和数据库交互  | http://www.mybatis.org/mybatis-3/zh/index.html       |
| Swagger-UI           | 文档生成工具         | https://github.com/swagger-api/swagger-ui            |
| Lombok               | 代码生成工具，用于简化代码，提高可读性    | https://github.com/rzwitserloot/lombok  |

#### 前端技术

| 技术       | 说明                  | 官网                                   |
| ---------- | --------------------- | -------------------------------------- |
| Vue        | 前端框架              | https://cn.vuejs.org/                     |
| Vue-router | 路由框架              | https://router.vuejs.org/zh/              |
| Vuex       | 全局状态管理框架      | https://vuex.vuejs.org/zh/               |
| Element-ui    | 前端UI组件框架            | https://element.eleme.cn               |
| Axios      | AJAX请求框架          | https://github.com/axios/axios         |
| v-charts   | 基于Echarts的图表框架 | https://v-charts.js.org/               |

#### TODO

请按重要程度排序

1. Warehouse物品管理部分
2. 页面鉴权
3. `/home`欢迎页



