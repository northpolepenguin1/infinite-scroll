<template>
    <div class="InfiniteScroll">
        <p>{{ message }}</p>
        <div v-show="anim1" class="anim1">
            <span>anim1</span><br />
        </div>
        <button v-on:click="anim1Btn">anim1</button>
        <div v-show="anim2" class="anim2">
            <span>anim2</span><br />
        </div>
        <button v-on:click="anim2Btn">anim2</button><br />
        <div v-show="anim3 " class="anim3"> 
        <span>anim3</span>
        </div>
        <button v-on:click="anim3Btn">anim3</button><br />
        <div class="anim4">
            a
        </div>
    </div>   
</template>

<script>
export default {
  name: 'InfiniteScroll',
  data() {
      return {
          message: 'アニメーション',
          anim1: false,
          anim2: false,
          anim3: false,
      }
  },
  methods: {
      anim1Btn: function() {
          this.anim1 = !this.anim1
      },
      anim2Btn: function() {
          this.anim2 = !this.anim2
      },
      anim3Btn: function() {
          this.anim3 = !this.anim3
      }
  }
}
</script>
<style scoped>
    .InfiniteScroll {
        font-family: 'Teko', serif;
        font-size: 22px;
    }
    .anim4 {
        animation: anime1 5s ease-2s infinite alternate;
    }

    @keyframes anime1 {
        0% {width: 50px; height: 50px; background-color: aqua;}
        100% {width: 200px; height: 50px; background-color: blue;}
    }

    @keyframes sizeScale {
    0% {
        width:200px;
    }
    100% {
        width:300px;
    }
}
</style>