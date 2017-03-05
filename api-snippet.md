## 创建 Snippet

### 请求语法



```json
// POST /v1/snippet/
// Content-Type: application/json
// Authorization: codevs <auth_token>   #关于auth_token的相关信息，请查阅文档[鉴权]章节
{
  "language": <Language>,
  "version": <Version>,
  "code": <Code>,
  "timeLimit": <TimeLimit>,
  "memoryLimit": <MemoryLimit>
}
```

### 请求内容



| 参数          | 类型     | 必填   | 说明                  |
| :---------- | :----- | :--- | :------------------ |
| language    | string | 是    | 代码所属语言              |
| version     | string | 是    | 编译器版本               |
| code        | string | 是    | 待运行的代码              |
| timeLimit   | string | 否    | 最大运行时间（默认为 "300ms") |
| memoryLimit | string | 否    | 最大可用内存 （默认 128mb )  |

1. 普通用户的 timeLimit 可设置范围为 0 - 1000ms，普通用户的 memoryLimit的内存可设置范围为 0 - 400mb
2. timeLimit 和 memoryLimit 支持 human size，例如 "0.3s","300ms","100mb","10240kb"

### 请求返回

```
{
  "fetchUrl": <fetchUrl>,
  "uid": <uid>
}
```

| 参数       | 类型     | 说明             |
| :------- | :----- | :------------- |
| fetchUrl | string | 查询该代码的运行结果的url |
| uid      | string | 本次代码运行的 uid    |

## 查询 snippet 运行结果

### 请求语法

```json
// GET /v1/snippet/<uid>
// Content-Type: application/json
// Authorization: codevs <auth_token>   #关于auth_token的相关信息，请查阅文档[鉴权]章节
```

## 请求内容

该 api 无需请求内容

### 请求返回 (WIP)

?> 正在施工中

!> 下一版将会添加该部分

# 