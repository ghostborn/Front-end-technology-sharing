> **圆和椭圆**

```html
<div class="circle"></div>
<div class="ellipse"></div>
```

```css
.circle {
  width: 64px;
  height: 64px;
  border-radius: 50%;
  background: #5394fd;
}

.ellipse {
  width: 128px;		// 宽高不相等
  height: 64px;
  border-radius: 64px / 32px;	// border-radius: x/y， x表示圆角的水平半径，y表示圆角的垂直半径
  background: #5394fd;
}
```



> **三角形**

```html
<div class="triangle-down"></div>
<div class="triangle-up"></div>
<div class="triangle-left"></div>
<div class="triangle-right"></div>
```

```css
.triangle-down {
    width: 0;
    height: 0;
    border-top: 32px solid #5394fd;
    border-left: 32px solid transparent;
    border-right: 32px solid transparent;
}

.triangle-up {
    width: 0;
    height: 0;
    border-bottom: 32px solid #5394fd;
    border-left: 32px solid transparent;
    border-right: 32px solid transparent;
}

.triangle-left {
    width: 0;
    height: 0;
    border-right: 32px solid #5394fd;
    border-top: 32px solid transparent;
    border-bottom: 32px solid transparent;
}

.triangle-right {
    width: 0;
    height: 0;
    border-left: 32px solid #5394fd;
    border-top: 32px solid transparent;
    border-bottom: 32px solid transparent;
}
```

