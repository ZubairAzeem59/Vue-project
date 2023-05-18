<template>
  <div class="main-page">
    <Header />
    <div class="main">
      <Sidebar />
      <Columns />
      <camera />
      <Newtab />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Sidebar from "./components/Sidebar.vue";
import Columns from "./components/Columns.vue";
import camera from "./components/camera.vue";
import Newtab from "./components/Newtab.vue"
export default {
  name: "App",
  components: {
    Header,
    Sidebar,
    Columns,
    camera,
    Newtab
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}



.main {
  display: flex;
}
</style>
