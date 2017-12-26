<template>
  <ul class="sidebar">
    <!-- $emit is used to emit an event on this component that the parent can listen for using '@'. In this case we're emitting the 'select' event, and passing the item in question as an argument. The parent component (App.vue) is binding an event listener for this event on line 8. -->
    <li v-for="item in items" :key="item.id" @click="$emit('select', item)">
      <div class="label">{{ item.label }}</div> 
      <div class="info">{{ item.active ? 'Active' : 'Inactive' }}</div>
    </li>
  </ul>
</template>

<style scoped>
  ul.sidebar {
    width: 20vw;
    min-width: 200px;
    border-right: 1px solid #DDD;
    margin: 0px 5px 0px 0px;
  }

  div.info {
    color: #AAA;
  }

  li {
    margin: 0px;
    border-bottom: 1px solid #DDD;
    list-style: none;
    list-style-type: none;
    padding: 5px;
    cursor: pointer
  }

  li:hover {
    background-color: #EEE;
  }

  li.selected {
    background-color: #DDD;
  }
</style>

<script>
  export default {
    props: ['items', 'selectedItem']
  }
</script>