<template>
  <div class="counter-wrapper">
    <div class="counter">
      {{ count }}
    </div>
    <button @click="$store.commit('INCREMENT')">Increment</button>
    <button @click="$store.commit('DECREMENT')">Decrement</button>
    <button @click="$store.dispatch('incrementAsync')">Increment Async</button>
  </div>
</template>

<script>
  import { default as swal } from 'sweetalert2'
  import * as animate from 'animate.css'
  import $ from 'jquery'

  export default {
    computed: {
      count() {
        swal({
          title: 'Please click ok',
          html: $('<div>')
          .addClass('some-class')
          .text('Its just a WIP'),
          animation: false,
          customClass: 'animated tada'
        }).catch(console.error)
        return this.$store.state.count
      }
    }
  }
</script>

<style>
  .counter {
    margin: 100px auto;
    border-radius: 3px;
    width: 200px;
    height: 200px;
    text-align: center;
    line-height: 200px;
    font-size: 5rem;
    background-color: #f0f0f0;
    user-select: none;
  }
</style>
