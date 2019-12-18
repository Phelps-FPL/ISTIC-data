<template>
  <div class="footer">
    <el-row>
      <el-col :lg="12" :xs="24" class="left">
        <h3>联系方式</h3>
        <p>
          <i class="el-icon-message"></i>
          <span>@istic.ac.cn</span>
        </p>
        <p>
          <i class="el-icon-phone"></i>
          <span>010-5888xxxxx</span>
        </p>
         <p>
          <i class="el-icon-location"></i>
          <span>北京市海淀区xxxxx</span>
        </p>
      </el-col>
      <el-col :xs='24' :lg='12' class="right">
          <p>如果你有课题、项目、科研管理等方面的需求或者任何相关建议，可以与我们联系详谈</p>
          <p><a href="mailto:xuxy@istic.ac.cn">
              <el-button type="primary" class="el-icon-message">联系我们</el-button>
            </a>
          </p> 
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="less" scoped>
.footer{
  background-color: #fff;
  .el-row{
    width: 1200px;
    max-width: calc(100% - 2rem);
    margin: 0 auto;
    text-align: left;
    padding: 2rem;
    .el-col{
      &.left{
        h3{
          color: #1890ff;
          line-height: 2rem;
        }
        p{
          span{
            display: inline-block;
            padding: 0.5rem 2rem;
          }
        }
      }
      &.right{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        p{
          padding: 0.5rem 0rem;
          line-height: 2.5rem;
        }
      }
    }
  }

}
</style>