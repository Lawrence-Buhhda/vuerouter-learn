<template>
<div>
  <h2>我是Profile组件</h2>
  <h2>{{$route.query}}</h2>
  <h2>{{$route.query.age}}</h2>

</div>
</template>

<script>
export default {
  name: "Profile",
  mounted() {
    //所有的组件都继承来组Vue类的原型
    console.log(this.$route)
    console.log(this.$router)
  },
  created() {
    console.log('Profile created')
  },
  destroyed() {
    console.log('Profile destroyed')
  }
}
</script>

<style scoped>

</style>