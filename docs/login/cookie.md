# cookie

|字段|必要性|内容|格式|备注|
|----|-----|----|----|---|
|SESSION|必要|标记身份|uuid|/login 和 /logout 界面在字段为空时通常会设置一个|
|SRVNAME|必要|未知|student%d|各种地方都必须且不能出错，但是生成规律未知|
|fine_auth_token|可选|未知|JWT|JWT中记录了学号<br />似乎用于一些数据统计后台，正常操作不会检查|
|fine_remember_login|可选|通常为-1|num||
