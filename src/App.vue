<template>
  <div class="pages">
    <shuju></shuju>
       <HomeApp></HomeApp>
       <ClickAction></ClickAction>
       <InputForm></InputForm>
  </div>
</template>

<script>
import shuju from './components/shuju.vue'
import HomeApp from './components/HomeApp.vue'
import ClickAction from './components/ClickAction.vue'
import InputForm from './components/InputForm.vue'
export default {
  name: 'App',
  components: {
    HomeApp,
    shuju,
    ClickAction,
    InputForm
  }
}
</script>

<style scoped>
</style>
