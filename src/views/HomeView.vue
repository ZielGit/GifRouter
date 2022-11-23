<template>
  <div>
    <h1 class="text-center">Gif Router</h1>
    <img :src="img" :alt="name">
  </div>
</template>

<script>
export default {
  data: () => ({
    img: "",
    name: ""
  }),
  created() {
    this.getRamdonGif();
  },
  methods: {
    async getRamdonGif(){
      const data = await fetch("https://api.giphy.com/v1/gifs/random?api_key=IGvt90bSMcE0dhKhcT4uLHTycvybOecy");
      const res = await data.json();
      
      this.img = res.data.images.original.url;
      this.name = res.data.title;
    },
  }
}
</script>

