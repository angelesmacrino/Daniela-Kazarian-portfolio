<template class="m-0 p-0">
  <div v-bind:class="[{ wrapHome: viewingHome }, wrapnoHome]">
    <div  class="m-0 p-0">
      <Header />
      <router-view v-on:hi="sayHi" v-on:gallery="imnotHome" />
      <div v-if="viewingHome" >
          <Footer theme="ImHome" />
      </div>
      <div v-if="!viewingHome">
          <Footer theme="noHome" />
      </div>
    </div>
  </div>
</template>

<script>

  import Header from "./components/Header.vue"
  import Footer from "./components/Footer.vue"

  export default {
    name: "App",
    components: {
      Header,
      Footer,
    },
    data: () => {
    return {
      mobileView: false,
      showNav: false,
      viewingHome: false,   
    };
  },

  methods: {
      handleView() {
          this.mobileView = window.innerWidth <= 700;
              
      },
      sayHi() {        
        this.viewingHome = true
      },
      imnotHome() {
        this.viewingHome = false
      }    
  },

created() {
      this.handleView();
      window.addEventListener('resize', this.handleView)
  } 
  }
</script>




<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

  Header {
    background: white;
  }

 .wrapHome {
    background:rgb(29, 23, 23);
 }

 .wrapnoHome {
    background:rgb(255, 255, 255);
 }
</style>
