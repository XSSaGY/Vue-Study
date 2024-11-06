# Vue学习的第一天
- 首先看代码
```javascript
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
<div id="int">{{ message }} {{ code }}</div>
<script>
  const { createApp, ref } = Vue
  var app = {
    setup() {
      const message = ref('Hello vue!')
      const code = ref('This is a code snippet.')
      return {
        message,
        code
      }
    }
  }
  createApp(app).mount('#int')
</script>
```
- 可以看到Vue是类似html式的脚本语言，我个人把Vue框架看作是一个库，里面提供一些方法。
- 下面逐行进行解释
```javascript
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
```
- 引入Vue的全局版本,https://unpkg.com/vue@3/dist/vue.global.js网址是Vue框架的所在地
```javascript
<div id="int">{{ message }} {{ code }}</div>
```
- 定义一个div标签，里面有两个变量{{ message }}和{{ code }}，这两个变量将在后面通过Vue的模板语法进行渲染,{{ }}这两个大括号是Vue的模板语法，用来渲染变量的值，内部的变量名可以改变。
```javascript
<script>
  const { createApp, ref } = Vue
  var app = {
    setup() {
      const message = ref('Hello vue!')
      const code = ref('This is a code snippet.')
      return {
        message,
        code
      }
    }
  }
  createApp(app).mount('#int')
</script>
```
- 定义一个Vue应用，里面有一个setup方法，这个方法返回一个对象，这个对象有两个变量message和code，这两个变量是通过ref方法创建的，ref方法可以创建一个响应式的变量，当变量的值发生变化时，依赖这个变量的视图也会自动更新。
- createApp和ref方法都是从Vue的全局对象中引入的，Var app = {}是Vue的应用对象，后面的第一个大括号是没有类名的类，内部的setup()函数是这个匿名类的方法，当系统调用createApp后会自动找到这个类中的setup()方法，然后执行。
- 最后的mount('#int')方法是将Vue应用挂载到div标签上，这里的#int是div的id属性。
- '#'是Vue的特殊字符，用来表示id属性，后面的'int'是div的id属性值。
- '.'也是Vue的特殊字符，用来表示类名，后面的'mount'是Vue的挂载方法，mount()方法可以将Vue应用挂载到指定元素上。
- 至此，Vue的第一个应用就完成了，可以看到div标签中的内容是Hello vue! This is a code snippet.