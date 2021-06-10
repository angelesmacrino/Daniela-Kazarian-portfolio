<template>
  <div class="home">
    <div class="row">

    <img class="img-fluid" v-bind:src="require('../assets/' + mobileImg)" v-if="mobileView" />
    <img class="img-fluid" v-bind:src="require('../assets/' + desktopImg)" v-if="!mobileView" />
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
          this.mobileView = window.innerWidth <= 700;
              
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
  img {
    padding-right: 0px;
    padding-top: 8px;
  }
</style>

