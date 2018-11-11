<template>
  <v-app dark>
    <menu-drawer/>
    <app-bar/>
    <main-content>
      <grid-sample/>
    </main-content>
  </v-app>
</template>

<script>
  import HelloWorld from './components/HelloWorld'
  import MenuDrawer from './components/MenuDrawer'
  import AppBar from './components/AppBar'
  import ListExample from './components/ListExample'
  import MainContent from './components/MainContentContainer'
  import GridSample from './components/GridExample'

  export default {
    name: 'App',
    components: {
      HelloWorld,
      MenuDrawer,
      AppBar,
      ListExample,
      MainContent,
      GridSample
    },
    data() {
      return {
        //
      }
    }
  }
</script>
