<template>
  <div class="mainindex">
    <h1>this is corny joke main page</h1>
    <img src="http://lorempixel.com/g/400/200/" alt="">
  </div>
</template>

<script>


export default {
  head(){
    return {
      title: "welcome to dad jocks",
      meta:[
        {
          hid:'description',
          name:'description',
          content:'Best place for corny dad jokes'
        }
      ]
    }
  },
  components: {

  }
}
</script>

<style>
  .mainindex h1 {
    text-align: center;
    text-transform: uppercase;
    margin-bottom: 18px;
  }

  .mainindex {
    text-align: center;
  }

  .mainindex img {
    border: 7px solid #a4a138;
  }

</style>
