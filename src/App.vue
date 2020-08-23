<template>
  <div id="app">
    <p>app.vue 这是入口</p>
    <router-view/>
    <p>听说这个是个入口，怎么个入法呢？app.vue </p>
    <p>填充上面router-view 这个标签？</p>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="scss">
 @import "./style/style";
</style>
