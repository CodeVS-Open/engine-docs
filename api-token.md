# 鉴权

## 制作签名

### 什么是签名

签名是 codevs 用来识别用户身份与权限的凭证，我们采用

- AK/SK(公钥/私钥) [需要工单申请开通该功能]
- token

两种方式来对用户进行身份验证。

!> 目前仅开放 token 方式，如您需要更安全的 AK/SK 请mailto wph95@codevs.cn



#### 设计目的

- 对用户身份进行认证，使服务端获知该请求的发送者。
- 防止身份假冒。
- token分发，使用户可以在自己的应用服务器和app之间分发token，达到保护AK/SK的目的。

### 创建token

请在 engine.codevs.com/admin 界面中创建 token

### 签名用法示例

在需要鉴权的请求，添加 Header "**Authorization**", 值为 codevs < token > 

```json
POST /<your_request_path>
Content-Type: application/json
Authorization: codevs <auth>
```

!> 注意，codevs 和 < token > 存在一个空格



# 错误码 [WIP]