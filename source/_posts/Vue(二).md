---
title: Vue（一）
---

## 一、引入

``` HTML
<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

``` HTML
<!-- 生产环境版本，优化了尺寸和速度 -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

<!--more-->

## 二、入门实例

### 2.1、Hello World!

``` HTML
<!DOCTYPE html>
<html>

  <head>
    <meta charset="utf-8">
    <title>Vue测试实例</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>

  <body>
    <div id="app">
      {{ msg }}
    </div>

    <script>
      var app = new Vue({
        el: '#app',
        data: {
          msg: 'Hello World!'
        }
      })
    </script>
  </body>

</html>
```

> 在Chrome控制台修改app.msg的值，可以发现上例相应更新，说明数据和DOM已经被建立了关联。

### 2.2、指令

#### v-model指令

``` HTML
<!DOCTYPE html>
<html>

  <head>
    <meta charset="utf-8">
    <title>Vue测试实例</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>

  <body>
    <div id="app">
      <input v-model="msg" />
    </div>

    <script>
      var app = new Vue({
        el: '#app',
        data: {
          msg: 'Hello World!'
        }
      })
    </script>
  </body>

</html>
```

> 修改input输入框内的值，可以发现(通过Chrome控制台console.log的方式)msg的值也会发生改变，反过来，修改app.msg的值，也会影响到input输入框的值，轻松实现表单输入和应用状态之间的双向绑定。

#### v-if指令

``` HTML
<!DOCTYPE html>
<html>

  <head>
    <meta charset="utf-8">
    <title>Vue测试实例</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>

  <body>
    <div id="app">
      <p v-if="flag">我是一段消息</p>
    </div>

    <script>
      var app = new Vue({
        el: '#app',
        data: {
          flag: true
        }
      })
    </script>
  </body>

</html>
```

> 在Chrome控制台修改app.flag的值可以控制消息的显示和消失。

#### v-for指令

``` HTML
<!DOCTYPE html>
<html>

  <head>
    <meta charset="utf-8">
    <title>Vue测试实例</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>

  <body>
    <div id="app">
      <ol>
        <li v-for="item in arr">{{ item.text }}</li>
      </ol>
    </div>

    <script>
      var app = new Vue({
        el: '#app',
        data: {
          arr: [
            { text: 'a' },
            { text: 'b' },
            { text: 'c' }
          ]
        }
      })
    </script>
  </body>

</html>
```

> 使用v-for指令绑定数组的数据来渲染一个列表，在Chrome控制台输入app.arr.push({ text: 'new' })，列表也会动态的添加这个新的列表项。

#### v-on指令

``` HTML
<!DOCTYPE html>
<html>

  <head>
    <meta charset="utf-8">
    <title>Vue测试实例</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>

  <body>
    <div id="app">
      <p>{{ msg }}</p>
      <button v-on:click="changeMsg">反转字符串</button>
    </div>

    <script>
      var app = new Vue({
        el: '#app',
        data: {
          msg: 'Hello World!'
        },
        methods: {
          changeMsg: function () {
            this.msg = this.msg.split('').reverse().join('')
          }
        }
      })
    </script>
  </body>

</html>
```

> 使用v-on指令添加事件监听器，调用在Vue实例中定义的方法。

### 2.3、组件

#### 在Vue中注册组件

``` HTML
<!DOCTYPE html>
<html>

  <head>
    <meta charset="utf-8">
    <title>Vue测试实例</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>

  <body>
    <div id="app">
      <comp-test></comp-test>
    </div>

    <script>
      Vue.component('comp-test', {
        template: '<h1>这是一些消息</h1>'
      })

      new Vue({
        el: '#app'
      })
    </script>
  </body>

</html>
```

#### 通过prop特性，将父作用域数据传递到子组件

``` HTML
<!DOCTYPE html>
<html>

  <head>
    <meta charset="utf-8">
    <title>Vue测试实例</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>

  <body>
    <div id="app">
      <ul>
        <comp-test v-for="item in arr" v-bind:msg="item"></comp-test>
      </ul>
    </div>

    <script>
      Vue.component('comp-test', {
        props: ['msg'],
        template: '<li>{{ msg.text }}</li>'
      })

      var app = new Vue({
        el: '#app',
        data: {
          arr: [
            { text: 'a' },
            { text: 'b' },
            { text: 'c' }
          ]
        }
      })
    </script>
  </body>

</html>
```