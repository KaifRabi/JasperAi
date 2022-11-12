<template>
  <div id="app" class="bg-black">
    <NavBar />
    <HeroSection />
  </div>
</template>

<script>
import HeroSection from './components/HeroSection.vue'
import NavBar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    HeroSection,
  }
}
</script>
