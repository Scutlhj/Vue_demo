<template>
  <div class="img">
    <img :src="props.photoUrl">
    <span class="rank">{{ props.rank }}</span>
  </div>
</template>

<script setup>
  import {computed} from "vue";

  const props = defineProps(["photoUrl","rank"])
  const color = computed(()=>{
    if (props.rank === 1) {
      return "rgb(254, 45, 70)"
    } else if (props.rank === 2) {
      return "rgb(245, 102, 1)"
    } else {
      return "rgb(247, 169, 1)"
    }
  })
</script>

<style scoped>
.img{
  position: relative;
  width: 100px;
  background-color: white;
  border-radius: 15px;
  overflow: hidden;
}
.img img{
  width: 100%;
  vertical-align: top;
}
.img .rank{
  width: 30px;
  height: 30px;
  border-bottom-right-radius: 15px;
  background-color: v-bind("color");
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
</style>