<template>
  <div id="app">
    <User msg="Welcome"/>
    <Footer />
  </div>
</template>

<script>
import User from './components/User.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    User,
    Footer
  }
}
</script>
