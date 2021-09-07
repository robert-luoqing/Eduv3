# <center>主页的API</center>
## 获取Home页显示的配置信息
- Url: /home/setting
- Post: 无
- Header: edutoken或无
- Response: 
```typescript
{
  homeMenus: [{ tabName: string, iconType: "icon" | "assetImage" | "webImage", iconUrlOrName: string, isOpenSystemModule: boolean, urlOrModuleName: string }],
  tabs: [{ tabName: string, iconType: "icon" | "assetImage" | "webImage", iconUrlOrName: string, isOpenSystemModule: boolean, urlOrModuleName: string, isDefault: boolean }],
}

```
| 参数 | 类型 | 说明 |
| --- | --- | --- |
| tabName | string | 显示的名称 |
| iconType | "icon","assetImage","webImage"中的一个 | 图标的类型 |
| iconUrlOrName | string | 图标的地址，如果iconType为webImage,则传入的是图标的web地址 |
| isOpenSystemModule | boolean | 是否打开一个系统约定的页面，如果为false，则打开一个页面 |
| urlOrModuleName | string | 如果isOpenSystemModule为true, 则该内容为约定的名字，如: "home", "settig"等，如果为false,则要传入一个url地址 |

## 获取当前登录的用户信息
- Url: /account/myUserInfo
- Post: 无
- Header: edutoken
- Response: 
```typescript
{
   userId: string,
   mobile: string,
   avatar: string,
   userName: stirng,
   preferSubjectId: string,
   preferSubjectName: string,
   messageCount: number,
}

```
## 获取当前用户（无用户）的直播
- Url: /account/homeLives
- Post: 无
- Header: edutoken
  edutoken可能为空，为空时，表示该用户没有登录
- Response: 
```typescript
[{
  liveId: string,
  startLiveDateTime: number,
  endLiveDateTime: number,
  title: string,
  teachName: string,
  teachAvatar: string,
  teachIntroduce: string,
  appointmentCount: number,
}]
```
## 获取当前用户(无用户）的学习课程
- Url: /account/courses
- Post: 无
- Header: edutoken
  edutoken可能为空，为空时，表示该用户没有登录
- Response: 
```typescript
[{
  courseId: string,
  courseCover: string,
  courseName: stirng,
  courseDesc: string,
  price: number,
  needShowPrice: boolean,
}]
```

