<template>
    <Gallery />
        <div id="lightbox" class="d-flex align-items-center" @click.self="closeLightbox">
          <div class="container" >
            <div class="row">
              <div class="col">
                <transition appear name="photo">
                <img class="img-fluid w-auto shadow" :alt="`${photo.alt}`" :src="photoUrl(photo.filename)"  @click.self="closeLightbox">
                  
                  
                </transition>

              <div id="lightbox-info" class="p-0 m-0">
                  <div id="lightbox-info-inner" class="rounded shadow">
                    <p class="m-0">
                      {{photo.title}}
                    </p>
                  </div>
                </div>  
              </div>
                
            </div>
          </div>
        </div>

    
 
</template>

<script>
import photos from '@/photos.json';
import Gallery from '@/views/Gallery.vue';



export default {
  name: 'Photo',
  components: {Gallery},
  data() {
    return {
      photos,
    };
  },
  computed: {
    photo() {
      return this.photos.find((photo) => {
        return photo.id === Number(this.$route.params.id);
      });
    },
  },
  methods: {
    photoUrl(filename) {
      return require(`../assets/images/${filename}`);
    },
    closeLightbox() {
    this.$router.push('/gallery');
    }
  },
};
</script>

<style scoped>

.photo-enter-from {
opacity: 0;
}
.photo-enter-to {
opacity:1
}

.photo-enter-active {
transition: all 1s ease
}

img {
  border-radius: 1rem;
}

#lightbox {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(143, 143, 143, 0.9);
  }
  
  #lightbox-info {
    margin: auto 2rem auto 0;
  }
  #lightbox-info-inner {
    background-color: #FFFFFF;
    display: inline-block;
    padding: 2rem;
  }

</style>