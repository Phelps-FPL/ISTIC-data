<template>
  <div class="industry">
    <el-button type="primary" style="padding:10px 12px;font-size:20px" class="hidden-lg-and-up"></el-button>
    <el-container>
      <el-aside class="hidden-md-and-down">
        <el-autocomplete
          class="inline-input"
          placeholder="请输入名称"
          prefix-icon="el-icon-search"
          :fetch-suggestions="querySearch"
          v-model="name"
          @select="handleSelect"
        ></el-autocomplete>
        <el-table
          ref="listTable"
          :data="nameList"
          highlight-current-row 
          height="calc(100vh - 60px)"
          @current-change="handleCurrentChange"
        >
          <el-table-column property="id" label="#" align="center" width="60" sortable></el-table-column>
          <el-table-column property="value" label="高校名称" align="center" sortable></el-table-column>
        </el-table>
      </el-aside>
      <el-main></el-main>
    </el-container>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import * as echarts from "echarts/lib/echarts";
import "echarts/lib/chart/radar";
import "echarts/lib/component/tooltip";
export default {
  data() {
    return {
      name: ""
    };
  },
  created() {
    this.$store.dispach("initData", { name: "industry" });
    ///在页面加载时读取localStorage里的状态信息
    localStorage.getItem("dataset") &&
      this.$store.replaceState(
        Object.assign(
          this.$store.state,
          JSON.parse(localStorage.getItem("dataset"))
        )
      );
    //在页面刷新时将vuex里的信息保存到localStorage里
    window.addEventListener("beforeunload", () => {
      localStorage.setItem("dataset", JSON.stringify(this.$store.state));
    });
  },
  methods: {
    handleSelect(val) {
      this.$refs.listTable.setCurrentRow(this.nameList[val.id - 1]);
    },
    querySearch(queryString, cb) {
      var results = queryString
        ? this.nameList.filter(item => item.value.indexOf(queryString) === 0)
        : this.nameList;
      cb(results);
    },
  },
  computed: {
      ...mapGetters(["indicatorsList", "dataList", "nameList"]),
    currentTableData() {
      let that = this;
      return this.currentData.map((d, index) => {
        return {
          indicatorName: that.indicatorsList[index],
          indicatorvalue: d
        };
      });
    }
  },
};
</script>

<style lang="less" scoped>
@import url("../assets/less/base.less");

</style>