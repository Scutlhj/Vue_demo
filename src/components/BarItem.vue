<template>
  <div class="bar-items">
    <PhotoBar :photoUrl="props.item.photoUrl" :rank="props.item.rank"></PhotoBar>
    <div class="desc">
      <span class="name">{{ props.item.name }}</span>
      <HotBar :hot="props.item.hot" :maxHot="props.maxHot"></HotBar>
    </div>
  </div>
</template>

<script setup>
  //props中的数据为响应式数据即使用了proxy
  import HotBar from "@/components/HotBar";
  import PhotoBar from "@/components/PhotoBar";
  const props = defineProps(["item","maxHot"])
</script>

<style scoped>
.bar-items{
  display: flex;
  margin-bottom: 20px;
}
.bar-items .desc{
  flex: auto;
  margin-left: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  font-size: 18px;
}
</style>