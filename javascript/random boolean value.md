> **在JavaScript中生成随机布尔值**

`Math.random()`生成一个介于0和1之间的随机数，其结果大于或等于0.5的概率为50%，分布均匀。

```javascript
const randomBoolean = () => Math.random() >= 0.5;
randomBoolean();
```

