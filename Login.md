# <center>登录页API</center>
## 账号登录
- Url: /account/comomLogin
- Post: {name: 'xxxxx', pwd: 'xxxxx'}

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| name | string | 手机号或账号 |
| pwd | string | 密码 |
- Header: 无
- Response: { token: 'xxxx', userId: "xxxx", userName: "xxxxx" }

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| token | string | 登录成功后的token |
| userId | string | 用户Id |
| userName | string | 用户名 |

## 发送短信
- Url: /account/sendSMS/{mobile}

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| mobile | string | 手机号 |

- Get
- Header: 无
- Response: 无

## 短信登录
- Url: /account/smsLogin
- Post: {mobile: 'xxxxx', code: 'xxxxx'}
  
| 参数 | 类型 | 说明 |
| --- | --- | --- |
| mobile | string | 手机号 |
| code | string | 短信里的号码 |
- Header: 无
- Response: { token: 'xxxx', userId: "xxxx", userName: "xxxxx" }

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| token | string | 登录成功后的token |
| userId | string | 用户Id |
| userName | string | 用户名 |