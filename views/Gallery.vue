=>
<template>
  <div class="paraDesktop">
    <div class="gallery">
      <transition-group appear name="galleryTransitions">
        <div class="galleryPanel"
          v-for="photo in photos"
          :key="photo.id">
            <router-link :to="`/photo/${photo.id}`">
              <img :src="thumbnailUrl(photo.filename)" :alt="`${photo.alt}`">
            </router-link>
        </div>
      </transition-group>
    
    </div>
  </div>
  
</template>

<script>

    import photos from '@/photos.json';



    export default {
    name: 'Gallery',

        data() {
            return {
                photos,
            };
    },
        created() {
            this.$emit('gallery')
        },
        methods: {
    thumbnailUrl(filename) {
      return require(`../assets/images/thumbnails/${filename}`);
    },
  },
    }
</script>

<style scoped>

.galleryTransitions-enter-from {
opacity: 0;
}
.galleryTransitions-enter-to {
opacity:1
}

.galleryTransitions-enter-active {
transition: all 1s ease
}

 .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(20rem, 1fr));
    grid-gap: 1rem;
    max-width: 80rem;
    padding: 0 1rem;
  }

  .galleryPanel img {
    width: 100%;
    height: 25vw;
    object-fit: cover;
    border-radius: 0.75rem;
  }

  @media (width:360px) and (height:640px) {
    .galleryPanel {
      padding-right: 0px!important;
    }
  }

   @media (width:411px) and (max-height:823px) {
    .galleryPanel {
      padding-right: 0px!important;
    }
  }


  /*MEDIA QUERYES FOR IPHONE */

 @media (width:320px) and (height:568px) {
    .galleryPanel {
      padding-right:15px;
    }
  }

  @media (width:375px) and (height:667px) {
    .galleryPanel {
      padding-right:0px;
    }
  }

  /*MEDIA QUERYES FOR IPAD */

  @media (width:768px) and (height:1024px) {
    .gallery{
      padding-top:150px;
      padding-right:20px;
    }
  }

  @media (width:1024px) and (height:1366px) {
    .gallery{
      padding-top:150px;
      padding-right:20px;
    }
  }

  /*MEDIA QUERYES FOR DESKTOP */

  @media (min-width:1300px) {
    .paraDesktop {
      padding-left: 15%
    }
  }

</style>
