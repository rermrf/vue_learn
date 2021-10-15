#### 第一个vue程序

```vue
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>

    <!-- mvvm中 vm：v表示：前端显示层，m表示：前端数据模型如vm -->

    <!-- v -->
    <div id="app">
        <div>{{message}}</div>
    </div>

    <script src="js/vue2.6.14.js"></script>
    <script>
        // m
        const vm = new Vue({
            el: '#app',
            data:{
                message: 'hello'
            }
        });
    </script>

</body>
</html>
```



## 指令

指令以v-开头

#### 1. vue-bind

1.v-if绑定div/span的title鼠标悬浮信息:

```vue
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>

    <div id="app">
        <div v-bind:title="message">鼠标停留几秒</div>
        <!-- 等同与<div title="hello">鼠标停留几秒</div>，不过数据不是写死的，而是通过M获取的值 -->
    </div>

    <script src="js/vue2.6.14.js"></script>
    <script>

        const vm = new Vue({
            el: '#app',
            data:{
                message: 'hello'
            }
        });

    </script>

</body>
</html>
```



2.v-if判断

```vue
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>

    <div id="app">
        <div v-if="ok">Yes</div>
        <div v-else="ok">No</div>
    </div>

    <script src="js/vue2.6.14.js"></script>
    <script>

        const vm = new Vue({
            el: '#app',
            data:{
                ok: true
            }
        });

    </script>

</body>
</html>
```

if(ok = true)	显示Yes 	else	显示No



if	else	else if

```vue
<div id="app">
        <div v-if="evaluate=== 'A' ">A</div>
        <div v-else-if="evaluate=== 'B' ">B</div>
        <div v-else>C</div>
</div>

<script src="js/vue2.6.14.js"></script>
<script>

        const vm = new Vue({
            el: '#app',
            data:{
                evaluate: 'A'
            }
        });

</script>
```





3.v-for循环

```vue
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>

    <div id="app">
        <div v-for="item in items">{{item.message}}</div>
        <!-- 获取下标 -->
        <!--<div v-for="(item,index) in items">{{item.message}}--{{index}}</div>-->
    </div>

    <script src="js/vue2.6.14.js"></script>
    <script>

        const vm = new Vue({
            el: '#app',
            data:{
                items: [
                    {message: 'java'},
                    {message: 'javascript'},
                    {message: 'html'}
                ]
            }
        });

    </script>

</body>
</html>
```

可通过控制台新增元素vm.items.push({message: 'vue'})