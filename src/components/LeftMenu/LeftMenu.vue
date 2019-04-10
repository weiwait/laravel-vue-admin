<template>
    <div ref="leftMenu" class="LeftMenu">

        <div id="portrait">
            <div id="lp-img">
                <img src="../../assets/logo.png" alt="">
            </div>
        </div>

        <router-link to="/edit-model">Edit</router-link>

        <div id="left-el-menu">
            <el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose">
                <el-submenu index="1">
                    <template slot="title">
                        <i class="el-icon-location"></i>
                        <span slot="title">导航一</span>
                    </template>
                    <el-menu-item-group>
                        <span slot="title">分组一</span>
                        <el-menu-item index="1-1">选项1</el-menu-item>
                        <el-menu-item index="1-2">选项2</el-menu-item>
                    </el-menu-item-group>
                    <el-menu-item-group title="分组2">
                        <el-menu-item index="1-3">选项3</el-menu-item>
                    </el-menu-item-group>
                    <el-submenu index="1-4">
                        <span slot="title">选项4</span>
                        <el-menu-item index="1-4-1">选项1</el-menu-item>
                    </el-submenu>
                </el-submenu>
            </el-menu>

        </div>

    </div>
</template>

<script>
    export default {
        name: 'LeftMenu',
        props: {
        },
        data() {
            return {
            };
        },
        methods: {
            handleOpen(key, keyPath) {
                console.log(key, keyPath);
            },
            handleClose(key, keyPath) {
                console.log(key, keyPath);
            }
        }
    };
</script>

<style scoped lang="stylus">
.LeftMenu
    position fixed
    left 0
    top 0
    width 180px
    height 100%
    background-color #cccccc
    #portrait
        #lp-img
            width 80px
            height 80px
            margin 30px auto
            border-radius 50%
            overflow hidden
            img
                width 100%

</style>
