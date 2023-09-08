<template>
  <el-container style="height: 700px; border: 1px solid #eee">
    <el-header style="font-size: 40px; background-color: rgb(238, 241, 246)">复域笔记</el-header>
    <el-container>
      <el-aside width="230px" style="border: 1px solid #eee">
        <!-- 从官网复制的代码 -->
        <el-menu :default-openeds="['1', '3']">
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i>系统信息管理</template>
            <el-menu-item-group>
              <template slot="title">部门管理</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">员工管理</template>
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
            <template slot="title"
            ><i class="el-icon-setting"></i>导航三
            </template
            >
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
        <!-- 从官网复制的代码 -->
      </el-aside>

      <el-main>
        <!--        表单-->
        <el-form :inline="true" :model="searchForm" class="demo-form-inline">
          <el-form-item label="姓名">
            <el-input v-model="searchForm.name" placeholder="姓名"></el-input>
          </el-form-item>
          <el-form-item label="性别">
            <el-select v-model="searchForm.gender" placeholder="性别">
              <el-option label="男" value="1"></el-option>
              <el-option label="女" value="2"></el-option>
            </el-select>
          </el-form-item>
          <!--        日期选择-->
          <el-date-picker
              v-model="searchForm.entrydate"
              type="daterange"
              range-separator="至"
              start-placeholder="开始日期"
              end-placeholder="结束日期">
          </el-date-picker>
          <!--    以上    日期选择-->
          <el-form-item>
            <el-button type="primary" @click="onSubmit">查询</el-button>
          </el-form-item>
        </el-form>

        <!--        表格-->
        <el-table :data="tableData" border>
          <el-table-column prop="name" label="姓名" width="180"></el-table-column>
          <el-table-column prop="image" label="图像" width="180">

            <template slot-scope="scope">
              <img :src="scope.row.image" width="100px" height="70px">
            </template>
          </el-table-column>
          <el-table-column prop="gender" label="性别" width="140">
            <template slot-scope="scope">
              {{scope.row.gender==1?'男':'女'}}
            </template>
          </el-table-column>
          <el-table-column prop="job" label="职位" width="140"></el-table-column>
          <el-table-column prop="entrydate" label="入职时间" width="180"></el-table-column>
          <el-table-column prop="updatetime" label="最后操作时间" width="230"></el-table-column>
          <el-table-column label="操作">
            <el-button type="primary" size="mini">编辑</el-button>
            <el-button type="danger" size="mini">删除</el-button>
          </el-table-column>
        </el-table>
        <br>
        <br>
        <!--        分页条-->
        <!-- pagination 分页  -->
        <el-pagination
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            background
            layout="sizes,prev, pager, next,jumper,total"
            :total="1000">
        </el-pagination>

      </el-main>
    </el-container>
  </el-container>
</template>


<script>
import axios from 'axios';

export default {
  data() {
    return {
      tableData: [],
      searchForm: {
        name: "",
        gender: "",
        entrydate: [],
      }
    };
  },
  methods: {
    onSubmit: function () {
      alert("查询数据");
    },
    // 函数参数代表 每页条数
    handleSizeChange: function (val) {
      alert("每一页条数" + val);
    },
    // 函数参数代表当前页
    handleCurrentChange: function (val) {
      alert("当前页" + val);
    },

  },
  mounted() {
    //发送异步请求,获取数据
    axios.get("https://mock.apifox.cn/m1/3235583-0-default/element_emp_list").then((result) => {
      this.tableData = result.data.data;
    });
  }
}

</script>


<style>
</style>