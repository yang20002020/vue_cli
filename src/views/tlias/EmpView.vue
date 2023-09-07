<template>
  <el-container style="height: 700px; border: 1px solid #eee">
    <el-header style="font-size: 40px; background-color: rgb(238, 241, 246)"
      >智能学习辅导系统</el-header>
    <el-container>
      <el-aside width="200px">
        <!-- 从官网复制的代码 -->
        <el-menu :default-openeds="['1', '3']">
          <el-submenu index="1">
            <template slot="title"
              ><i class="el-icon-message"></i>系统信息管理</template
            >
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
              ><i class="el-icon-setting"></i>导航三</template
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
        <el-table :data="tableData">
          <el-table-column
            prop="name"
            label="姓名"
            width="180"
          ></el-table-column>
          <el-table-column
            prop="image"
            label="图像"
            width="180"
          ></el-table-column>
          <el-table-column
            prop="gender"
            label="性别"
            width="140"
          ></el-table-column>
          <el-table-column
            prop="job"
            label="职位"
            width="140"
          ></el-table-column>
          <el-table-column
            prop="entrydate"
            label="入职日期"
            width="180"
          ></el-table-column>
          <el-table-column
            prop="updatetime"
            label="最后操作时间"
            width="230"
          ></el-table-column>
          <el-table-column label="操作">
            <el-button type="primary" size="mini">编辑</el-button>
            <el-button type="danger" size="mini">删除</el-button>
          </el-table-column>
        </el-table>
      </el-main>
    </el-container>
  </el-container>
</template>


<script>
export default {
  data(){
    return {
      tableData:[]
    }
  }
};
</script>


<style >
</style>