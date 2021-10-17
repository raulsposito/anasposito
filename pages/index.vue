<template>
  <div>
    <Hero/>
    <Boost/>
    <Vid/>
    <Join/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    }
  },
  mounted() {
    window.addEventListener('scroll', () => {
      if (window.scrollY > 150) {
        this.show = false
      } else this.show = true
    })
    return () => {
      window.removeEventListener('scroll')
    }
  },
}
</script>

<style scoped>
@keyframes fadein {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes fadeout {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}

.fadeIn {
  -webkit-animation: fadein 1s ease-in alternate;
  -moz-animation: fadein 1s ease-in alternate;
  animation: fadein 1s ease-in alternate;
}

.fadeOut {
  -webkit-animation: fadeout 1s ease-out;
  -moz-animation: fadeout 1s ease-out;
  animation: fadeout 1s ease-out;
}
</style>