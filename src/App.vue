<template>
  <div id="app">
<!--    <router-link to="/home" tag="button" replace active-class="active">首页</router-link>-->
<!--    <router-link to="/about" replace active-class="active">关于</router-link>-->
<!--        <router-link to="/home" tag="button" replace>首页</router-link>-->
<!--        <router-link to="/about" tag="button" replace>关于</router-link>-->
<!--    <button @click="homeClick">首页</button>-->
<!--    <button @click="aboutClick">关于</button>-->

    <router-link to="/home">首页</router-link>
    <router-link to="/about">关于</router-link>
<!--    通过router-link来实现跳转-->
<!--    <router-link v-bind:to="'/user/'+userid">用户</router-link>-->
<!--    <router-link v-bind:to="{path:'/profile',query:{name:'why',age:18,height:1.88}}">档案</router-link>-->

<!--    通过按钮来实现跳转-->
    <button @click="userClick">用户</button>
    <button @click="profileClick">档案</button>
    <keep-alive exclude="Profile,User">
      <router-view></router-view>
    </keep-alive>

  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      userid:'lisi'
    }
  },
  methods:{
    homeClick(){
      //通过代码的方式修改路由 vue-router this指当前组件
      //push => pushState
      // this.$router.push('/home')
      this.$router.replace('/home')
      console.log('homeClick');
    },
    aboutClick(){
      //
      // this.$router.push('/about')
      this.$router.replace('/about')
      console.log('aboutClick')
    },
    userClick(){
      this.$router.push('/user/'+this.userid)
    },
    profileClick(){
      // this.$router.push('/profile') 没法传参数
      this.$router.push({
        path:'/profile',
        query:{
          name:'kobe',
          age:18,
          height:1.88
        }
      })
    }
  }
}
</script>

<style>
/*.router-link-active{*/
/*  color: red;*/
/*}*/
.active{
  color: red;
}
</style>
