<template>
  <div class="wrapper" @click="update">

    <text class="title">点我。 {{target}}</text>
  </div>
</template>

<style>
  .wrapper { align-items: center; margin-top: 120px; }
  .title { padding-top:40px; padding-bottom: 40px; font-size: 48px; }
  .logo { width: 360px; height: 156px; }
  .desc { padding-top: 20px; color:#888; font-size: 24px;}
</style>

<script>
var modal = weex.requireModule('modal')
  export default {
    data: {
      logoUrl: 'http://img1.vued.vanthink.cn/vued08aa73a9ab65dcbd360ec54659ada97c.png',
      target: 'World'
    },
    methods: {
      update: function (e) {
        this.target = '手气不错'
        modal.confirm({
          message: this.target,
          duration: 0.3
        }, function (value) {
          console.log('alert callback', value)
        })
        console.log('target:', this.target)
      }
    }
  }
</script>
