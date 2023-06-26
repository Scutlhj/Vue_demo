<template>
  <!--  主容器-->
  <div class="container">
    <!--头部菜单-->
    <div class="title">
      <!--      两个切换按钮-->
      <button @click="isShow = 0" class="hot-soccer" :class="{active:isShow === 0}">热门球员</button>
      <button @click="isShow = 1" class="hot-team" :class="{active:isShow === 1}">热门球队</button>
    </div>
    <!--    在eslint中使用v-for要带个key即(value,key) in values-->
    <div class="main-bar" v-show="isShow === 0">
      <slot name="1"></slot>
    </div>
    <div class="main-bar" v-show="isShow === 1">
      <slot name="2"></slot>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue";
const isShow = ref(0)
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
  color: white;
}
.container{
  width: 600px;
  background-color: blue;
  margin: 0 auto;
  padding: 20px;
}
.title{
  width: 100%;
  display: flex;
  border-radius: 10px;
  /*不用的话父元素边框会被子元素挡住*/
  overflow: hidden;
}
.title .hot-soccer,.title .hot-team{
  padding: 5px 0;
  border: none;
  flex: auto;
  font-size: 20px;
  color: black;
  background-color: white;
  cursor: pointer;
  transition: .1s;
}
.title .active{
  color: white;
  background-color: red;
}

.main-bar{
  margin-top: 10px;
  padding: 0 10px;
}
</style>