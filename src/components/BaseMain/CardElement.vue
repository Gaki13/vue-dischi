<template>
    <div class="card">
        <img :src="album.poster" alt="">
        <h2 class="Title">{{album.title}}</h2>
        <p class="Author">{{album.author}}</p>
        <p class="Year">{{album.year}}</p>
    </div>
</template>

<script>

export default {
    name: 'CardElement',
    props: {
        album: Object,
    }  
}
</script>

<style lang="scss" scoped>
   .card{
       background-color: #2e3a46;
       padding: 1rem;
       text-align: center;
       margin: 1rem;
       .Title{
           color: white;
       }
       .Author, .Year{
           color: #808080;
       }
   }
</style>