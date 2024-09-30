> **通用唯一标识符（UUID）是一个128位的数字，用于唯一标识Internet上的某些对象或实体**

在现代浏览器或`Node.js`中使用[Crypto API](https://developer.mozilla.org/zh-CN/docs/Web/API/Web_Crypto_API)来生成UUID 

```javascript
// Browser(JavaScript)
crypto.randomUUID(); // ''93fd6bd4-53e0-4deb-9aab-983c79e61183''

//Node.js(JavaScript)
import { randomUUID } from 'crypto';
randomUUID(); // '7982fcfe-5721-4632-bede-6000885be57d'
```

