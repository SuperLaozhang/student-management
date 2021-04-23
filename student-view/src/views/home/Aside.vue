<template>
  <div style="width: 201px">
    <el-menu
      default-active="2"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose"
      @select="handleSelect"
      background-color="#545c64"
      text-color="#fff"
      active-text-color="#ffd04b">
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span>学生管理</span>
        </template>
        <el-menu-item-group>
<!--          <template slot="title">学生管理</template>-->
          <el-menu-item index="/studentinfo">学生信息
<!--            <router-link to="/studentinfo">学生信息</router-link>-->
          </el-menu-item>
          <el-menu-item index="1-2">统计</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
      <el-menu-item index="2">
        <i class="el-icon-menu"></i>
        <span slot="title">导航二</span>
      </el-menu-item>
      <el-menu-item index="3" disabled>
        <i class="el-icon-document"></i>
        <span slot="title">导航三</span>
      </el-menu-item>
      <el-menu-item index="4">
        <i class="el-icon-setting"></i>
        <span slot="title">系统管理</span>
      </el-menu-item>
    </el-menu>
  </div>
</template>

<script>
export default {
  methods: {
    handleOpen(key, keyPath) {
      console.log("key"+key, "keyPath" + keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    handleSelect(index,indexPath){
      this.$router.push({
        path:index
      })
    }
  }
}
</script>

