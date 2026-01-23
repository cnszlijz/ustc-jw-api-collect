# 登录

登录界面为 <https://jw.ustc.edu.cn/login>. 未登录时返回 HTML 页面，若 cookie 无 `SESSION` 则会设置新的 `SESSION`. 已登录时跳转到[主页](https://jw.ustc.edu.cn/home)

值得一提的是，[网站根目录](https://jw.ustc.edu.cn/) 会无条件跳转[登录界面](https://jw.ustc.edu.cn/login)

## 发起登录

> https://jw.ustc.edu.cn/ucas-sso/login

*请求方式：GET*

**URL 参数：**

|参数名|类型|内容|必要性|
|-----|----|----|-----|
|ticket|str|CAS 令牌|可选|

**响应：** HTTP 302, 成功获取个人信息则跳转 <https://jw.ustc.edu.cn/>，`ticket` 字段为空则跳转 [统一身份认证系统](https://passport.ustc.edu.cn/login)

## 获取 fine_auth_token

> https://jw.ustc.edu.cn/webroot/decision/login/cross/domain

*请求方式：GET*

该请求由 js 自动发起，目的未知

**URL 参数：**

|参数名|类型|内容|
|-----|----|----|
|fine_username|str|学号|
|fine_password|str||
|validity|num|-1|
|callback|str|函数名|
|_|num|timestamp|

**响应：** text/javascript

e.g.

```javascript
jQuery1122334455667788990000_1767196800({
    "accessToken": "一个JWT，和 fine_auth_token 相同",
    "url": "一个网址，内容是将请求 URL 的主体部分更换为 https://jw.ustc.edu.cn/webroot/decision ，Query String 部分不变。打开这个链接是一个标题为数据决策系统的网页",
    "status": "success"
})
```
