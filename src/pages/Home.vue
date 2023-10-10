<script >
export default{
  data() {
    return{
      obs: 0,
      slides: [
        "https://i0.wp.com/www.giacomocusano.com/wp-content/uploads/2016/07/coastal-wash-web.jpg?fit=1024%2C682&ssl=1",
        "https://www.artemedialab.it/wp-content/uploads/2019/04/immagini-sfondo-1-700x400.jpg",
        "https://fotografiaartistica.it/wp-content/uploads/2019/06/nasa-immagini-gratuite-dello-spazio.jpg"],
      
      
      
    };
    
  },
  methods:{
    imagedestra(){
      if(this.obs == 2){
      this.obs = 0
    }else{
      this.obs ++
    }

    },
    imagesinistra(){
      if(this.obs == 0){
        this.obs = 2
      }else{
      this.obs --
      }
    }
  }
};
</script>

<template>
  <div class="arrows">
      <div class="arrows-left" @click="imagesinistra">&#129044;</div>
      <div class="arrows-right" @click="imagedestra">&#129046;</div>
    </div>
 <div class="carousel" v-for="(slide, i) in slides" :key="slide">
      <img  v-if="i == obs" :src="slides[i]">
 </div>
</template>

<style scoped>
.carousel{
  display: flex;
  align-content: center;
  
}
.arrows{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.arrows-left, .arrows-right{
  font-size: 100px;
}
</style>
