<template>
  <transition name="fade">
    <div class="loading-wrap">
      <div class="loading-animate"></div>
      <p class="loading-prompt">loading···</p>
    </div>
  </transition>
</template>
<style lang="scss">
  @import "../assets/scss/_define.scss";
  .loading-wrap{
  @extend %pr;
    z-index: 9;
  }
  .loading-animate {
  @extend %pa;
    margin-top: 160px;
    left: 50%;
    width: 60px;
    height: 60px;
    background-color: #669999;
    margin-left: -30px;
    -webkit-animation: rotateplane 1.2s infinite ease-in-out;
    animation: rotateplane 1.2s infinite ease-in-out;
  }
  .loading-prompt{
  @extend %pa;
  @extend %f12;
  @extend %tac;
  @extend %c699;
    left: 0;
    right: 0;
    margin-top: 240px;
  }
  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }
  .fade-enter, .fade-leave-active {
    opacity: 0
  }
  @-webkit-keyframes rotateplane {
    0% { -webkit-transform: perspective(120px) }
    50% { -webkit-transform: perspective(120px) rotateY(180deg) }
    100% { -webkit-transform: perspective(120px) rotateY(180deg)  rotateX(180deg) }
  }
  @keyframes rotateplane {
    0% {
      transform: perspective(120px) rotateX(0deg) rotateY(0deg);
      -webkit-transform: perspective(120px) rotateX(0deg) rotateY(0deg)
    } 50% {
        transform: perspective(120px) rotateX(-180.1deg) rotateY(0deg);
        -webkit-transform: perspective(120px) rotateX(-180.1deg) rotateY(0deg)
      } 100% {
          transform: perspective(120px) rotateX(-180deg) rotateY(-179.9deg);
          -webkit-transform: perspective(120px) rotateX(-180deg) rotateY(-179.9deg);
        }
  }
</style>
