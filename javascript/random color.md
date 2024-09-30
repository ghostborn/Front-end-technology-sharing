> **在JavaScript中生成随机十六进制颜色代码**

```javascript
const randomHexColorCode = () => {
  let n = (Math.random() * 0xfffff * 1000000).toString(16);
  return '#' + n.slice(0, 6);
};

randomHexColorCode(); // '#e34155'
```

