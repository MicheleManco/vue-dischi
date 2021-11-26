<template>
<div class="container-card">
    <div class="card">
        <div class="img-container"><img :src="details.poster" alt=""></div>
        <h2 class="title">{{details.title}}</h2>
        <div class="author">{{details.author}}</div>
        <div class="year">{{details.year}}</div>
    </div>
</div>
  
</template>

<script>
export default {
  name: 'Album',
  props:{
      details: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container-card {
width: 20%;
padding: 15px;
margin-top:50px ;
}
.card {
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #2e3a46;
    text-align: center;
    height: 370px;
    .img-container {
        width: 100%;
        img{
            max-width: 100%;
        }
    }
    .title{
            color: white;
            margin-top: 15px ;
        }
    .author{
        color: gray;
        margin-top: 15px;
    }
    .year{
        color: gray;
    }
}
</style>