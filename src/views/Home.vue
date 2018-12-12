<template>
  <div class="home">
    <div
      v-intro-autostart="autostart"
      v-intro-autostart.config="autostartConfig"
    >
      <div v-intro="'第一步'">第一步</div>
      <div v-intro="'第二步'">第二步</div>
    </div>    
  </div>
</template>

<script>

export default {
  name: 'home',
  data() {
    return {
      autostart: false,
      autostartConfig: {
          nextLabel: '[next -->]'
      }
    }
  },
  mounted() {
    console.log(localStorage.getItem('new') === null || localStorage.getItem('new') !== '1' )
    if(localStorage.getItem('new') === null || localStorage.getItem('new') !== '1') {
      this.$intro().start()
      this.$intro().showHints()
      localStorage.setItem('new', 1)
    }
  }
}
</script>
