## 📦 如何使用
```
// 移动端
@import './_mixin';
@import './_resetMobile';

// PC端
@import './_mixin';
@import './_resetPc';

// 你可能需要设置一下你的主色调
body {
  color: #333;
}
```

## 🔨字体图标
`iconfont` 默认的使用方式有点冗余，建议这么使用

```
// 当字体图标不固定时,这么写方便替换 【Unicode】
<span class="icon-del">&#xe60b;</span>

.icon-del {
    @include iconfont;
    color: #999;
}

// 当字体图标固定时，这么写html结构清晰
.icon-del {
    font-size: .24rpx;
    color: #999;

    &:before {
        @include iconfont;
        content: "\e628"; // 打开浏览器 审查元素  【Font class】
    }
}
```

## 🔨文字溢出
```
@include textEllipsis($type: 'multipleRows', $row: 1) // 多行溢出
@include textEllipsis($type: 'singleRow', $maxLength: 100%) // 单行溢出

// 示范
.title {
    @include textEllipsis($type: 'multipleRows', $row: 1) // 多行溢出
}
```

## 🔨1px 边框线
```
// 使用after元素绘制下边框线
@include thinLine($useBefore: false, $position: 'bottom', $backgroundColor: #eee, $right: .3rem, $bottom: 0, $left: .3rem);

// 使用before元素绘制上边框线
@include thinLine($useBefore: true, $position: 'top', $backgroundColor: #eee, $right: .3rem, $top: 0, $left: .3rem);
```

```
module.exports = {
    publicPath: '/',
    css: {
        loaderOptions: {
            scss: {
                prependData: `@import "你的路径/_mixin.scss";`
            }
        }
    }
};

```
