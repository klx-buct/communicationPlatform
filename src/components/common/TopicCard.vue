<template>
    <router-link tag="div" to="/post" class="content">
        <span class="prompt">{{prompt}}</span>
        <el-row>
            <el-col :span="2">
                <el-avatar
                    shape="square"
                    :src="imgUrl"
                ></el-avatar>
            </el-col>
            <el-col :span="22">
                <el-row>
                    <el-col :span="3">
                        <span class="small-font">来自</span>
                    </el-col>
                    <el-col :span="21">
                        <span class="small-font">{{type}}</span>
                    </el-col>
                </el-row>
                <el-row>
                    <span class="title">{{titleFirst}} </span>
                    {{titleSecond}}
                </el-row>
                <el-row>
                    <span class="small-font">共 {{amount}} 个回答</span>
                </el-row>
                <el-row class="line">
                    <el-row class="small-font">
                        <span style="color:black">{{username}} </span>
                        <span>回答</span>
                    </el-row>
                    <el-row>
                        <div class="text">
                            {{content}}
                        </div>
                    </el-row>
                </el-row>
            </el-col>
        </el-row>
    </router-link>
</template>

<script>
export default {
    props: ['imgUrl','type', 'titleFirst', 'titleSecond', 'amount', 'username', 'content', 'prompt']
}
</script>

<style lang="scss" scoped>
    .content {
        position: relative;
        box-sizing: border-box;
        width: 90%;
        padding: 25px;
        background-color: white;
        border-radius: 5px;
        cursor: pointer;
    }
    .small-font{
        color:#bbbfc2;
        font-size:10px;
    }
    .line {
        border-left: 1px solid #dadada;
        padding-left: 15px;
    }
    .el-row{
        margin-top:2px;
    }
    .text {
        color:#7d8389;
        font-size:10px;
        display:-webkit-box; /*–课伸缩盒子/弹性盒子–*/
        -webkit-box-orient:vertical;/*–从上向下垂直排列子元素–*/
        -webkit-line-clamp:3;/*–限制在一个块元素显示的文本的行数(超出3行显示省略号)–*/
        overflow:hidden;
    }
    .title {
        color: red;
    }
    .prompt {
        display: inline-block;
        position: absolute;
        left: 5px;
        top: 5px;

        font-size: 10px;
        color: #c0c4c7;
    }
</style>
