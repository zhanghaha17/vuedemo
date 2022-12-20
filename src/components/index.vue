<template>
<div>
  <el-breadcrumb separator="/">
    <el-breadcrumb-item :to="{ path: '/index' }">首页</el-breadcrumb-item>
    <el-breadcrumb-item><a href="/manage">活动管理</a></el-breadcrumb-item>
    <el-breadcrumb-item :to="{ path: '/active'}">活动列表</el-breadcrumb-item>
    <el-breadcrumb-item :to="{ path: '/info'}">活动详情</el-breadcrumb-item>
  </el-breadcrumb>
</div>
</template>

<script>
export default {
  name: "index"
}
</script>

<style scoped>

</style>
