<script setup>
import { onMounted, ref } from 'vue';


const images = ref([
    "//images.unsplash.com/photo-1691441131483-7901e11ba084?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1032&q=80",
    "//images.unsplash.com/photo-1674922164798-9f1ea898f58e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1032&q=80",
    "//plus.unsplash.com/premium_photo-1676231363985-279c8c60b708?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80",
    "//images.unsplash.com/photo-1681477421173-804e57cda0e5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=838&q=80"
])

let carousel = null

onMounted(() => {
    carousel = new Flickity('#image_slider', {
        autoPlay: true
    })
})

</script>

<template>
    <div>
        <h2 class="text-center text-4xl mt-6 mb-8">Image Carousel</h2>
        <div id="image_slider">
            <div :style="`background-image: url(${image})`" v-for="(image, index) in images" :key="index"></div>
            <!-- <img class="" :src="image" v-for="(image, index) in images" :key="index"> -->
        </div>
    </div>
</template>

<style scoped>
#image_slider {
    width: 750px;
    margin: auto;
    padding: 0 10px;
}
#image_slider div {
    height: 450px;
    width: 100%;
    background-size: cover;
    background-position: center;
}
</style>