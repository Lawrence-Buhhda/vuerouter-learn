<template>
  <!--  所有的item都展示同一个图片，同一个文字-->
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive">
      <slot name="item-icon"></slot>
    </div>
    <div v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <div :class="{active:isActive}">
      <slot name="item-text"></slot>
    </div>

    <!--      <img src="../../assets/img/tabbar/home.svg" alt="">-->
    <!--      <div>首页</div>-->
  </div>
</template>

<script>
export default {
  name: 'TabBarItem',
  props: {
    path: String
  },
  data () {
    return {
      isActive: false
    }
  },
  methods: {
    itemClick () {
      this.$router.replace(this.path)
    }
  }
}
</script>

<style scoped>
.tab-bar-item {
  /*均等分*/
  flex: 1;
  text-align: center;
  height: 49px;
  font-size: 14px;
}

.tab-bar-item img {
  width: 24px;
  height: 24px;
  margin-top: 3px;
  /*图片基线对齐而不是中线*/
  vertical-align: middle;
  margin-bottom: 2px;
}

.active {
  color: red;
}
</style>
