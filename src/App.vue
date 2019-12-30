<template>
  <div id="app">
      <Nav/>
      <div class="body">
        <router-view/>
      </div>
  </div>
</template>
<script>
  import Nav from '@/components/Navbar'

  export default {
    name: 'App',
    components: {
      Nav
    }
  }
</script>

<style lang="scss">
  .body{
    padding: 15px;
  }
</style>
