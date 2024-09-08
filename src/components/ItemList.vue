<!-- src/components/ItemList.vue -->
<template>
  <ul class="item-list">
    <li v-for="(item, index) in items" :key="index">{{ item }}</li>
  </ul>
</template>

<script>
export default {
  name: 'ItemList',
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.item-list {
  list-style-type: none;
  padding: 0;
}
.item-list li {
  padding: 8px 0;
  border-bottom: 1px solid #ddd;
}
</style>
