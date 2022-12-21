<script>
export default {
    props: {
      thumb: String,
      galleries: Array
    },
    data(){
      return {
        defaultImage: ''
      }
    },
    methods: {
        changeDefaultImage(image){
            this.defaultImage = image
        }
    },
};
</script>

<template>
  <section id="gallery">
    <img
      :src="defaultImage ? defaultImage : thumb"
      alt=""
      class="w-full mt-6 rounded-2xl"
    />
    <div class="grid grid-cols-4 gap-4 mt-4">
      <template v-for="gallery in galleries" :key="gallery.id">
        <div @click="changeDefaultImage(gallery.url)" class="overflow-hidden cursor-pointer rounded-2xl" :class="{'ring-2 ring-indigo-500': defaultImage == gallery.url}">
            <img :src="gallery.url" class="w-full" alt="" />
        </div>
      </template>
    </div>
  </section>
</template>
