<template>
  <div class="d-flex flex-row  p-3">
    <div class="col-6 text-nowrap">
      <h1 class="text-start display-5">Daniela Kazarian</h1>
    </div>
    <div class="col-6 align-items-center">
      <div id="navigation-icon" class="text-end me-5" v-if="mobileView" @click="showNav = !showNav">
          
          <img src="../assets/menu.svg" alt="Hamburguer menu icon">
      </div>
        <NavigationDesktop v-if="!mobileView">
            <a href="https://www.artstation.com/nairazak" target="_blank"><img class="my-2 m-2" src="../assets/artstation.svg" alt="Arstation icon"></a> 
            <a href="https://www.instagram.com/nairazak.art/" target="_blank"><img class="my-1 m-2" src="../assets/instagram.svg" alt="Instagram icon"></a> 
            <p class="p-1 m-2"><a href="" class="text-decoration-none text-reset">Gallery</a></p>
            <p class="p-1 m-2"><router-link :to=" {name: 'About'} "  class="text-decoration-none text-reset">About</router-link></p>       
            <p class="p-1 m-2"><router-link :to=" {name: 'Home'} "  class="text-decoration-none text-reset">Home</router-link></p>
        </NavigationDesktop>
      <div :class="{'open':showNav, 'closed':!showNav}">
        <NavigationMobile>
            <a href="https://www.artstation.com/nairazak" target="_blank"><img class="my-2 m-2" src="../assets/artstation.svg" alt="Arstation icon"></a> 
            <a href="https://www.instagram.com/nairazak.art/" target="_blank"><img class="my-1 m-2" src="../assets/instagram.svg" alt="Instagram icon"></a> 
            <p class="p-1 m-2"><a href="" class="text-decoration-none text-reset">Gallery</a></p>
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

@media (max-width:280px) {

  #navigation-icon {
     padding-left: 100px;
  }



}
</style>