<template>
    <div class="center examplex">
      <vs-navbar color="#7d33ff" text-white square center-collapsed v-model="active">
        <template #left>
          <img src="/logos/logo-vuesax-logotipo-vuesax-png-4.png" alt="">
        </template>
        <vs-navbar-item :active="active == 'guide'" id="guide">
          Guide
        </vs-navbar-item>
        <vs-navbar-item :active="active == 'docs'" id="docs">
          Documents
        </vs-navbar-item>
        <vs-navbar-item :active="active == 'components'" id="components">
          Components
        </vs-navbar-item>
        <vs-navbar-item :active="active == 'license'" id="license">
          license
        </vs-navbar-item>
        <template #right>
          <vs-button color="#fff" flat >Login</vs-button>
          <vs-button color="#fff" border >Get Started</vs-button>
        </template>
      </vs-navbar>
      <div class="square">
        <div class="child">
          child 1
        </div>
        <div class="child">
          child 2
        </div>
        <div class="child">
          child 3
        </div>
      </div>
    </div>
  </template>
  
  <script>
import applemusic from "./components/applemusic";
export default {
  name: "App",
  components: {
    applemusic,
  },
};
</script>

  <script>
  export default {
    data:() => ({
      active: 'guide'
    })
  }
  </script>