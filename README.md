# xm-secondhand
# 校园二手交易平台
## 项目介绍
模仿二手交易平台，写的校园二手交易网站，实现学生校园二手闲置物品的交易。包括用户登录注册，发布商品、发帖、求购、一对一在线聊天、按需搜索反馈等功能。
## 技术栈
### 前端
Vue + Vue Router + ElementUI + Axios 
### 后端
MySQL+Springboot + Mybatis
## 部分页面展示
### 登录
![image](https://github.com/LaoHuSongzi/xm-secondhand/blob/master/xm-secondhand/files/loginPage.png)
### 用户界面
![image](https://github.com/LaoHuSongzi/xm-secondhand/blob/master/xm-secondhand/files/frontEndhome.png)
### 商品详情
![image](https://github.com/LaoHuSongzi/xm-secondhand/blob/master/xm-secondhand/files/Buy.png)
### 沙箱支付
![image](https://github.com/LaoHuSongzi/xm-secondhand/blob/master/xm-secondhand/files/shaxiang.png)
### 私聊
![image](https://github.com/LaoHuSongzi/xm-secondhand/blob/master/xm-secondhand/files/chat.png)
### 管理员界面
![image](https://github.com/LaoHuSongzi/xm-secondhand/blob/master/xm-secondhand/files/backEndhome.png)
### 管理列表
![image](https://github.com/LaoHuSongzi/xm-secondhand/blob/master/xm-secondhand/files/backEnd.png)
## 项目亮点
使用Echarts实时多维度统计销售数据  
采用了WebSocket实现在线聊天室，确保在线聊天室的连接稳定性和可靠性  
使用沙箱环境配合natapp隧道，模拟支付宝线上真实支付场景  
为提升性能，使用骨架屏、图片懒加载、路由懒加载替代数据从请求到展示的空白期,提高用户的使用体验   
