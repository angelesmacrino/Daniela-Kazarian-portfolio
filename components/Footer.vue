<template>
<footer class="sticky-bottom">
    <div class="row">
    <small :class=" { yesHome: theme === 'ImHome'} ">Copyright © 2021 Daniela Kazarian. All Rights Reserved. Design by Angeles Macrino</small>
    </div>
</footer>
</template>

<script>

export default {
   props : ['theme']
}
</script>


<style scoped>
    small {
        font-size: 0.7em;
    }

    @media (max-width:414px){
        small {
            font-size: 0.6em
        }
    }

    .yesHome {
        background-color: rgb(29, 23, 23);
        border: none;
        color: rgb(165, 169, 172);
    }
</style>