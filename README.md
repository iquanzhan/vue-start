# vue-start
## 项目初始化

#### 1.初始化项目

```
npm init -y
```

#### 2.安装vue

```
npm install vue --save
```

#### 3.创建Vue模版

```
<div id="app">
        <h2>hello,{{name}}</h2>
    </div>
    <script src="./node_modules/vue/dist/vue.js"></script>
    <script>
        var app = new Vue({
            el: '#app',
            data: {
                name: '小明'
            }
        });
    </script>
```

 

## Vue基本特性

#### 1.数据和方法的定义

```js
 var doubleApp = new Vue({
            el: '#doubleApp',
            data: {
                number: 0
            },
            methods: {
                add:function(){
                    this.number++;
                }    
            }
        })
```
使用：
```
<input type="number" v-model="number" />
<button  v-on:click="add">+</button>
```

#### 2.生命周期函数

```
var app = new Vue({
            el: '#app',
            data: {
                hello: '你好'
            },
            methods: {},
            beforeCreate() {
                console.log("beforeCreate");
            },
            created() {
                //实例创建后的函数
                console.log("created");
                console.log(this);
            },
            beforeMount() {
                console.log("beforeMount");
            },
            mounted() {
                console.log("mounted");
            },
            beforeUpdate() {
                console.log("beforeUpdate");
            },
            updated() {
                console.log("updated");
            },
            beforeDestroy() {
                console.log("beforeDestroy");
            },
            destroyed() {
                console.log("destroyed");
            }
        });
```

#### 3.差值闪烁

```
<span v-text="text"></span>
<span v-html="html"></span>

//其中text、html为model数据
```

#### 4.v-on基本用法

```
<button v-on:click="add">+</button>
<button v-on:click="decrement">-</button>
```

```
 var app = new Vue({
            el: '#app',
            data: {
                number: 0
            },
            methods: {
                add() {
                    this.number++;
                },
                decrement() {
                    this.number--;
                }
            }
        });
```

v-on:click='add'`可以简写为`@click='add'`

#### 5.事件修饰符、按键修饰符

##### 5.1 事件修饰符

```
<button @click.once="add">+</button>
```

##### 5.2 按键修饰符

```
<input @keyup.enter="add" />
```

全部的按键别名：

- `.enter`
- `.tab`
- `.delete` (捕获“删除”和“退格”键)
- `.esc`
- `.space`
- `.up`
- `.down`
- `.left`
- `.right

##### 5.3 组合按钮

可以用如下修饰符来实现仅在按下相应按键时才触发鼠标或键盘事件的监听器。

- `.ctrl`
- `.alt`
- `.shift`

```html

<!-- Ctrl + Click -->
<div @click.ctrl="doSomething">Do something</div>
```

#### 6.v-for

##### 6.1 基本用法

```
<ul>
    <li v-for="user in users">
    	{{user.id}} - {{user.name}}
    </li>
</ul>
```

##### 6.2 index索引

```
<li v-for="(user,index) in users">
	{{index}} - {{user.id}} - {{user.name}}
</li>
```

##### 6.3 遍历对象

```
v-for="(value,key,index) in object"
```

