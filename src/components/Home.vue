<template>
  <div>
    <h2>我是首页</h2>
    <p>我是首页内容，哈哈哈</p>

    <router-link to="/home/news">新闻</router-link>
    <router-link to="/home/message">消息</router-link>
    <router-view></router-view>

    <h2>{{message}}</h2>
  </div>
</template>

<script>
export default {
  name: "Home",
  data(){
    return {
      message:'你好'
    }
  },
  created() {
    console.log('home created');
    this.$router.push('home')
    // document.title='首页'
  },
  destroyed() {
    console.log('home destroyed');
  }

}
</script>

<style scoped>

</style>