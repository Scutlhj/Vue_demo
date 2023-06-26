<template>
  <BarItem v-for="(item,index) in items" :item="item" :maxHot="props.maxHot" :key="index"></BarItem>
</template>

<script setup>
  import BarItem from "@/components/BarItem";
  const props = defineProps(["items","maxHot"])
</script>

<style scoped>
</style>