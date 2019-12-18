<template>
    <div class="module">
        <el-card :body-style="{ padding: '0px' }">
      <el-image :src='imgSrc' class="image" lazy></el-image>
      <div class='title'>
          {{title}}
      </div>
    </el-card>
    </div>
</template>

<script>
export default {
    name:'FuncModule',
    props:{
        imgSrc:String,
        title:String
    }
}
</script>

<style lang="less" scpoed>
.module{
    .el-card:hover{
        transform: translateY(-10px);
        box-shadow: 6px 10px 10px #ebeef5;
    }
    .el-card{
        .image{
            width: 100%;
            display: block;
        }
        div.title{
            padding: 14px;
            border-top: 1px solid #ebeef5;
        }
    }
}
</style>