> **检查是否启用了`localStorage`或`sessionStorage`**

废话不多说，直接上代码，请看：

```javascript
const isLocalStorageEnabled = () => {
  try {
    const key = `__storage__test`;
    window.localStorage.setItem(key, null);
    window.localStorage.removeItem(key);
    return true;
  } catch (e) {
    return false
  }
};

isLocalStorageEnabled();  // true, if localStorage is accessible
```

```javascript
const isSessionStorageEnabled = () => {
  try {
    const key = `__storage__test`;
    window.sessionStorage.setItem(key, null);
    window.sessionStorage.removeItem(key);
    return true;
  } catch (e) {
    return false;
  }
};

isSessionStorageEnabled(); // true, if sessionStorage is accessible
```

