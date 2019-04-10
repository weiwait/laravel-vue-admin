<template>
    <div id="app">
        <left-menu></left-menu>
        <top-menu id="header"></top-menu>
        <div id="router-view">
            <router-view></router-view>
            <!--<component v-bind:is="currentComponent"></component>-->
        </div>
    </div>
</template>

<!--<template>-->
<!--<el-container id="app">-->
<!--<el-header></el-header>-->
<!--<el-aside></el-aside>-->
<!--<router-view class=".el-main"></router-view>-->
<!--</el-container>-->
<!--</template>-->

<script>
    import LeftMenu from "./components/LeftMenu/LeftMenu";
    import TopMenu from "./components/TopMenu/TopMenu";
    import Home from "./views/Home";
    import About from"./views/About";

    export default {
        data() {
            return {
                currentComponent: Home
            }
        },
        components: {
            'left-menu': LeftMenu,
            'top-menu': TopMenu,
            'home': Home,
            'about': About
        },
        mounted() {
            let clientHeight = document.documentElement.clientHeight || document.body.clientHeight;
            let clientWidth = document.documentElement.clientWidth || document.body.clientWidth;
            let header = document.getElementById('header');
            let left = parseFloat(window.getComputedStyle(header).left);
            let routerView = document.getElementById('router-view');
            header.style.width = (clientWidth - left) + 'px';
            routerView.style.width = (clientWidth - left) + 'px';

            window.onresize = () => {
                header.style.width = (clientWidth - left) + 'px';
                routerView.style.width = (clientWidth - left) + 'px';
            }
        }
    }
</script>

<style lang="stylus">
    #app
        font-family 'Avenir', Helvetica, Arial, sans-serif
        -webkit-font-smoothing antialiased
        -moz-osx-font-smoothing grayscale
        text-align center
        color #2c3e50
        width 100%
        height 100%

    .el-aside
        background-color black
        height 100%
        width 180px

    .el-header
        background-color black
        padding 0


    #router-view
        position fixed
        top 50px
        left 180px
        width 100%
        height 100px


    #nav
        padding 30px

        a
            font-weight bold
            color #2c3e50

            &.router-link-exact-active
                color #42b983
</style>
