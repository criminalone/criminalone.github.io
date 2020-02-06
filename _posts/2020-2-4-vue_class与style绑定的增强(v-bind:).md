在将 v-bind 用于 class 和 style 时，Vue.js 做了专门的增强。可传入的类型除了*字符串*之外，还可以是*对象*或*数组*。

---
---

## class

* **对象**（用于有数据绑定的 class，boolean值决定是否应用此class）:

1. 可以在标签中v-bind:class="{类名：在vue的data中绑定的**布尔值**的数据名}"
2. 也可以"{"data中绑定的对象名"}"
3. 也可以"{"计算属性中绑定的函数名，数据被return成一个对象返回"}"

* **数组**：

1. v-bind:class="[data中绑定的数据名1 值为字符串, data中绑定的数据名2]"
2. 可以用三元表达式，v-bind:class="[isActive ? activeClass : '']"
3. 当有多个条件 class 时这样写有些繁琐。所以在数组语法中也可以使用对象语法：v-bind:class="[{ activ类名: 在vue的data中绑定的**布尔值**的数据名 }, ata中绑定的数据名 值为字符串]"

---

## style

* **对象**:

1. v-bind:style="{ 属性名: data中对应值的名字}"
2. 直接绑定到一个样式对象： v-bind:style="data中对应样式对象的名字"
3. 利用计算属性返回对象

* **数组**:

1. 可以将多个样式对象应用到同一个元素上：v-bind:style="[样式对象1, 样式对象2]"
2. 可以为 style 绑定中的属性提供一个包含多个值的数组，常用于提供多个带前缀的值，例如：

```javaScript
<div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }"></div>
```

这样写只会渲染数组中最后一个被浏览器支持的值。在本例中，如果浏览器支持不带浏览器前缀的 flexbox，那么就只会渲染 display: flex。
