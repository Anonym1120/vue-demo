<template>
  <h1>Velocity.js</h1>
  <transition
  name="fade"
  @before-enter="handleBeforeEnter"
  @enter="handleEnter"
  @after-enter="handleAfterEnter"
  >
  <div v-show="show">
      Welcome
  </div>
  </transition>
  <button @click="click">click</button>


</template>

<script>
import Velocity from 'velocity-animate'

export default {
    data() {
        return {
            show: true,
        }
    },
    methods: {
        click() {
            this.show = !this.show
        },
        handleBeforeEnter: function(el) {
            el.style.opacity = 0
        },
        handleEnter: function(el, done) {
            Velocity(el, {opacity: 1}, {duration: 1000, complete: done})
        },
        handleAfterEnter: function() {
            alert('動畫結束')
        },
    },
}
</script>

<style>
</style>