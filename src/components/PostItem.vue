<template>
    <div class = "post">
        <div><strong>Название: {{ post.attributes.title }}</strong></div>
        <div><strong>Описание: {{ post.attributes.body }}</strong></div>
    </div>
</template>

  
<script>
export default{
    props:{
        post:{
            type: Object,
            required:true,
        }
    }
}
</script>

  
<style>
.post {
  padding: 15px;
  border: 2px solid rgb(30, 7, 230);
  margin-top: 15px;
  display: block;
  align-items: center;
  justify-content: space-between;

}
</style>
