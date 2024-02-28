<template>
    <div>
        <PostList :posts="posts"></PostList>
        <img :src="imageUrl" alt="Image" />
    </div>
</template>

<script>
import PostList from "@/components/PostList";
import axios from 'axios';
export default{
    components:{
        PostList
    },
    data(){
        return{
            posts: [],
            imageUrl: ''
        }
    },
    created() {
    this.fetchImage()
    },
    methods:{
    async fetchImage() {
      try {
        const response = await fetch('http://localhost:1337/api/posts');
        const data = await response.json();
        this.imageUrl = data.url;
      } catch (error) {
        console.error(error);
      }
    },
           async FetchPosts(){
            try{
                const response = await axios.get('http://localhost:1337/api/posts');
                this.posts = response.data.data;
                console.log(response)
            } catch(e){
                alert('Ошибка')
            }
           },
    mounted(){
        this.FetchPosts();
    }
}
</script>

<style>
</style>