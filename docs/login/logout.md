# 登出

## 用户界面登出

> https://jw.ustc.edu.cn/logout-emitter

*请求方式：GET*

**url参数：** 无

**响应：** HTTP 302, 通常指向 [/logout](https://jw.ustc.edu.cn/logout)

## 登出

> https://jw.ustc.edu.cn/logout

**URL 参数：**

|参数名|类型|内容|
|-----|----|----|
|service|str|下一步跳转的 URL|

**响应：** HTTP 302, 指向 service 字段的内容，通常是 <https://passport.ustc.edu.cn/logout?service=https://jw.ustc.edu.cn/logout>。字段为空时会跳转到 [/login?refer=https://jw.ustc.edu.cn/logout](https://jw.ustc.edu.cn/login?refer=https://jw.ustc.edu.cn/logout)

若 cookie 中没有 `SESSION` 字段则会会设置 `SESSION`

退出成功会清除 cookie 中的 `SESSION` 字段和 `SRVNAME` 字段，并设置 `rememberMe=deleteMe`