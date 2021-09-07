# <center>API约定</center>
## Token的传入 
所有的API在请求时都有可能传入token（有些API不需要，如login类的函数), 如果有token传入, 则表示调用该API的用户有登录或以前登录过。  
token值被放在http的头的"edutoken"中
## API返回值错误值约定
如果在调用API中，如果有错误出现，则要求返回的对象中有以下字段
```
{
  errorCode: string | number,
  errorMessage: string,
}

如: commonLogin中
{
  errorCode: "1234",
  errorMessage: "用户名或密码错误"
}
```
如果正常的返回数据，则可以无返回errorCode和errorMessage，当用户返回errorMessage, 如果没有特殊约定，则客户端会直接把errorMessage显示给最约用户。

## Http StatusCode的约定
除了网络异常（404）及后端服务器崩溃（400）后，其他都有status: 200返回，包括正常的错误返回

## 403, 401的约定
如果有些API需要只有登录的用户才可以访问，而这些API并没有传入token，或传入token失效，则返回
```
{
  errorCode: "401",
  errorMessage: "你没有登录，无法访问"
}
{
  errorCode: "403",
  errorMessage: "无权限访问"
}
```
## 时间格式约定
所以的时间格式统一返回timestamp, 也就是说时间戳， 数字类型
