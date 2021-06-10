<template>
    <div class="d-flex flex-row-reverse align-items-center" id="navigation">
        <slot></slot>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Stylish&display=swap');

    p {
        font-family: 'Stylish', sans-serif;
        font-size: 1.5em;
    }

    p, img {

        padding-left: 10px;
    }
</style>