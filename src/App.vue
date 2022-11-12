<template>
  <div id="app" class="bg-black">
    <NavBar />
    <HeroSection />
    <InfoCard />
  </div>
</template>

<script>
import HeroSection from './components/HeroSection.vue'
import NavBar from './components/NavBar.vue'
import InfoCard from './components/InfoCard.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    HeroSection,
    InfoCard
  }
}
</script>
