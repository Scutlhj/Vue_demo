<template>
  <div class="hot-bar">
    <div class="current-hot">{{ props.hot }}热度</div>
  </div>
</template>

<script setup>
  import {computed} from "vue";

  const props = defineProps(["hot","maxHot"])
  const width = computed(()=>{
    return props.hot/props.maxHot*100+"%"
  })
</script>

<style scoped>
.hot-bar{
  background-color: rgb(3, 37, 103);
  border-radius: 15px;
}
.hot-bar .current-hot{
  width: v-bind("width");
  text-indent: 0.7em;
  border-radius: 15px;
  background-image: linear-gradient(
      90deg,
      rgb(187, 3, 52) 50%,
      rgb(66, 2, 12)
  );
  white-space: nowrap;
  user-select: none;
}
</style>