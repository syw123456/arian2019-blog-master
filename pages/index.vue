<template>
    <div class="content">
      <h1 class="name" data-text="Hello">Hello.</h1>
      <h2> My name is Arian.</h2>
      <h2 class="tagline">developer + <br/>app designer </h2>
      <nuxt-link to="/about" class="button">learn more</nuxt-link>
  </div>
</template>
<script>
export default {
  components: {
  },

  props: []
}
</script>

<style scoped>
h1{
  display: inline-block;
  -webkit-transform-style: preserve-3d;
  -moz-transform-style: preserve-3d;
  transform-style: preserve-3d;
  -webkit-perspective: 500;
  -moz-perspective: 500;
  -ms-perspective: 500;
  perspective: 500;
  -webkit-font-smoothing: antialiased;
}
h1:before,h1:after{
  position: absolute;
  top: 0;
  left: -1px;
  content: attr(data-text);
  -webkit-transform-origin: left top;
  -moz-transform-origin: left top;
  -ms-transform-origin: left top;
  transform-origin: left top;
  -webkit-transition: all ease-out 0.3s;
  -moz-transition: all ease-out 0.3s;
  -ms-transition: all ease-out 0.3s;
  transition: all ease-out 0.3s;
}
h1:before{
  color: rgba(0,0,0,0.3);
  -webkit-transform: scale(1.1,1) skew(0,20deg);
  -moz-transform: scale(1.1,1) skew(0,20deg);
  -ms-transform: scale(1.1,1) skew(0,20deg);
  transform: scale(1.1,1) skew(0,20deg);
}
h1:after{
  color: #0fa0b1;
  -webkit-transform: rotateY(-40deg);
  -moz-transform: rotateY(-40deg);
  -ms-transform: rotateY(-40deg);
  transform: rotateY(-40deg);
  text-shadow: -1px 0 1px #0fa0b1, 1px 0 1px rgba(0,0,0,0.8);
}
</style>
