> **命名导出**

```javascript
// environment.js
export const key = 'this-is-a-secret';

// index.js
import {key} from 'environment';
```

- 一个模块可以有任意数量的命名导出
- 导入和导出名称应相同
- 导入需要 {}



> **默认导出**

```javascript
// environment.js
const environment = {
    key: 'this-is-a-secret',
    port: 8000
};
export default environment;

// index.js
import environment from 'environment';
const {key, port} = environment;
```

- 默认导出使用关键字 `default`
- 一个模块只能有一个默认导出
- 导入名称可以是任何内容
- 导入不需要 {}



> **默认+命名**

```javascript
// environment.js
export const envType = 'DEV';
const environment = {
    key: 'this-is-a-secret',
    port: 8000
};
export default environment;

// index.js
import { envType }, environment from 'environment';
const { key, port } = environment;
```

- 默认导出和命名导出可以混合使用



> **导出列表**

```javascript
// environment.js
const key = 'this-is-a-secret';
const port = 8000;
export {
	key,
    port
};

// index.js
import { key, port } from 'environment';
```

- 导出列表是编写多个命名导出的紧凑方法
- 导出列表不是对象



> **重命名导出**

```javascript
// environment.js
const key = 'this-is-a-secret';
export { key as authKey };

// index.js
import { authKey } from 'environment';
```



> **重命名导入**

```javascript
// environment.js
export const key = 'this-is-a-secret';

// index.js
import { key as authKey } from 'environment';
```



> **全部导入**

```javascript
// environment.js
export const envType = 'DEV';
const environment = {
    key: 'this-is-a-secret',
    port: 8000
};
export default environment;

// index.js
import * as env from 'environment';
const {default: { key, port }, envType } = environment;
```

