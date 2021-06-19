<template>
  <div class="home">
    <div class="row m-0">
      <div class="tabletSpacing"></div>
    <transition appear name="fade">
      <img class="img-fluid p-0" v-bind:src="require('../assets/' + mobileImg)" v-if="mobileView" />   
    </transition>

    
    
    <transition appear name = "fade">
      <img class="img-fluid p-0" v-bind:src="require('../assets/' + desktopImg)" v-if="!mobileView" />
    </transition>

    <div id="backBlock"></div>
    </div> 
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      mobileImg: "M02.jpg",
      desktopImg: "M01.jpg",
      mobileView: false,
      showNav: false,
    };
  },

  methods: {
      handleView() {
          this.mobileView = window.innerWidth <= 630;             
      },
  },
   created() {
      this.handleView();
      this.$emit('hi')
      window.addEventListener('resize', this.handleView)
  }
};
</script>

<style scoped>

.fade-enter-from {
opacity: 0;
}
.fade-enter-to {
opacity:1
}

.fade-enter-active {
transition: all 2s ease
}

  img {
    padding-right: 0px;
    padding-top: 8px;
    max-height:855px
  }

  #backBlock {
    margin: 0px;
    padding: 0px;
  }

  /*MEDIA QUERYES FOR MOBILE */

  @media (min-width:321px) and  (max-width:414px) {
    img {
      padding-top: 35px;
    }
  }

@media (width:411px) and (height: 823px) {
  #backBlock {
    height: 145px!important;
  }
}

@media (width:320px) and (height: 568px) {
  #backBlock {
    height: 15px!important;
  }
}

@media (width:360px) and (height: 640px) {
  #backBlock {
    height: 30px!important;
  }
}

  @media (min-height:640px) {
    #backBlock {
      height: 50px;
    }
  }

  @media (max-width:375px) and (max-height: 812px) {

  #backBlock {
      height: 180px;
    }

}

@media (width:414px) and (height: 736px) {

  #backBlock {
      height: 60px;
    }
}

@media (width:375px) and (height: 667px) {

  #backBlock {
      height: 35px;
    }

  }

    /*MEDIA QUERYES FOR DESKTOP */

    @media (min-width:768px) and (min-height:768px) {

       #backBlock {
      height: 0px;
    }
    }

      /*MEDIA QUERYES FOR TABLETS */

      @media (width:768px) and (height:1024px) {
        .tabletSpacing {
          height:100px;
          background: rgba(255, 255, 255, 1);
          
        }
        
      }

  
</style>

