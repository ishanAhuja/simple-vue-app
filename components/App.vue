<template>
  <div class="screen">

    <!-- "masthead" is a vue component that is imported into this component on line 30, and registered with the App component (this component) on line 76. To create a new component, simply create a file with at least the template tag. Then import it and register it with the component you want to use your new component from. You can nest as many components as needed, without restrictions. -->
    <masthead />
    <div class="two-pane">
      <!-- Imported on line 32, registered on line 75-->
      <sidebar :selected-item="selectedItem" :items="items" @select="setSelectedItem" />

      <!-- Imported on line 32, registered on line 77-->
      <detail-view :item="selectedItem" />
    </div>
  </div>
</template>

<style scoped>
  div.screen {
    display: flex;
    flex-direction: column;
    height: 100vh;
    font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Oxygen-Sans,Ubuntu,Cantarell,"Helvetica Neue",sans-serif;
  }

  div.two-pane {
    display: flex;
    flex-grow: 1;
    flex-direction: row;
  }
</style>

<script>
  import DetailView from './DetailView'
  import Masthead from './Masthead'
  import Sidebar from './Sidebar'

  export default {
    data () {
      return {
        items: [
          {
            id: 1,
            label: 'Wi-Fi',
            description: 'Wi-fi allows you to wirelessly network multiple nodes.',
            active: true
          },
          {
            id: 2,
            label: 'Bluetooth',
            description: 'Bluetooth enables adhoc peer-to-peer networking between nodes.',
            active: false
          },
          {
            id: 3,
            label: 'GPS',
            description: 'GPS provides realtime geolocation capabilities.',
            active: false
          },
          {
            id: 4,
            label: 'Mobile Data',
            description: 'Communicate with cell towers and transmit data wirelessly over long distances.',
            active: false
          }
        ],
        selectedItem: null
      }
    },
    methods: {
      // Methods are called from lifecycle methods (like when the component is created/destroyed/etc) or as event handlers. This method has been bound to the "select" event on line 8, which is emitted by the Sidebar component.
      setSelectedItem (selectedItem) {
        this.selectedItem = selectedItem
      }
    },
    components: {
      DetailView,
      Masthead,
      Sidebar
    }
  }
</script>