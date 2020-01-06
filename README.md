### 目录树如下  
├── demo 目录为对接的一些程序，能用的  
├── AopSdk.php //SDK入口文件   
├── config.php //配置文件   
├── f2fpay //SDK文件    
├── index.html   
├── notify.php  //异步验证文件    
├── pay //支付页面   
│   ├── index.php   
│   ├── qrcode.class.php   
│   └── qrcode.php   
├── pay.php // 创建支付文件   
├── query.php //订单查询页面   
└── static //静态文件页面   
    ├── avatar.jpg   
    ├── erphpdown.css   
    ├── payment-alipay.png   
    └── signin.css   


DEMO: [http://pay.i5.gs](http://pay.i5.gs)

对接程序DEMO
发卡 [http://ka.i5.gs](http://ka.i5.gs)

---

简介: 
通过对支付宝f2fpay SDK的二次开发，实现在线支付功能。

---

更新记录:   
2019.12.25  
修复一个弱智的bug,就是订单金额保留两位小数的问题(pay.php第18行),发现以前写的验证订单有些过于繁琐(能通过支付宝校验的话,就不必验证金额了),不过懒得改了..      
2019.11.12  
写了设置密钥对的教程/工具,给有需要的人   
2019.8.27  
新增一个发卡的DEMO  
2019.8.19 
重构，现在可以`一键切换`是否需要记录订单。(config.php中)   
2019.8.5 
第一次提交

---

使用方法：
1. 修改config.php ，填入你的支付宝公钥/私钥/PID 
2. 根据config.php 提示是否需要订单记录，使用注释中的SQL创建数据表，并修改相关数据库配置。
3. 检查config.php中的 notify_url 确认公网可访问
4. 完成。

---

主要逻辑：
1. 生成订单插入数据库-->显示二维码供用户支付-->支付完成后支付宝异步通知到notify.php-->notify.php对支付宝传来的数据进行校验，改变数据库中订单状态-->query.php返回订单成功状态-->完成支付  
2. 生成订单-->显示二维码-->直接根据支付宝的接口查询订单状态-->成功

--- 

很多人反馈的支付后不能成功回调问题,大部分是没有检查回调地址变量..请检查并`确认可用`后再试, 如果实在调试不出,请打赏(纯自愿,并非买卖.无售后)后发送相关信息到我的邮箱  
另: 可`有偿`提供 对接各种程序 服务，如有需要请联系邮箱 'yumusb艾特foxmail.com'。  
![zanshang](https://ae01.alicdn.com/kf/H512c765e75bf4e01b91f1771ff69a8d2o.png)  

