<template>
    <div>
      <img :src="imageUrl" alt="Image" />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        imageUrl: ''
      };
    },
    created() {
      this.fetchImage();
    },
    methods: {
      async fetchImage() {
        try {
          const response = await fetch('https://your-strapi-url.com/images/1');
          const data = await response.json();
          this.imageUrl = data.url;
        } catch (error) {
          console.error(error);
        }
      }
    }
  };
  </script>
  