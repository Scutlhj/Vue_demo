<script setup>
import MainBar from "@/components/MainBar";
import BarList from "@/components/BarList";
//父组件使用props将参数传递给子组件
 const players = [
   {
     name:"梅西",
     hot:433760,
     photoUrl:"/images/messi.png",
     rank:1
   },
   {
     name:"C罗",
     hot:233967,
     photoUrl:"/images/ronaldo.png",
     rank:2
   },
   {
     name:"内马尔",
     hot:122343,
     photoUrl:"/images/neymar.png",
     rank:3
   }
 ]
 const teams = [
   {
     name:"法国",
     hot:433760,
     photoUrl:"/images/法国.jpg",
     rank:1
   },
   {
     name:"巴西",
     hot:233967,
     photoUrl:"/images/巴西.jpg",
     rank:2
   },
   {
     name:"荷兰",
     hot:222343,
     photoUrl:"/images/荷兰.jpg",
     rank:3
   }
 ]
 const maxHotPlayer = players[0].hot
 const maxHotTeam = teams[0].hot
</script>

<template>
  <MainBar>
<!--    使用<slot name="2"></slot>定义一个待填充的位置，在父元素使用<template #2>下的内容即可自动替换该命名slot-->
    <template #1>
      <BarList :items="players" :maxHot="maxHotPlayer"></BarList>
    </template>
    <template #2>
      <BarList :items="teams" :maxHot="maxHotTeam"></BarList>
    </template>
  </MainBar>
</template>

<style scoped>
</style>
