<script>
import axios from "axios";
import CategoriesCard from "@/components/CategoriesCard.vue";

export default {
  components: {
    CategoriesCard,
  },
  data() {
    return {
      categories: [],
    };
  },
  methods: {
    async getCategories() {
      try {
        const response = await axios.get(
          "https://zullkit-backend.buildwithangga.id/api/categories"
        );
        this.categories = response.data.data.data;
      } catch (error) {
        console.log(error);
      }
    },
  },
  mounted() {
    this.getCategories();
  },
};
</script>

<template>
  <main>
    <div class="container px-4 mx-auto my-16 md:px-12" id="categories">
      <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">
        All Categories
      </h2>
      <div class="flex flex-wrap -mx-1 lg:-mx-4">
        <CategoriesCard
          v-for="category in categories"
          :key="category.id"
          :title="category.name"
          :count="category.products_count"
          :image="category.thumbnails"
          :id="category.id"
        />
      </div>
    </div>
  </main>
</template>
