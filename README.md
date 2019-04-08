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

