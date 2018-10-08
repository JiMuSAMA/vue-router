# vue-router
vue-router.js 跳转

<script src="https://cdn.bootcss.com/vue/2.4.0/vue.js"></script>
		<script src="https://cdn.bootcss.com/vue-router/2.4.0/vue-router.js"></script>
    
    	<div id="app">
    <div>
        <!--
            router-link to属性就是指向某个具体的链接，链接的内容会被渲染到router-view标签中
            router-link会被渲染成a标签，例如第一个会变成<a href="#/first">第一个页面</a>,前面加了个#
        -->
        <router-link  to="/first">第1个页面</router-link>
        <router-link  to="/second">第2个页面</router-link>
        <router-link  to="/third">第3个页面</router-link>
    </div>
    <router-view></router-view>
</div>
</body>
<script>
    /*
    * 申明三个模板
    */
    var first = { template: '<p>this is first page</p>' };
    var second = { template: '<p>this is second page</p>' };
    var third = { template: '<p>this is third page</p>' };
    /*
    * 定义路由，component属性是通过 Vue.extend() 创建的组件构造器，或者，只是一个组件配置对象。
    */
    var routes = [
        { path: '/first', component: first },
        { path: '/second', component: second },
        { path: '/third', component: third }
    ];
    /*
    * 创建VueRouter实例
    */
    var router = new VueRouter({
        routes:routes
    });
    /*
    * 给vue对象绑定路由
    * .$mount("#app")手动挂载，用来延迟挂载，跟
    *  const app = new Vue({
    *   el:"#app"
    *   router
    * });
    * 效果是一样的
    */
    const app = new Vue({
        router
    }).$mount("#app");

</script>
