<template>
    <el-container class="home">
    <el-header>
      <div class="logo"></div>
      <div class="logout">
        欢迎光临
        <a href="javascript:;" @click="logout">退出</a>
      </div>
       <h1 class="title">电商后台管理系统</h1>
    </el-header>
    <el-container>
      <el-aside width="200px">
        <!-- 侧边栏 -->
        <!-- el-menu 菜单组件 -->
        <!-- default-active 默认选中的菜单 -->
        <!-- el-submenu 子菜单 -->
        <!-- el-menu-item-group 子菜单的分组 -->
        <!-- el-menu-item  二级菜单 -->
        <!-- :unique-opened="true"  只能打开一个子菜单 -->
            <el-menu
          default-active="1-1"
          class="el-menu-vertical-demo"
          :unique-opened="true"
          background-color="#545c64"
          text-color="#fff"
          active-text-color="#ffd04b">
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>用户管理</span>
            </template>
              <!-- 放菜单项 -->
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>
              <span slot="title">用户列表</span>
            </el-menu-item>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>权限管理</span>
            </template>
            <el-menu-item index="2-1">
              <i class="el-icon-menu"></i>
              <span slot="title">角色列表</span>
            </el-menu-item>
            <el-menu-item index="2-2">
              <i class="el-icon-menu"></i>
              <span slot="title">权限列表</span>
            </el-menu-item>
          </el-submenu>
        </el-menu>
      </el-aside>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  methods: {
    // 退出功能
    logout() {
      // 弹出模态框
      // 参数1：提示内容
      // 参数2：提示标题
      this.$confirm('您确定退出吗?', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        type: 'warning'
      })
        .then(() => {
          localStorage.removeItem('token')
          this.$router.push('/login')
          this.$message.success('退出成功')
        })
        .catch(() => {
          this.$message.info('退出取消')
        })
    }
  }
}
</script>

<style lang="less" scoped>
// 如果给style添加scoped属性，样式只会在当前组件生效
// 实现原理： 如果给当前组件的style添加了scoped,,,,把当前组件中所有的div都增加一个随机的属性
.home {
  height: 100%;

  .el-header {
    background-color: #b3c1cd;

    .logo {
      width: 180px;
      height: 60px;
      float: left;
      background-image: url('../assets/logo.png');
      background-size: contain;
      background-repeat: no-repeat;
      background-position: center;
    }

    .logout {
      width: 200px;
      line-height: 60px;
      height: 60px;
      float: right;
      text-align: right;
      a {
        color: darkorange;
      }
    }

    .title {
      height: 60px;
      line-height: 60px;
      overflow: hidden;
      text-align: center;
      color: #fff;
      font-weight: bold;
    }
  }
  .el-aside {
    background-color: #545c64;

    .el-submenu {
      width: 200px;
    }
  }
  .el-main {
    background-color: #d4dffe;
  }
}
</style>
