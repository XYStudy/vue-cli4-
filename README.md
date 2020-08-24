** 
* vue-cli4搭建项目
** 
注意：添加node_modules包时，一定要使用yarn,使用npm 经常会报错安装失败
1.vue create + 项目名
2.yarn add element-ui
3.yarn add axios
4.yarn add vuex-class
5.新增vue.config.js
键入module.exports = {
    lintOnSave: false, //eslint不作校验
    publicPath:""
}
6.proxy设置代理
module.exports = {
    lintOnSave: false, //eslint不作校验
    publicPath:""

    主要是对proxy的设置
    proxy: {
        '/api': {
            target: 'http://sso-frontend-service.dev.svc.cluster.local:18201',
            changeOrigin: true,
            ws: true,
            pathRewrite: {
                '^/api': ''
            }
        },
        '/api1': {
            target: 'http://frontend-service.dev.svc.cluster.local:18101',
            changeOrigin: true,
            ws: true,
            pathRewrite: {
                '^/api1': ''
            }
        }
    }
}
设置了proxy后，在配置请求地址的地方，将地址改成api 变量即可