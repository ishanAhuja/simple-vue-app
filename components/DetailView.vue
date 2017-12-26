<template>

  <!-- v-if is a Vue Directive that conditionally renders an element. In this case, if item has a truthy (not null or empty) value, it'll render this block, otherwise it'll render the v-else block that follows it. -->
  <div class="detail-view" v-if="item">
    <div class="info">
      <!-- Curly braces are used to output the escaped (non-html) values of variables. -->
      <h1>{{ item.label }}</h1>
      <h3>{{ item.description }}</h3>
    </div>
    <div class="toggle">
      <!-- v-model is a Vue directive that creates a 2-way binding between a prop or a data value and an input field. This way, when the value is changed using the field, that change is propagated to all the places where that prop's value is used. -->
      <h3><label> Enabled <input type="checkbox" v-model="item.active"></label></h3>
    </div>
  </div>

  <div class="detail-view no-info" v-else>
    <h3 class="select-item-message">Select an item from the left.</h3>
  </div>
</template>

<!-- Notice that we're using SCSS by specifying it in the "lang" attribute. -->
<style lang="scss" scoped>
  div.detail-view {
    display: flex;
    flex-grow: 1;
    justify-content: center;

    h3.select-item-message {
      color: #999;
      text-align: center;
    }

    // So that the message is center aligned on both axes.
    &.no-info {
      align-items: center;
    }
  }

  div.info {
    flex-grow: 1;
  }
</style>

<script>
  export default {
    props: ['item']
  }
</script>