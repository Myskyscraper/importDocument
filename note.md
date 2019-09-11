1 html 

2 css

3 js
    this function 指向调用者；箭头里指向上下环境



4 浏览器机制


5 工程
    Vue 函数多，methods 和watch为对象
        build文件 
            用于存放 webpack 相关配置和脚本/webpack.base.conf.js 用于配置 less、sass等css预编译库;
        config
            用于区分开发环境、线上环境的不同;
            config.js 配置开发环境的 端口号、是否开启热加载 或者 设置生产环境的静态资源相对路径、是否开启gzip压缩、npm run build 命令打包生成静态资源的名称和路径等。
            index.js 
                    build 对象下 对于 生产环境 的配置：
                    index：配置打包后入口.html文件的名称以及文件夹名称
                    assetsRoot：配置打包后生成的文件名称和路径
                    assetsPublicPath：配置 打包后 .html 引用静态资源的路径，一般要设置成 "./"
                    productionGzip：是否开发 gzip 压缩，以提升加载速度
                    
                    dev 对象下 对于 开发环境 的配置：
                    port：设置端口号
                    autoOpenBrowser：启动工程时，自动打开浏览器
                    proxyTable：vue设置的代理，用以解决 跨域 问题

        src下componets：
            存放vue开发中一些公共组件：header.vue、footer.vue等
        src下emit：
            自己配置的vue集中式事件管理机制。
        src下service：
            自己配置的vue请求后台接口方法。
            (1)与后台连接端口的配置:config，打开 index.js proxytable
            (2)fetch 请求后台接口:vue项目utils 工具包下创建fetch.js 件;
                src 下新建一个 api 文件夹，创建一个 js 文件
        src下util：
            存放vue开发过程中一些公共的.js方法。
        src下store
            index.js
            state：存储状态（变量）
            getters.js:对数据获取之前的再次编译，可以理解为state的计算属性。我们在组件中使用 $sotre.getters.fun()
            mutation.js 修改状态，并且是同步的
            actions.js  异步操作。在组件中使用是$store.dispath('')
        watch 和computed
            watch擅长处理的场景：一个数据影响多个数据 草帽海贼团 纵多成员
            computed擅长处理的场景：一个数据受多个数据影响 名字书写 （存在依赖型数据 2.依赖型数据发生改变这两个条件才改变）
        keep-alive

        fetch.js:是一种xmlhttp的请求方式 返回Promise 类型
        和axios

6 工具


7安全



//-----------

obj遍历  config 和build 防抖和节流 继承问题
vue.js   api那设置  删除当前信息  表格校验 信息编辑 提交  表格校验证那种
哈希：
data设置 
vuex再遍历一遍
fetch.js 和axios的区别
开发环境和生产环境设置
2vuex/api-data happy