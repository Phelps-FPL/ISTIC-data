<template>
  <div class="home">
    <div class="banner">
      <el-row>
        <el-col :md="24">
          <h1>
            <strong>ISTIC</strong>科学评价之门
          </h1>
          <h3>
            选取高等院校、医疗机构作为研究对象，以论文、专利、上市公司年报数据作为数据源，
            结合Web前端数据可视化技术从科研成果转化、学科发展布局、学科交叉融合、国际合作地图、医工结合、科教协同融合等
            多方面分析中国科研机构的创新能力。
          </h3>
          <a href="#funcModule">
            <el-button type="primary" plain icon="el-icon-caret-bottom">继续了解</el-button>
          </a>
        </el-col>
      </el-row>
    </div>
    <div class="funcModule" id="funcModule">
      <el-row :gutter='20'>
        <el-col :xs='24' :sm='12' :lg='8'>
          <a href="">
              <img :src="industryUrl" alt="" title="中国高校产学共创排行榜">
              </a>
        </el-col>
        <el-col :xs='24' :sm='12' :lg='8'>
          <a>
            <img :src="worldmapUrl" alt="" title="中国高校产学共创排行榜">
              </a>
        </el-col>
        <el-col :xs='24' :sm='12' :lg='8'>
              <a><img :src="papermatrixUrl" alt="" title="中国高校产学共创排行榜"></a>
        </el-col>
        <el-col :xs='24' :sm='12' :lg='8'>
              <a><img :src="patentmatrixUrl" alt="" title="中国高校产学共创排行榜"></a>
        </el-col>
        <el-col :xs='24' :sm='12' :lg='8'>
              <a><img :src="medicalUrl" alt="" title="中国高校产学共创排行榜"></a>
        </el-col>
        <el-col :xs='24' :sm='12' :lg='8'>
              <a><img :src="fushionUrl" alt="" title="中国高校产学共创排行榜"></a>
        </el-col>
      </el-row>
    </div>
    <Footer></Footer>
  </div>
</template>

<script>
// @ is an alias to /src
import Footer from '../components/Footer'
import industry from '../assets/industry.png';
import worldmap from "../../src/assets/map.png";
import papermatrix from "../../src/assets/paperMatrix.png";
import patentmatrix from "../../src/assets/patentMatrix.png";
import medical from "../../src/assets/medical.png";
import fushion from "../../src/assets/fushion.png";
export default {
  name: 'home',
  components: {
    Footer
  },
  data() {
    return {
      industryUrl:industry,
      worldmapUrl: worldmap,
      papermatrixUrl: papermatrix,
      patentmatrixUrl: patentmatrix,
      medicalUrl: medical,
      fushionUrl: fushion,
    }
  },
}
</script>


<style lang="less" scoped>
  @import url("../assets/less/base.less");
  .home{
    .banner{
      text-align-last: center;
      margin: 4rem 0;
      .el-row{
        width: 1200px;
        max-width: calc(100% - 2rem);
        margin: 0 auto;
      }
      h1{
        font-size: 2rem;
        color: @brand-color;
      }
      h3{
        line-height: 3rem;
        font-size: 1rem;
        font-weight: 500;
        color: @font-primary-color;
      }
      @media screen and (max-width: 992px) {
        h3 {
          font-size: 1rem;
          line-height: 2.5rem;
          text-align: justify;
        }
      }
    }
    .funcModule{
      width: 1200px;
      max-width: calc(100% - 2rem);
      margin: 2rem auto;
      a{
      text-decoration: none;
      img{
        width: 400px;
        height: 400px;
      }
      } 
      .el-row{
        .el-col{
          margin:  1rem 0;
        }
      }
    }
  }
</style>