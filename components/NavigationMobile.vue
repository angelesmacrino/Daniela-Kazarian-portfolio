<template>
     <div class="d-flex flex-column-reverse align-items-center align-self-end shadow" id="navigation-mobile">
        <slot></slot>
    </div>
</template>



<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Stylish&display=swap');

    p {
        font-family: 'Stylish', sans-serif;
        font-size: 1.5em;
        
    }

    

    

    #navigation-mobile{
        position: absolute;
        top:-300px;
        right: 20px;
        background-color: white;

    }

  
    
</style>