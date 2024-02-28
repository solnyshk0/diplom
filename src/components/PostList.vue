<template>
    <div>
        <h3>Новости</h3>
        <PostItem :post="post" v-for="post in posts"></PostItem>
    </div>
</template>

<script>
import PostItem from '@/components/PostItem.vue';

export default{
    props: {
        posts: {
            type: Array,
            required: true,
        }
    },
    components: { PostItem }
}
</script>

  
  <style scoped>
  .user-list-item {
    display: inline-block;
    margin-right: 10px;
  }
  .user-list-enter-active,
  .user-list-leave-active {
    transition: all 0.4s ease;
  }
  .user-list-enter-from,
  .user-list-leave-to {
    opacity: 0;
    transform: translateX(130px);
  }
  .user-list-move {
    transition: transform 0.4s ease;
  }
  </style>