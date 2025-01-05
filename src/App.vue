<template>
  <q-layout view="lHh Lpr lFf">
  <SideBar />
  <RightSideBar />
  <Header />
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import SideBar from './components/SideBar.vue';
import RightSideBar from './components/RightSideBar.vue';
import Header from './components/Header.vue';



export default {
  name: 'LayoutDefault',

  components: {
    SideBar,
    RightSideBar,
    Header
},

  setup () {
    return {
      
    }
  }
}
</script>
