<script>
import axios from "axios";
import ItemsCard from '@/components/ItemsCard.vue';

export default {
  components: {
    ItemsCard,
  },
  data() {
    return {
      items: [],
      data: {}
    };
  },
  methods: {
    async getProducts(){
      try {
        const response = await axios.get('https://zullkit-backend.buildwithangga.id/api/categories?id='+ this.$route.params.id)
        this.items = response.data.data.products
        this.data = response.data.data
      } catch(error){
        console.log(error);
      }
    } 
  },
  mounted() {
    this.getProducts();
  },
};
</script>

<template>
  <main>
    <div class="container px-4 mx-auto my-16 md:px-12" id="categories">
      <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">
        {{ data.name }}
      </h2>
      <div class="flex flex-wrap -mx-1 lg:-mx-4">
        <itemsCard 
          v-for="item in items" :key="item.id"
          :id="item.id"
          :title="item.name"
          :category="item.subtitle"
          :image="item.thumbnails"
        />
      </div>
    </div>
  </main>
</template>
