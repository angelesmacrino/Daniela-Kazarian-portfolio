<template>
  <Header />
  <router-view v-on:hi="sayHi"/>
  <div v-if="viewingHome" >
      <Footer theme="ImHome" />
    </div>
    <div v-if="!viewingHome">
      <Footer />
    </div>
 

</template>

<script>
//TODO: clase dinamica para el footer.
        //

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
        console.log("hi")
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
</style>
