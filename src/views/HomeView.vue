<script>
export default {
  data(){
    return {
      isGanteng: false
    }
  },
  methods: {
    ubah(){
      this.isGanteng = !this.isGanteng
    }
  }
}
</script>

<template>
  <main>
    <button @click="ubah()">Switch</button>
    <h1 v-if="isGanteng">Ganteng dong!!</h1>
    <h1 v-else>Kamu jelek!!</h1>
  </main>
</template>
