<template>
  <div class="container">
    <div class="g-container">
      <div class="box">
        <div class="item item-right"></div>
        <div class="item item-left"></div>   
        <div class="item item-top"></div>
        <div class="item item-bottom"></div> 
        <div class="item item-middle"></div> 
      </div>
      <div class="box">
        <div class="item item-right"></div>
        <div class="item item-left"></div>   
        <div class="item item-top"></div>
        <div class="item item-bottom"></div> 
        <div class="item item-middle"></div> 
      </div>
    </div>
  </div>
</template>


<script>

  export default {

  }

</script>


<style scoped>
  .container {
    height: 800px;
    overflow: hidden;
    background-color: #000;
    text-align: center;
  }
  .container:before{
    content: '';
    display: inline-block;
    height: 100%;
    vertical-align: middle;
  }
  .g-container {
    display: inline-block;
    vertical-align: middle;
    perspective: 4px;
    perspective-origin: 50% 50%;
    position: relative;
    animation: hueRotate 21s infinite linear;
  }
  .box {
    position: absolute;
    /*   perspective: 4px; */
    width: 1000px;
    height: 1000px;
    left: -500px;
    top: -500px;
    transform-style: preserve-3d;
    animation: move 12s infinite linear;
    animation-fill-mode: forwards;
  }
  .box:nth-child(2){
    animation: move 12s infinite linear;
    animation-delay: -6s;
  }
  .item {
    position: absolute;
    width: 100%;
    height: 100%;
    background: url(https://z3.ax1x.com/2021/08/20/fLwuMd.jpg);
    background-size: cover;
    opacity: 1;
    animation: fade 12s infinite linear;
    animation-delay: 0;
  }
  .box:nth-child(2) .item {
    animation-delay: -6s;
  }
  .item-right {
    transform: rotateY(90deg) translateZ(500px);
  }

  .item-left {
    transform: rotateY(-90deg) translateZ(500px);
  }

  .item-top {
    transform: rotateX(90deg) translateZ(500px);
  }

  .item-bottom {
    transform: rotateX(-90deg) translateZ(500px);
  }

  .item-middle {
    transform: rotateX(180deg) translateZ(1000px);
  }

  @keyframes move {
    0%{
      transform: translateZ(-500px) rotate(0deg);
    }
    100%{
      transform: translateZ(500px) rotate(0deg);
    }
  }

  @keyframes fade {
    0%{
      opacity: 0;
    }
    25%,
    60%{
      opacity: 1;
    }
    100%{
      opacity: 0;
    }
  }

  @keyframes hueRotate {
    0% {
      filter: hue-rotate(0);
    }
    100% {
      filter: hue-rotate(360deg);
    }
  }
</style>