<template>
  <ul class="sidebar">
    <!-- We're using Vue's v-for directive to iterate over the array of items passed in as a prop. The li element will be repeated for each item in the array, and can be accessed under the variable name 'item', as specified here. -->

    <!-- We're binding the class attribute to dynamically have the value 'selected' if the id of that item is that of the selected item, ie, when showing the selected item. -->

    <!-- $emit is used to emit an event on this component that the parent can listen for using '@'. In this case we're emitting the 'select' event, and passing the item in question as an argument. The parent component (App.vue) is binding an event listener for this event on line 8. -->
    <li
      v-for="item in items" :key="item.id"
      :class='selectedItemId === item.id ? "selected" : ""'
      @click="$emit('select', item)">
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
    props: ['items', 'selectedItemId']
  }
</script>