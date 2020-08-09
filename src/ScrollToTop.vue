<template>
  <div class="vue-div-wrapper">
    <transition name="fade">
      <button class="vue-scroll-button" v-if="isVisible" @click="goToTop(duration)">{{this.text}}</button>
    </transition>
  </div>
</template>

<script>
  export default{
    name: 'ScrollToTop',
    props: {
      text: {
        type: String,
        default: 'Back to top',
      },
      visibleY:{
        type: Number,
        default: 400,
      },
      duration:{
        type: Number,
        default: 800,
      }
    },
    data(){
      return {
        isVisible: false
      }
    },
    created () {
      window.addEventListener('scroll', this.scrollEvent);
    },
    destroyed () {
      window.removeEventListener('scroll', this.scrollEvent);
    },
    methods: {
      scrollEvent () {
        this.isVisible = (this.visibleY < window.scrollY);
      },
      goToTop(duration){
        if (document.scrollingElement.scrollTop === 0) return;
        const totalScrollDistance = document.scrollingElement.scrollTop;
        let scrollY = totalScrollDistance
        let oldTimestamp = null;

        function step (newTimestamp) {
          if (oldTimestamp !== null) {
            scrollY -= totalScrollDistance * (newTimestamp - oldTimestamp) / duration;
            if (scrollY <= 0) return document.scrollingElement.scrollTop = 0;
            document.scrollingElement.scrollTop = scrollY;
          }
          oldTimestamp = newTimestamp;
          window.requestAnimationFrame(step);
        }
        window.requestAnimationFrame(step);

        this.$emit('scrolledOnTop');
      }
    }
  }
</script>

<style>
  .vue-scroll-button{
    cursor: pointer;
    position: fixed;
    z-index: 1000;
    margin-top:30px;
    border-radius: 20px;
    border: none;
    padding: 8px;
    background-color: black;
    color: white;
    outline: none;
  }
  .vue-scroll-button:hover{
    box-shadow: 0 12px 13px -6px black;
    transition: 0.5s;
  }
  .vue-div-wrapper{
    text-align: center;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }
  .fade-enter-active, .fade-leave-active {
    transition: opacity .2s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
</style>