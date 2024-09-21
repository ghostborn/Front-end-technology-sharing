> **函数式编程中的不变性的简单讨论**

在传统编程中，数据通常是可变的，这意味着它在创建后可以随意操作和更改。eg:

```javascript
let arr = [1, 2, 3];
arr.push(4);	// `arr` is now [1, 2, 3, 4]
```



然而在函数式编程中，数据被视为不可变，这意味着一旦创建就无法更改。不是修改数据，而是基于旧数据创建新数据。
这有助于防止意外后果，并更容易推断程序。

```javascript
const arr = [1, 2, 3];
const newArr = [...arr, 4];		// `newArr` is [1, 2, 3, 4], `arr` is still [1, 2, 3]
```

如上例子所示，原始数组未被修改。相反，将基于旧数组创建新数组，原始数组仍然可用，如果需要，可以在程序中的其他位置使用。



> **函数式编程常用的使用场景**

1. **高阶函数**

​      指的是可以接受函数作为参数或者返回一个新函数的函数，常用的有`map`、`reduce`、`filter`

2. **纯函数**

​      指的是对于相同的输入，总是返回相同的输出，而且没有任何副作用的函数。

3. **柯里化（currying）**

​      通过把接收多个参数的函数转化为接收一个参数并返回新函数的形式，来简化函数的使用。实现柯里化需要用到闭包和递归技术


















