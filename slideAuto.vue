<template>
  <div class="slider">
    <div class="container-slides" :style="{transform: `translateX(${index}px)`}">
      <img src="" class="img-slider" alt="">
      <img src="" class="img-slider" alt="">
      <img src="" class="img-slider" alt="">
      <img src="" class="img-slider" alt="">
    </div>  
  </div>
</template>

<script>
 
export default {
  name:'Carrousel',
  data(){
    return{
      index:0,
    }
  },
  methods:{
    next(){
      console.log(this.index)
      if(this.index === -1500){
        this.index = 0;
      }else{
        this.index -= 500;
      }
    },
    prev(){
      if(this.index === 0){
        this.index = -1500;
      }else{
        this.index += 500;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.slider{
  width: 500px;
  height: 300px;
  margin: 100px auto 0;
  overflow: hidden;
  position: relative;
}
.container-slides{
  display: flex;
  animation: slide 13.5s ease infinite 0s;
  width: 400%;
  @keyframes slide {
    0%, 14.81%, 100% {
      transform: translate(0,0);
    }
    25.93%, 40.74% {
      transform: translate(-25%,0);
    }
    51.85%, 66.67% {
      transform: translate(-50%,0);
    }
    77.78%, 92.59% {
      transform: translate(-75%,0);
    }
  }
}
.img-slider{
  width: 100%;
  height: auto;

}


</style>