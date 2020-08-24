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