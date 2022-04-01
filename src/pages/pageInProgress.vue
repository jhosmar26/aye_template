<template>
  <section class="hero">
    <div :class="loaded" class="hero--title">
      Página en construcción
    </div>
  </section>
</template>
<script>
export default ({
  data() {
    return{
      loaded: ""
    }
  },
  mounted() {
    this.loaded = "loaded"
  }
})
</script>
<style scoped>

.hero{
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 2rem;
}

.hero--title{
  font-size: clamp(1rem, 12vw, 6rem);
  width: min-content;
}
</style>
