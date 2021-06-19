<template>
  <div class="d-flex flex-row  p-3" id="myHeader">
    <div class="col-6 text-nowrap">
      <h1 class="text-start display-5">Daniela Kazarian</h1>
    </div>
    <div class="col-6 align-items-center">
      <div id="navigation-icon" class="text-end me-5" v-if="mobileView" @click="showNav = !showNav">
          
          <img src="../assets/menu.svg" alt="Hamburguer menu icon" id="hamburguerMenu">
      </div>
        <NavigationDesktop v-if="!mobileView">
            <a href="https://www.artstation.com/nairazak" target="_blank"><img class="my-2 m-2" src="../assets/artstation.svg" alt="Arstation icon"></a> 
            <a href="https://www.instagram.com/nairazak.art/" target="_blank"><img class="my-1 m-2" src="../assets/instagram.svg" alt="Instagram icon"></a> 
            <p class="p-1 m-2"><router-link :to=" {name: 'Gallery'} "  class="text-decoration-none text-reset">Gallery</router-link></p>       
            <p class="p-1 m-2"><router-link :to=" {name: 'About'} "  class="text-decoration-none text-reset">About</router-link></p>       
            <p class="p-1 m-2"><router-link :to=" {name: 'Home'} "  class="text-decoration-none text-reset">Home</router-link></p>
        </NavigationDesktop>
      <div :class="{'open':showNav, 'closed':!showNav}">
        <NavigationMobile  @click="showNav = !showNav">
            <a href="https://www.artstation.com/nairazak" target="_blank"><img class="my-2 m-2" src="../assets/artstation.svg" alt="Arstation icon"></a> 
            <a href="https://www.instagram.com/nairazak.art/" target="_blank"><img class="my-1 m-2" src="../assets/instagram.svg" alt="Instagram icon"></a> 
            <p class="p-1 m-2"><router-link :to=" {name: 'Gallery'} "  class="text-decoration-none text-reset">Gallery</router-link></p>       
            <p class="p-1 m-2"><router-link :to=" {name: 'About'} "  class="text-decoration-none text-reset">About</router-link></p>
            <p class="p-1 m-2"><router-link :to=" {name: 'Home'} "  class="text-decoration-none text-reset">Home</router-link></p>
        </NavigationMobile>
      </div>
    </div>
  </div>
</template>

<script>
import NavigationDesktop from "./NavigationDesktop.vue";
import NavigationMobile from "./NavigationMobile.vue"

export default {
  name: "Header",
  components: {
    NavigationDesktop: NavigationDesktop,
    NavigationMobile: NavigationMobile,
  },
  data: () => {
    return {
      mobileView: false,
      showNav: false,

    };
  },

  methods: {
      handleView() {
          this.mobileView = window.innerWidth <= 700;
              
      }
  },

  created() {
      this.handleView();
      window.addEventListener('resize', this.handleView)
  }
};
</script>



<style scoped>

@import url("https://fonts.googleapis.com/css2?family=Yeon+Sung&display=swap");
@import url('https://fonts.googleapis.com/css2?family=Stylish&display=swap');

p {
      font-family: 'Stylish', sans-serif;
      font-size: 1.5em;
      
  }

h1 {
  font-family: "Yeon Sung", cursive;
}

.open {
  transform: translateY(300px);
  transition: 0.5s transform cubic-bezier(.11,.34,.65,.95);

}

.closed {
    transform: translateY(-300px);
    transition: 0.5s transform cubic-bezier(.11,.34,.65,.95);
}

#myHeader{
  background: white;
}

@media (width:360px) and (height: 640px) {
  #myHeader {
    padding-bottom: 10px!important;
    padding-top: 20px!important;
  }
  #hamburguerMenu {
    padding-top: 10px;
    padding-left:100%
  }
}

@media (max-width:540px) and (max-height: 823px) {
  #hamburguerMenu {
    padding-top: 10px;
    padding-left:100%
  }
}






@media (width:411px) and (height: 823px) {
  #myHeader {
    padding-top: 20px!important;
  }
  

}

@media (max-width:280px) {

  #navigation-icon {
     padding-left: 100px;
  }



}


</style>