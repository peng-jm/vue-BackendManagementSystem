<template>
    <div id="hello">
        <div id='leftMenu' class="menuLeft" v-bind:style="{'right':isCollapse?'96.2%':'91%'}">
            <el-menu
                    default-active="2"
                    class="el-menu-vertical-demo"
                    @open="handleOpen" @close="handleClose"
                    text-color=" rgba(255, 255, 255, 0.65)"
                    background-color="rgb(0,21,41)"
                    :collapse="isCollapse">
                <div class='headerLogo'>
                    <img src=".././assets/logo.png"/>
                    <span slot="title" v-show="!isCollapse">数仓平台</span>
                </div>
                <el-submenu index="1">
                    <template slot="title">
                        <i class="el-icon-location"></i>
                        <span slot="title">数仓管理</span>
                    </template>
                    <el-menu-item index="1-1">主题域管理</el-menu-item>
                    <el-menu-item index="1-2">数仓配置</el-menu-item>
                </el-submenu>
                <el-menu-item index="2">
                    <i class="el-icon-menu"></i>
                    <span slot="title">数据源管理</span>
                </el-menu-item>
                <el-menu-item index="3">
                    <i class="el-icon-setting"></i>
                    <span slot="title">元数据管理</span>
                </el-menu-item>
            </el-menu>
        </div>
        <div id='headerTitle' class="header" v-bind:style="{'left':isCollapse?'4%':'10%',display:'flex'}">
            <i class="el-icon-s-fold" v-if="isCollapse" @click="clickMenuShow"></i>
            <i class="el-icon-s-unfold" @click="clickMenuShow" v-else></i>
            <h3>深圳航天工业技术研究院</h3>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        data() {
            return {
                isCollapse: true
            };
        },
        methods: {
            handleOpen(key, keyPath) {
                console.log(key, keyPath);
            },
            handleClose(key, keyPath) {
                console.log(key, keyPath);
            },
            clickMenuShow() {
                this._data.isCollapse = !this._data.isCollapse
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="less">
    .el-menu--vertical {

        .el-menu-item.is-active {
            color: white !important;
            background: #1890FF !important;
        }

        .el-menu-item:hover {
            background-color: transparent !important;
            color: white !important;
        }

        .el-submenu__title:hover {
            background-color: transparent !important;
            color: white !important;
        }

        .el-submenu.is-active{
            color: white !important;
            background: #1890FF !important;
        }
    }

    #hello {
        width: 100%;
        height: 100%;

        .menuLeft {
            position: fixed;
            top: 0;
            left: 0;
            bottom: 0;

            .el-menu {
                box-shadow: 2px 0 6px rgba(0, 21, 41, 0.35);
                .el-submenu__title:hover {
                    background-color: transparent !important;
                    color: white !important;
                }
            }

            .el-menu-vertical-demo:not(.el-menu--collapse) {
                width: 150px;
                height: 100%;
                box-shadow: 2px 0 6px rgba(0, 21, 41, 0.35);
            }

            .el-menu--collapse {
                height: 100%;
            }

            .headerLogo {
                background: #002140 !important;
                width: 100%;
                height: 50px;
                line-height: 50px;

                > img {
                    display: inline-block;
                    height: 32px;
                    vertical-align: middle;
                    margin-left: 20px;
                }

                > span {
                    margin-left: 10px;
                    color: white;
                    font-size: 18px;
                    font-weight: 600;
                }

            }

            .el-submenu {
                margin-top: 5px;

                .el-menu-item {
                    min-width: 0;
                }

                .el-menu-item:hover {
                    background-color: transparent !important;
                    color: white !important;
                }

                .el-menu-item.is-active {
                    background-color: #1890FF !important;
                    color: white !important;
                }

            }

        }

        .el-menu-item:hover {
            background-color: transparent !important;
            color: white !important;
        }

        .el-submenu__title:hover {
            background-color: transparent !important;
            color: white !important;
        }

        .el-submenu:hover {
            background-color: transparent !important;
            color: white !important;
        }

        .el-menu-item.is-active {
            background-color: #1890FF !important;
            color: white !important;
        }

        .header {
            position: fixed;
            top: 0;
            right: 0;
            height: 60px;
            display: flex;
            align-items: center;
            box-shadow: 0 1px 4px rgba(0, 21, 41, 0.08);

            i {
                width: 3%;
                text-align: center;
                font-size: 24px;
                cursor:pointer;
            }

        }
    }

</style>
