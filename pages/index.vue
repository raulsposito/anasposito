<template>
  <div>
    <Hero class="mt-8"/>
    <Scroll class="fadeOut scrolldown"/>
    <Boost class="mt-24 letter-a"/>
    <Vid/>
    <Join class="-mt-24 letter-x"/>
  </div>
</template>

<script>
import lax from 'lax.js'

export default {
  data() {
    return {
      show: false,
    }
  },
  mounted() {
        lax.init()
        lax.addDriver('scrollY', function () {
        return window.scrollY
        })
        lax.addElements('.fadeIn', {
        scrollY: {
            opacity: [
            [0, 100],
            [0, 1],
            ],
        },
        })
        lax.addElements('.scrolldown', {
        scrollY: {
            'letter-spacing': [
            [0, 'screenHeight*0.75'],
            [0, 150],
            {
                cssUnit: 'px',
            },
            ],
            opacity: [
            [50, 100],
            [1, 0],
            ],
            translateX: [
            [0, 'screenHeight'],
            [0, 80],
            ],
        },
        })
        lax.addElements('.fadeOut', {
        scrollY: {
            opacity: [
            [0, 100],
            [1, 0],
            ],
        },
        })
        lax.addElements('.letter-x', {
        scrollY: {
            translateY: [
            [-400, 0],
            [100, 0],
            ],
            translateX: [
            [2220, 'screenHeight'],
            [0, 600],
            ],
            opacity: [
            [0, 100],
            [0, 1],
            ],
        },
        })
        lax.addElements('.letter-a', {
        scrollY: {
            translateY: [
            [-400, 0],
            [200, 0],
            ],
            translateX: [
            [220, 'screenHeight'],
            [0, -400],
            ],
            opacity: [
            [0, 100],
            [0, 1],
            ],
        },
        })
        lax.addElements('.downarrows', {
        scrollY: {
            translateY: [
            [0, 75],
            [0, 200],
            ],
            opacity: [
            [0, 100],
            [1, 0],
            ],
        },
        })
        lax.addElements('.grow', {
        scrollY: {
            scale: [
            [30, 100],
            [0.3, 1],
            ],
        },
        })
    },
    beforeUnmount() {
    lax.removeElements(
      '.fadeIn',
      '.grow',
      '.downarrows',
      '.letter-a',
      '.letter-x',
      '.fadeOut',
      '.scrolldown'
    )
  },
}
</script>
