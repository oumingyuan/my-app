<template>


    <div id="app">

        <el-header style="text-align: right; font-size: 20px">
            <el-dropdown>
                <i class="el-icon-setting" style="margin-right: 15px"></i>
                <el-dropdown-menu slot="dropdown">
                    <el-dropdown-item>查看</el-dropdown-item>
                    <el-dropdown-item>新增</el-dropdown-item>
                    <el-dropdown-item>删除</el-dropdown-item>
                </el-dropdown-menu>
            </el-dropdown>
            <span>王小虎</span>
        </el-header>

        <el-container style="height: 1500px; border: 1px solid #eee">


            <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
                <el-menu :default-openeds="['1', '3']">
                    <el-submenu index="1">
                        <template slot="title"><i class="el-icon-message"></i>导航一</template>
                        <el-menu-item-group>
                            <template slot="title">分组一</template>
                            <el-menu-item index="1-1">选项1</el-menu-item>
                            <el-menu-item index="1-2">选项2</el-menu-item>
                        </el-menu-item-group>
                        <el-menu-item-group title="分组2">
                            <el-menu-item index="1-3">选项3</el-menu-item>
                        </el-menu-item-group>
                        <el-submenu index="1-4">
                            <template slot="title">选项4</template>
                            <el-menu-item index="1-4-1">选项4-1</el-menu-item>
                        </el-submenu>
                    </el-submenu>
                    <el-submenu index="2">
                        <template slot="title"><i class="el-icon-menu"></i>导航二</template>
                        <el-menu-item-group>
                            <template slot="title">分组一</template>
                            <el-menu-item index="2-1">选项1</el-menu-item>
                            <el-menu-item index="2-2">选项2</el-menu-item>
                        </el-menu-item-group>
                        <el-menu-item-group title="分组2">
                            <el-menu-item index="2-3">选项3</el-menu-item>
                        </el-menu-item-group>
                        <el-submenu index="2-4">
                            <template slot="title">选项4</template>
                            <el-menu-item index="2-4-1">选项4-1</el-menu-item>
                        </el-submenu>
                    </el-submenu>
                    <el-submenu index="3">
                        <template slot="title"><i class="el-icon-setting"></i>导航三</template>
                        <el-menu-item-group>
                            <template slot="title">分组一</template>
                            <el-menu-item index="3-1">选项1</el-menu-item>
                            <el-menu-item index="3-2">选项2</el-menu-item>
                        </el-menu-item-group>
                        <el-menu-item-group title="分组2">
                            <el-menu-item index="3-3">选项3</el-menu-item>
                        </el-menu-item-group>
                        <el-submenu index="3-4">
                            <template slot="title">选项4</template>
                            <el-menu-item index="3-4-1">选项4-1</el-menu-item>
                        </el-submenu>
                    </el-submenu>
                </el-menu>
            </el-aside>


            <el-container>
                <!--                <el-header style="text-align: right; font-size: 12px">-->
                <!--                    <el-dropdown>-->
                <!--                        <i class="el-icon-setting" style="margin-right: 15px"></i>-->
                <!--                        <el-dropdown-menu slot="dropdown">-->
                <!--                            <el-dropdown-item>查看</el-dropdown-item>-->
                <!--                            <el-dropdown-item>新增</el-dropdown-item>-->
                <!--                            <el-dropdown-item>删除</el-dropdown-item>-->
                <!--                        </el-dropdown-menu>-->
                <!--                    </el-dropdown>-->
                <!--                    <span>王小虎</span>-->
                <!--                </el-header>-->


                <el-main>

                    <template>
                        <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
                            <el-tab-pane label="用户管理" name="first">用户管理</el-tab-pane>
                            <el-tab-pane label="配置管理" name="second">配置管理</el-tab-pane>
                            <el-tab-pane label="角色管理" name="third">

                                <HelloWorld msg="Welcome to Your Vue.js App"/>

                            </el-tab-pane>
                            <el-tab-pane label="表格数据" name="fourth">

                                <el-table :data="tableData">
                                    <el-table-column prop="date" label="日期" width="140">
                                    </el-table-column>
                                    <el-table-column prop="name" label="姓名" width="120">
                                    </el-table-column>
                                    <el-table-column prop="address" label="地址">
                                    </el-table-column>
                                </el-table>


                            </el-tab-pane>
                        </el-tabs>
                    </template>


                </el-main>
            </el-container>


        </el-container>


<!--        <el-row class="tac">-->

<!--            <el-col :span="4">-->
<!--                <el-menu-->
<!--                        default-active="2"-->
<!--                        class="el-menu-vertical-demo"-->
<!--                        @open="handleOpen"-->
<!--                        @close="handleClose"-->
<!--                        background-color="#545c64"-->
<!--                        text-color="#fff"-->
<!--                        active-text-color="#ffd04b">-->

<!--                    <el-menu-item index="1">-->
<!--                        <i class="el-icon-setting"></i>-->
<!--                        <span slot="title">主页展示</span>-->
<!--                    </el-menu-item>-->


<!--                    <el-submenu index="2">-->
<!--                        <template slot="title">-->
<!--                            <i class="el-icon-location"></i>-->
<!--                            <span>用户管理</span>-->
<!--                        </template>-->
<!--                        <el-menu-item-group>-->
<!--                            <template slot="title">分组一</template>-->
<!--                            <el-menu-item index="1-1">选项1</el-menu-item>-->
<!--                            <el-menu-item index="1-2">选项2</el-menu-item>-->
<!--                        </el-menu-item-group>-->
<!--                        <el-menu-item-group title="分组2">-->
<!--                            <el-menu-item index="1-3">选项3</el-menu-item>-->
<!--                        </el-menu-item-group>-->
<!--                        <el-submenu index="1-4">-->
<!--                            <template slot="title">选项4</template>-->
<!--                            <el-menu-item index="1-4-1">选项1</el-menu-item>-->
<!--                        </el-submenu>-->
<!--                    </el-submenu>-->
<!--                    <el-menu-item index="3">-->
<!--                        <i class="el-icon-menu"></i>-->
<!--                        <span slot="title">商家管理</span>-->
<!--                    </el-menu-item>-->
<!--                    <el-menu-item index="4" disabled>-->
<!--                        <i class="el-icon-document"></i>-->
<!--                        <span slot="title">商品管理</span>-->
<!--                    </el-menu-item>-->
<!--                    <el-menu-item index="5">-->
<!--                        <i class="el-icon-setting"></i>-->
<!--                        <span slot="title">入库管理</span>-->
<!--                    </el-menu-item>-->

<!--                    <el-menu-item index="6">-->
<!--                        <i class="el-icon-setting"></i>-->
<!--                        <span slot="title">出库管理</span>-->
<!--                    </el-menu-item>-->

<!--                    <el-menu-item index="7">-->
<!--                        <i class="el-icon-setting"></i>-->
<!--                        <span slot="title">库存管理</span>-->
<!--                    </el-menu-item>-->

<!--                    <el-menu-item index="8">-->
<!--                        <i class="el-icon-setting"></i>-->
<!--                        <span slot="title">信息管理</span>-->
<!--                    </el-menu-item>-->

<!--                </el-menu>-->
<!--            </el-col>-->


<!--        </el-row>-->



    </div>
</template>

<script>
    import HelloWorld from './components/HelloWorld.vue'

    export default {
        name: 'app',
        components: {
            HelloWorld
        },

        data() {
            const item = {
                date: '2016-05-02',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
            };
            return {
                tableData: Array(20).fill(item)
            }
        }
    }
</script>

<style>

    .el-header {
        background-color: #B3C0D1;
        color: #333;
        line-height: 60px;
    }

    .el-aside {
        color: #333;
    }

    /*#app {*/
    /*  font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
    /*  -webkit-font-smoothing: antialiased;*/
    /*  -moz-osx-font-smoothing: grayscale;*/
    /*  text-align: center;*/
    /*  color: #2c3e50;*/
    /*  margin-top: 60px;*/
    /*}*/
</style>
