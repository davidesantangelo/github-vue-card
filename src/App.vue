<template>
  <div id="app">
    <User msg="Welcome"/>
  </div>
</template>

<script>
import User from './components/User.vue'

export default {
  name: 'App',
  components: {
    User
  }
}
</script>
