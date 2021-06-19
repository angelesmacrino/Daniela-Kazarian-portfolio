<template>
<div class="d-flex flex-row justify-content-center align-items-top flex-wrap">
  <figure class="image">
    <transition appear name = "fade">
      <img class=" p-0 rounded" v-bind:src="require('../assets/' + aboutMeImg)" alt="Daniela Kazarian fictonalized persona, alien-like creature" />
    </transition>
    <blockquote class="p-3 m-0">
      <i>
        <strong>"Some people say my work is often depressing and pessimistic,
        with the emphasis on death, blood, overcrowding, 
        strange beings and so on, but I don't really think it is."</strong>
      </i>  
    </blockquote>
    <figcaption>
      &mdash; H.R. Giger
    </figcaption>
  </figure>
  <p>
    Inspired in the works of H.R. Giger, 
    White Wolf's <cite>World of Darkness</cite> and David Cronenberg films.
    Her main themes are dark mutations, transformations and twisted creatures. 
  <br>
  <br>  
    Daniela Kazarian lives with her two cats, dog and parrot in Buenos Aires,
    Argentina. She is a web developer and artist,
    and in her free time she loves playing video and tabletop games.
  </p>

</div>

  
   

</template>

<script>

export default{
  data: function() {
    return {
      aboutMeImg: "incarna.jpg"
    }
  },
  created() {
    this.$emit('gallery')
  },


}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Stylish&display=swap');

p {
  max-width: 400px;
}

img {
  min-width:300px;
  min-height:350px;
  max-width:500px
}

.image {
  max-width: 500px;
  margin:0px
}

.quote {
  max-width: 400px
}

.fade-enter-from {
opacity: 0;
}
.fade-enter-to {
opacity:1
}

.fade-enter-active {
transition: all 2s ease
}

p {
  font-family:'Stylish', sans-serif;
  font-size:1.1rem
  }

  img {
    max-height:80%;
    max-width:80%
  }








  
</style>

