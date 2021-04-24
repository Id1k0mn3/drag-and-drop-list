<template>
  <button @click="add">add section</button>
  <sections-items v-for="i in items" :key="i"></sections-items>
</template>

<script>

import SectionsItems from './SectionsItems.vue';

export default {
  components: {
    SectionsItems
  },
  data() {
    return {
      counter: 0,
      items: [],
    }  
  },
  methods: {
    add() {
      this.items.push(Math.random())
      console.log(this.items)
    }
  }
}
</script>