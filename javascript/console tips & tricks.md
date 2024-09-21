> ##### 前端需要知道的console命令和技巧

每个人都会每隔一段时间使用 `JavaScript` 控制台进行日志记录或调试。但是 [console](https://developer.mozilla.org/en-US/docs/Web/API/Console) 对象的功能远不止[`console.log()`](https://developer.mozilla.org/en-US/docs/Web/API/console/log)。



[`console.trace()`](https://developer.mozilla.org/en-US/docs/Web/API/Console/trace)工作原理与[`console.log()`](https://developer.mozilla.org/en-US/docs/Web/API/console/log)，但它也会输出整个堆栈跟踪，以便你确切地知道发生了什么。

```javascript
const outer = () => {
    const inner = () => console.trace('Hello');
    inner();
};

outer();
/*
  Hello
  inner @ VM207:3
  outer @ VM207:5
  (anonymous) @ VM228:1
*/
```



[`console.group()`](https://developer.mozilla.org/en-US/docs/Web/API/Console/group)允许您将日志分组到可折叠的结构中，当您有多个日志时，这尤其有用。

```javascript
console.group('Outer');           // Create a group labelled 'Outer'
console.log('Hello');             // Log inside 'Outer'
console.groupCollapsed('Inner');  // Create a group labelled 'Inner', collapsed
console.log('Hellooooo');         // Log inside 'Inner'
console.groupEnd();               // End of current group, 'Inner'
console.groupEnd();               // End of current group, 'Outer'
console.log('Hi');                // Log outside of any groups
```



###### `日志记录级别`

```javascript
console.debug('Debug message');
console.info('Useful information');
console.warn('This is a warning');
console.error('Something went wrong!');
```



[`console.assert()`](https://developer.mozilla.org/en-US/docs/Web/API/console/assert)提供了一种方便的方法，仅在断言失败时（即当第一个参数是）将某些内容记录为错误，否则完全跳过日志

```javascript
const value = 10;

console.assert(value === 10, 'Value is not 10!'); // Nothing is logged
console.assert(value === 20, 'Value is not 20!'); // Logs "Value is not 20!"
```



你可以使用[`console.count()`](https://developer.mozilla.org/en-US/docs/Web/API/Console/count)来计算一段代码已执行的次数。

```javascript
Array.from({ length: 4 }).forEach(
  () => console.count('items')  // Call the counter labelled 'items'
);
/*
  items: 1
  items: 2
  items: 3
  items: 4
*/
console.countReset('items');  // Reset the counter labelled 'items'
```



[`console.time()`](https://developer.mozilla.org/en-US/docs/Web/API/Console/time)为您提供了一种快速检查代码性能的方法，但由于准确性低，因此不应用于真正的基准测试。

```javascript
console.time('loop')
const start = Date.now()
while (Date.now() - start < 2000) {}
console.timeEnd('loop')
```



`console.table()`允许你以表格的形式打印数组或对象的集合。

```javascript
const arr = ['1', '2', '3']
console.table(arr)

const obj = {
    name: '李华',
    age: '18',
    information: '在校学生'
}
console.table(obj)
```

![](https://cdn.jsdelivr.net/gh/ghostborn/Picture/202409181549230.png)



最后，`console.log()` 还支持定义 CSS 的格式

```javascript
console.log(
    'CSS can make %cyour console logs%c %cawesome%c!',  // String to format
    // Each string is the CSS to apply for each consecutive %c
    'color: #fff; background: #1e90ff; padding: 4px',   // Apply styles
    '',                                                 // Clear any styles
    'color: #f00; font-weight: bold',                   // Apply styles
    ''                                                  // Clear any styles
);
```

![](https://cdn.jsdelivr.net/gh/ghostborn/Picture/202409181551755.png)
